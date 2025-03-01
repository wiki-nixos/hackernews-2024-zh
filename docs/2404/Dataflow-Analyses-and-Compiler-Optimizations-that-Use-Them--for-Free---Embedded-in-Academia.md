<!--yml

category: 未分类

日期：2024-05-27 13:24:06

-->

# 数据流分析和使用它们的编译器优化，免费获取 —— Embedded in Academia

> 来源：[https://blog.regehr.org/archives/2578](https://blog.regehr.org/archives/2578)

编译器可以随着时间的推移而改进，但这是一个缓慢的过程。"Proebsting's Law"是一个古老的笑话，它建议编译器优化的进步将使计算速度每18年翻倍一次 —— 但如果说有什么乐观的话，那也是如此。缓慢的编译器进化从来不是一件好事，但在当今GPU、TPU和其他娱乐平台快速创新的环境中尤为棘手。

我们研究小组的主要目标之一是创建技术，使自我改进的编译器成为可能。将人类排除在编译器改进循环之外将使这一过程快上数个数量级，并且最终的编译器也倾向于通过设计来保证正确性。其中一种技术是超级优化，通过使用昂贵的搜索过程来发现编译器中缺失的优化。另一种技术是[泛化](https://users.cs.utah.edu/~regehr/generalization-oopsla24.pdf)，它将一个特定的优化（可能是超级优化器发现的，但不一定）转化为广泛适用的形式，适合包含在生产编译器中。

与一个代表性基准套件一起，超级优化+泛化将导致一种完全自动化的自我改进循环，用于优化编译器的一部分：窥孔优化器。在本文的其余部分，我将勾勒出这种自我改进循环的扩展版本，其中包括数据流分析。

数据流分析的目标是计算程序编译过程中每次执行时为真的有用事实。例如，如果我们可以证明 x 总是在 [5..15] 范围内，那么当 x 用作20元素数组的索引时，我们就不需要发出数组边界检查。这种特定的数据流分析是整数范围分析，像GCC和LLVM这样的编译器在每次优化编译时执行它。另一个分析方法 —— LLVM尤其依赖于它 —— 是"已知位"，它试图证明SSA值的各个位在所有执行中是否为零或一。

在文献中，我们可以找到大量的数据流分析，其中一些对优化某些类型的代码非常有用 — 但很难知道究竟哪些值得实现。我们可以尝试不同的方法，但是在一个生产编译器中实现一个新的数据流分析是一项很大的工作。这个工作可以分为两个主要部分。首先是实现分析本身，这需要在编译器的IR中创建每个指令的抽象版本：这些被称为数据流传递函数。例如，为了实现整数范围的加法操作，我们可以使用 [lo1, hi1] + [lo2, hi2] = [lo1 + lo2, hi1 + hi2] 作为传递函数。但即使在这种特别简单的情况下，如果我们需要处理溢出，这个工作也会变得更加复杂，而为位运算符编写正确和精确的传递函数则更不直接。同样地，考虑编写一个用于乘法的正确和精确的已知位传递函数。这并不容易！然后，一旦我们完成了这项工作，我们就需要做第二部分工作，即实现利用新数据流事实的优化。

我们能自动化这两部分工作吗？可以！在创建数据流事实的表示并正式化它们的含义方面，有一些初步工作是无法自动化的，但这并不是难事。然后，要自动创建数据流传递函数，我们转向这篇[非常好的论文](https://pages.cs.wisc.edu/~loris/papers/oopsla22.pdf)，该论文通过在严格的完整性约束和软精确性约束之间夹入合成的代码来综合它们。基本上，每个数据流分析最终都会进行逼近，但这些逼近只能在一个方向上，否则分析结果无法用于证明编译器优化。该论文留下一些工作需要在生产编译器中实际化，但在我看来，这主要是一个工程问题。

数据流传递函数的一个特性是它们在指令边界上失去精度。我们可以通过找到通常一起出现的指令集合（例如执行最小或最大操作的指令）并为聚合操作综合一个传递函数来减轻这一点。我们还可以通过特别处理一个指令的两个参数来恢复精度，这两个参数来自同一个源。在手动编写数据流传递函数时，我们不倾向于做这些事情，但在自动化工作流中，这些都不是问题。我们希望自动化的另一件事是创建高效且精确的[乘积运算符](https://arxiv.org/abs/1309.5146)，使数据流分析能够互相交换信息。

给定一组数据流传输函数，创建数据流分析就是将它们插入一个通用的数据流框架中，应用传输函数直到达到不动点。这些都是老生常谈的问题。数据流分析的结果是一组附加到每个正在编译的文件中指令的数据流事实。

要自动利用数据流事实来驱动优化，我们可以使用一个超级优化器。例如，我们教Souper使用了LLVM的几个数据流结果。与首次创建超级优化器相比，这很容易：基本上，我们可以重用已经创建的数据流分析的同一形式化，以合成传输函数。然后，泛化引擎还需要完全支持数据流分析；我们的[Hydra](https://users.cs.utah.edu/~regehr/generalization-oopsla24.pdf)工具已经在这方面做得很好，论文中有大量细节。

现在我们已经闭环了，让我们问一下LLVM中是否缺少一些有趣的数据流分析，我们应该实现哪些？当然我不能确定，但我长期以来一直对尝试的一个领域感兴趣，那就是“同余”，对于一个变量v，我们试图证明它总是满足v = ax+b，其中a和b是一对常数。这种领域对于追踪指向结构体数组的值非常有用，其中a是结构体的大小，b是其字段之一的偏移量。

我们当前的生产编译器生成，在实现层面上，与编译的数学基础有些脱节。在未来，我们将直接从这些基础中推导编译器实现的部分，例如数据流分析和窥孔优化。

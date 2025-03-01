<!--yml

类别：未分类

日期：2024-05-29 12:30:31

-->

# 反演：快速、可靠的结构化LLMs - Rysana

> 来源：[https://rysana.com/inversion](https://rysana.com/inversion)

# **反演**：快速、可靠的结构化LLMs

在Rysana，我们打造了**反演**——我们的结构化语言模型系列，旨在解决先前AI系统中的速度、可靠性和推理问题。

在600次抽取与推理测试中，字符每秒推理速度的平均/90/99百分位数。（数值越高越好）

我们的第一代模型在抽取和函数调用等结构化任务中达到了现代水平，同时比最佳替代品运行速度快**100×**以上，延迟降低**10×**以上，输出**100%可靠的结构**，比任何其他地方提供的最深入支持的JSON输出还要少**10,000×**的开销。

反演模型做更多，用更少——它们使用更少的计算资源、时间和数据，产生质量更高、可靠性更强、推理能力更强的输出。

成为第一批尝试反演的人。[注册获取早期访问权](/request-access)。

## 100× 更快的打字LLM推理

我们受到通用语言模型在理解系统和通过自然语言和结构化数据将人类意图与机器行动紧密联系的能力的激发，于2023年2月开始构建反演。

在我们基于这些模型构建产品时，我们发现这些模型在生产环境中的可靠性、成本和速度远不足够。我们需要创建一种新型模型，可以在实际环境中大规模处理我们的工作负载。

关键洞见在于**结构化推理**本质上是加速的——如果我们构建的模型能始终可靠地输出带约束的结构化数据，我们可以大幅提升输出的速度和质量。

首令牌时间（毫秒）在600次抽取与推理测试中的最小/平均/最大值。（数值越低越好）

我们致力于将同等质量的现代LLMs在诸如函数调用、[操作/工作流程](/docs/lusat)和动态UI生成等工作负载下的输出时间，从大约一分钟缩短到不到100毫秒，这大致是人类感知响应为即时的速度。

确保输出始终与我们期望的数据类型匹配至关重要，对我们来说，这意味着对于函数参数或组件属性，必须有效地符合JSON模式。

这样的系统将解锁**新的AI本地应用的寒武纪爆发**，具有可靠的实时感——从能够对复杂动态环境做出反应的人形机器人和游戏NPC，到能够理解并处理复杂人类意图的自然语言界面和代理，眨眼之间即可完成操作。

这意味着：

1.  我们需要在几乎没有时间内处理语法和模式，

1.  我们需要将模型的延迟降低到几乎即时，

1.  我们需要将推理加速到超过10,000 Hz。

在400个JSON模式测试中，输出约束的编译时间，微秒为单位，最小/平均/最大。无缓存，完全动态，相同硬件。比率是测试比率的平均值，而不是测试平均值的比率。

我们构建的第一组组件是用于处理数据结构和通过它们约束模型输出的系统。我们发明了一种新型编译器和基于物理的投影模型，实现了比最佳可比库更**严格**的约束，生成类型化JSON的编译速度约为**10,000倍快**。

我们的反向编译器处理一个典型的前所未见的模式/语法，大约在100 微秒（微秒）内，并在运行时约10 微秒内对模型约束进行采样，支持每秒超过**100,000 个令牌**的推断，输出完美结构化。

在600次提取和推理测试中，无效输出数据结构的百分比。（越低越好）

阅读更多关于在[文档](/docs/api/json-schema)中支持的类型和约束。

开发者体验可以确保您获得所要求的确切类型，这是一种享受。

始终有效的输出对于结构化工作负载来说是一个革命性的变革，显著提高了LLM在大多数任务中的可靠性和推理水平。与其他我们测试过的模型相比，反向模型通常可以达到或超过，甚至是具有10倍以上参数的模型。

在600次测试中，按操作/功能、提取和类型数据生成分组的正确输出百分比。（越高越好）

我们目前正在扩展对第一代反向模型的访问，并已经开始构建下一代模型，目标推理速度约为100,000赫兹。

## 加速结构化推理

您可能会想知道——这些都是如何实际工作的？

为什么反向模型在多个可能看似相互矛盾的前沿领域如约束和速度方面领先？这些领域通常需要权衡。

当我们刚开始使用反向模型时，它实际上比类似模型略慢——几乎比最强模型快不了多少，也不太可靠，截至去年春初。第一步是在常见JSON类型上实现保证的结构，这也是编译器的起源。

接下来，我们利用编译结构来“反转”推理过程，使用输出的约束动态调节所需计算量，从而增减生成每个令牌的计算量。

您可以将此视为根据输出结构中的位置开关大型神经元集群，而不仅仅是修改令牌采样。数学上，这是从完整模型到剪裁掉不需要的子层的较小模型的*投影*。

在反向模型测试中的字符每秒吞吐量。灰色表示比较的第三方模型。（越高越好）

去年夏天，我们建立了一个简化版，推理速度提升了约10倍，但要达到当前的性能水平，我们不得不从头开始完全重写我们的推理和学习系统，并训练新型神经网络以加速变压器的动态增强。

今天，我们的模型在每个可寻址的堆栈层面上都融合了几十项主要改进和数百项次要优化，而且我们已经在每个月保持了他们的效率一致提升。

**更新**：自从我们大约一个月前发布了这则公告以来，我们在推理速度方面又提升了114%，采样效率提高了100倍，编译速度提升了4倍，此外还有更多可靠性和推理能力的改进。

## Inversion v2及以后版本

我们还在研发一类全新的模型，面向Inversion的下一代 - 它们目前还没有准备好，但我们预计在各个方面实现另一个数量级的提升，希望尽可能多的重型工作负载在单个或双位数毫秒内完成，计算成本只需几分之一，并且在前所未有的可靠性和质量上。

我们期待：

+   打破预先训练的通用模型趋势，通过创建一种能够即时适应每个人并不断提升的架构。

+   实时生成UI组合，具备类型沙箱化代码生成。

+   提升多语言支持，深入理解方言和个人细微差异。

+   还有更多更多！

我们很高兴在接下来的几个月内分享更多关于此的信息。

## 为开发者打造

我们的目标是提供最佳的开发者体验，查看通过JS/TS（使用`zod`）、Python（使用`pydantic`）、cURL（使用JSON Schema）进行请求的各种方法示例：

## 我们的共同未来

我们将共同创造一个技术增强人类天才、使琐碎任务变得微不足道并赋予每个人更好生活和追求激情的未来。

加入我们的旅程，分享我们正在构建的技术见解和访问权限。

联系我们 [@RysanaAI](https://x.com/RysanaAI)

## 订阅我们的新闻简报

当我们发布新文章时，您将收到一封电子邮件。没有垃圾邮件，只有好东西。

### 总结

我们创造了**Inversion** - 一系列设计用于解决传统AI系统中速度、可靠性和推理问题的结构化语言模型。

我们的第一代模型在结构化任务（如提取和函数调用）方面是目前的最新技术，推理速度高达**100倍**，延迟降低**10倍**，输出**100%可靠结构**，比最佳替代方案的开销减少**10,000倍**，并且提供了现有任何地方最深度的类型化JSON输出支持。

我们很快将扩展访问第一代Inversion模型，并已开始构建目标为每秒推理100,000次的下一代模型。

成为第一批尝试逆转的人。[注册获取早期访问权限](/request-access)。

*所有近似数字基于2024年3月至5月的1000次测试。结果可能有所不同。实验模型尚未最终确定。模型由单个客户端进行测试，依次向每个模型API服务器快速发出请求。推断速度计算为总输出字符数除以总请求时间。吞吐量计算为总输出字符数除以总请求时间减去首个标记时间。延迟计算为从请求开始到在请求客户端接收到首个标记的时间。类型错误率是根据请求的模式无法解析的输出百分比。

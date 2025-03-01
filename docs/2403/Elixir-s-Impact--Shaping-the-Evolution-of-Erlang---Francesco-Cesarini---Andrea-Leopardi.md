<!--yml

category: 未分类

date: 2024-05-29 12:40:51

-->

# Elixir的影响：塑造Erlang的演进 • Francesco Cesarini和Andrea Leopardi

> 来源：[https://goto.buzzsprout.com/1714721/14674925](https://goto.buzzsprout.com/1714721/14674925)

**介绍**

Andrea Leopardi：大家好。欢迎来到哥本哈根GOTO Copenhagen 2023的另一期GOTO Unscripted节目。我是Andrea Leopardi，来自意大利，是Elixir团队的一员。Elixir是一种运行在Erlang虚拟机上的函数式语言，今天我在这里与Francesco Cesarini一起。

Francesco Cesarini：我是Francesco Cesarini。我是Erlang Solutions的创始人和技术总监。自90年代中期以来，我一直在Erlang生态系统中工作。能够见证一门编程语言成为语言生态系统，我感到非常幸运。我想这可能是我们今天要讨论的内容，对吧？

Andrea Leopardi：Francesco和我住得非常近。

**Erlang生态系统的扩展**

Andrea Leopardi：我们在意大利从未见过面，只是通过各种会议，各种会议认识的，但是，是的。他参与Erlang的时间比我长得多。我加入了Elixir的一代，是的。那么，看到这个生态系统的扩展，或者说，这个小语言的成长是怎样的？

Francesco Cesarini：这真的很有趣。我是说，BEAM上的第一门语言出现了……我发现它已经被写出来了，它叫做[inaudible 00:01:17]。我在2008年的波特兰开源大会上听说了它。因此，当我们在美国举办第一次会议时，我们邀请Tony前来演讲。看他如何将类似Ruby的语法应用于运行在BEAM上的Erlang，而今天我们运行的所有东西都是在这个主要的虚拟机上。然后，很快Lisp Flavored Erlang由Robert Virding和Mariano Guerra创造了Efene。因此，有很多Prologue，你知道，被移植了。因此，出现了许多语言，甚至有些被用于生产中。

但是我们直到2014年在旧金山时，第一次在厄朗工厂专门为Elixir设立了一个完整的跟踪，我们才意识到它已经成为一种语言生态系统。那时还只是初期阶段。我记得那是第一次举办Elixir Comp的年份，大约有140人参加，包括戴夫·托马斯的狗在内。当时我和加勒特·史密斯一起散步，我们讨论着这种名为Elixir的新现象，对正在发生的事情感到兴奋，以及Elixir如何向程序员社区敞开了大门。在那次谈话中，我们意识到，你知道的，加勒特提出了一个观点：“是的，厄朗现在正在成为一种语言生态系统”，这时一切就豁然开朗了。这就是Java发生的事情，完全是这样。NET也是如此。而厄朗也在经历同样的过程，看到这一切真是令人惊叹。今天看来，我认为在BEAM上运行的语言超过35种，这非常令人印象深刻。你知道，并非所有这些语言都用于生产，很多还在试验阶段。

**厄朗的风味**

安德里亚·莱奥帕迪：而且有趣的是，我之前和音乐编程语言Sonic Pi的Sam Aaron交谈时，他谈到Java和Clojure之间的差异远远大于例如厄朗和Elixir之间的差异。我认为这是……你是否认为在……而在BEAM上的语言之间，尽管有许多不同的风格，一些是静态类型的，一些像Lisp，或者看起来像Prolog，或者看起来有点像Ruby。你感觉这些差异……？我的感觉是这些差异就像……

弗朗切斯科·切萨里尼：我同意。它们并不……差异并不是很大，但我认为厄朗……当他们发明厄朗，创造厄朗时，他们做对了很多事情。他们花了大约三年的时间来原型化一个特定领域的问题，你知道，可扩展、完全容错、软实时系统的问题域。首先看看所有已存在的语言，80年代工业中正在使用的语言，然后从那里使用一个实现Prolog的虚拟机。因此，当他们开始创建用C编写的第一个虚拟机时，他们在这些原型活动中取得了很大进展，他们简化并创建了这门语言，仅仅是最基本和最必要的部分。

如果你问 Erlang 的不同共同发明者他们的贡献是什么，你知道的，Mike Williams 曾经告诉我，“哦，我大部分时间都在说服 Joe 和 Robert，即使这是一个很酷的语言特性，我们也不需要它，因为它没有增加任何价值。”这些设计和原型活动，他们看了不同的构造，测试了它们，如果这个构造增加了价值，减少了代码量，并使建设这些电信系统的任务更容易，他们就保留了它。如果没有，他们就移除了。因此，作为结果，我认为 Erlang 成为了一种非常紧凑的、适合其用途的语言。因此，我认为所有基于 BEAM 的语言，你知道的，都得到了所有这些特性，并且为其增加了各自的风味。无意间看了我得到的 T 恤。

Andrea Leopardi：你最喜欢的 Erlang 口味是哪种？这个问题很小。但是我在想，你认为这些语言之间的相似性也是由于...至少我部分感觉是这样，还因为 Erlang 确实很难扩展？比如说，它不像其他语言一样，Erlang 的基本数据结构非常固定。如果你看看像是 Erlang 中的队列，它们是基于现有的数据结构 double 和 list 实现的，对吧？或者你看看 Elixir，它们必须基于 maps 实现。它们在编译时进行检查，但是必须基于 maps 实现。你认为这是...？

Francesco Cesarini：我的意思是，使用 Erlang 你可以做任何事情。但是当语言的发明者们去创建一个编程语言时，他们是为了解决特定的问题。我认为，你知道的，他们试图解决的问题决定了他们需要的特性。比如说，如果你看宏，它们在 Erlang 中是存在的，但是它们被隐藏得非常好，不是每个人都能访问。因此，它们使用起来和实现起来都非常困难。这是一个有意的决定，因为他们不想让语言变得可扩展。我认为他们试图解决的问题之一是维护成本。他们试图通过工具和 VM 中的检查点来降低系统的维护和运营成本，这一点他们非常成功。再说一遍，你知道的，我们能够解决所有系统的问题，很少有人说，你知道的，我们希望有这个或者那个。也许有些库可能缺失，但不是语言特性，因为保持简单意味着你可以在其之上用几行代码实现你需要的东西。

Andrea Leopardi：一个非常有趣的事情是，比如说 maps，是最近的 Erlang 特性，对吧？现在它们感觉像是一种非常必要的语言特性。

Francesco Cesarini: 绝对。我是说，我相信地图最初是由理查德·奥基夫在爱立信用户大会上首次介绍的，而在 2000 年才最终成为地图，但可能还需要十年才能将它们引入语言中。

Andrea Leopardi: 因为我记得大约在 Elixir 变成 1.0 的时候它们才进入 OTPR，比如说 17 可能是...

Francesco Cesarini: 对的。是的。而且，这是爱立信，你知道，爱立信是一个仁慈的独裁者，这就是现实，当你在处理开源时，他们对新功能非常保守，因为它们会增加语言的复杂性。毕竟，如果他们添加了什么，他们需要支持和维护它。

Andrea Leopardi: 几十年了。

Francesco Cesarini: 而且不仅如此，他们所做的每一件事都需要向后兼容。因为在生产中有数千万行的代码。如果你做了什么不向后兼容的东西，你会破坏构建过程，升级可能需要...是的，可能需要几年时间。我们曾经在项目上工作过，他们分叉了 BEAM，并且在几年后，有时候需要 6 到 12 个月的工作来将代码库恢复到 BEAM 的最新版本，我们在多个场合见过这种情况。

Andrea Leopardi: 不过我喜欢的是，我有一个希望列表，里面有一些可能会进入 Erlang 的东西。我认为可能最大的一个是结构体，因为它们的互操作性会很好。就像事实上...

Francesco Cesarini: 我认为结构体正是阻碍从 Erlang 调用 Elixir 库变得简单的原因。

Andrea Leopardi: 是的，因为你必须做一些看起来神秘的事情才能让它们工作。

Francesco Cesarini: 没错。这是其中一个限制性问题。所以，你知道，有一些讨论正在进行，其中一个缺失的可能性是为了兼容性问题向语言添加结构。我是说，回到第一个 ElixirCon，如果我没记错的话，约瑟曾经说过，哦，我们可以访问所有以 Erlang 编写的库，这些库已经存在了几十年的开源库，我们可以从 Elixir 中使用，而反过来却不是...你知道，你没有从 Erlang 那里得到相反的东西。现在是回报的时候了，所以是的，添加结构将会是...你知道，这将是一个巨大的好处。

Andrea Leopardi: 我也这么认为。而且有这样一个中心，就像 Elixir 似乎围绕结构体大量发展。这非常...你在各个地方都可以看到它们，非常符合习惯，如果能看到它们在 Erlang 核心中会很好，因为你可能可以显著优化例如标记这个结构体。毕竟，我们必须使用这个小构造，它占用内存，而我们系统中的所有这些结构都应该在 BEAM 中，因为这可能会改变。

Francesco Cesarini: 绝对。完全正确。

Andrea Leopardi: 所以，这非常有趣。

Francesco Cesarini：顺便说一句，Robert Virding 在 Lisp Flavored Erlang 中添加了结构体，这是...是的，BEAM 上运行的 Lisp 实现之一。因此，现在我们可以完全无缝地调用所有的 Elixir 库。

Andrea Leopardi：我很好奇 Gleam 是否有结构体。Gleam 是一种通过 Rust 编译的静态类型语言，尽管像 Gleam 编译器读取 Rust 并通过代码或 AST 生成 Erlang，但我不知道。但我想知道它是否有结构体，以及我在想它是否...我的意思是，我敢打赌它有，比如记录。知道它们实际上是否可以不标记它们是一件很有趣的事，因为它是一种静态类型语言，你可能可以进行检查。

Francesco Cesarini：这是个好问题。我不知道...

Andrea Leopardi：但我在 Erlang 中注意到的一件非常令人兴奋的事情是，我有时候觉得很难扩展 Erlang VM 本身，这可能是最好的，对吧？像它是一个非常复杂的 VM，有很多...它是一个庞大的 VM，对吧？它是一个非常智能的 VM，具有调度、进程和垃圾回收的许多功能，所以我认为，要使它在任何重要的方式上具有可扩展性可能是很困难的，当你去触及 VM 的深度时。但最近...像 ODP 的发布就令人兴奋。在过去的两三年中，他们添加了很多东西。我认为能够调用 gen servers，我想这是 OTP 25 或 26，最近的版本，能够做到异步调用 gen server，并稍后检查响应。所有这些东西都像是进入了核心，这太棒了，因为它允许我们为自己构建许多这些底层抽象。

Francesco Cesarini：是的，没错。

Andrea Leopardi：我是一个大粉丝。

**Erlang 开发中的挑战**

Francesco Cesarini：如果你看一下实际的 BEAM 本身，我认为在扩展和添加东西到其中最大的挑战是确保它们不会破坏调度程序的软实时特性，这可能是他们最担心的。

Andrea Leopardi：有趣的是，你提到这个，因为像是了解 BEAM 和 Elixir 的人，也许知道这一点，但其中一个...也许是唯一一个共享的函数数据结构，像是纯函数数据结构存在于共享内存中的是二进制，对吧？比如大于 64 字节的二进制，它们进入一个共享内存区域，所以不需要在进程之间移动它们，只需移动引用。这是我所知道的唯一一个完全跨...好吧，现在它们有原子计数器，但...

Francesco Cesarini：ETS 表是另一个具有破坏性操作的例子。

Andrea Leopardi：对。但 ETS 表有点像共享内存错误，对吧？但它被视为不纯的。你可以修改它的状态，对吧？

Francesco Cesarini：正确。

Andrea Leopardi：而且二进制文件的问题不是这样的。你不能修改选定的二进制文件。对我来说很有趣的是，即使是二进制文件，它们非常实用，放在64字节后的独立内存空间，它们也会引起很多问题，因为原来的问题是，像Erlang应用程序中的许多内存泄漏都是由于解析器复制二进制文件或者像这样，拆分大二进制文件而导致的。

Francesco Cesarini：内存碎片化。

Andrea Leopardi：确实如此。像是创建这些小横幅的副本或者像你有引用到永远不会清理或者进程不会死亡或这个或那个二进制文件的内存泄漏一样，然后你有一个内存泄漏因为这样，像二进制文件永远不会被垃圾回收。有趣的是你注意到，即使是结构的一天的构建，它仍然会对用户在某些特定用例中的问题有影响。毕竟，像这样做是困难的。就像BEAM拥有每个进程软件优化的优秀特性和所有这些东西，但是它们很难维护，你知道吗？也许其中的一部分是……

Francesco Cesarini：我认为是的，你已经回答了为什么我认为爱立信必须非常保守地进行改变的问题。我是说，即使是即时编译器，你知道的，至少花了三四年时间才制定完成。进行了广泛的研究，但当它推出时，它使WhatsApp能够减少约30%的服务器需求。这就是WhatsApp发推特感谢爱立信的原因。这反过来又转化为巨大的能源节约，这是我们正在看到的。

Andrea Leopardi：有趣的是Elixir本身，它不处于我们没有为其添加很多东西的位置。像我认为可能是过去几年来更多的东西进入了Erlang，因为Elixir一直非常……Elixir的生态系统扩展得令人难以置信。像所有的机器学习的东西都是疯狂的。像实时视图的东西是疯狂的，但是……

Francesco Cesarini：但这也是积极的一面。Elixir对Erlang的积极影响也是其中一部分。

Andrea Leopardi：因为人们意识到，在Erlang中有很多事情是你必须解决的。像，例如，原子操作。所有这些新增的特性像持久术语，这些都是，像，最近两三年内添加的一些了不起的特性，在Erlang中。你简直无法做到它们。像，像这种共享的持久存储被复制到进程的工具，读取非常快，写入非常痛苦，这太棒了，适用于如此多的用例，但你不能在...像，你必须在VM级别上做它，对吧？你不能在...所以，这些特性在Erlang中弹出来真是太棒了，因为，像，从Elixir中，我们只需免费得到它们，而从...你知道，在Erlang中，你可以随意使用它们。你可以在Gleam中使用它们。这显然是在Erlang中添加特性的好处。

Francesco Cesarini：如果你说，哦，Erlang没有什么事情在发生。不，有很多工作正在进行。你知道，Ericsson正在驱动事物前进做了很棒的工作，但这不是语言的问题，而是在库和虚拟机上花费的努力。

Andrea Leopardi：我认为这有些棘手，因为，像，Erlang团队正在为Erlang做的工作是低级的。像持久术语或原子计数器之类的东西，这些都是低级的东西，通常你需要...我认为99%的用例是为了，像，库作者或OTP本身。

Francesco Cesarini：确实。而用户看不到这一点。

Andrea Leopardi：主要用于gen server调用，像，它们被OTP本身使用，对吧？所以，你不会去...而在Elixir中正在发生的进展和新闻...像，它们似乎更令人兴奋，因为它们更容易。就像，哦，有一个新的机器学习库，让你可以，像，从[不可听见00:18:47]中挑选模型并运行你的机器学习模型。像，这是我可以很容易接触到的东西，可以很容易地到达用户或在live view中添加新功能。它们直接到达用户手中。而相反，Erlang正在做的工作同样重要，同样多产，对吧？像，他们正在做很多事情。只是它可能更深奥一些...

Francesco Cesarini：它更多地是低级的。这是一个你需要完全控制正在发生的事情的低级领域...

Andrea Leopardi：所以，要将它传递给用户更难，你知道？

Francesco Cesarini：这是你需要对正在发生的事情有完全控制的地方。

Andrea Leopardi：但这确实有影响。我是说，对于库来说，我用过计数器，我用过原子操作，我用过新特性，像，它们都很棒。

**Erlang 中的匹配规范**

弗朗切斯科·塞萨里尼：我几周前阅读手册页面时发现的一个令人惊讶的新功能是匹配规范的能力。所以，匹配规范，对于那些不了解的人来说，是一个提供一组...它是一个术语，由一组变量，一组可以对这些变量进行的逻辑操作，以及一组操作组成。因此，它是一个非常简单的程序。它有一个非常非常小的操作和操作集合，最初用于跟踪运行时的本地和全局函数调用。你知道的，我们必须跟踪，并编译代码，并且当满足某些条件时，你希望打开或关闭跟踪或触发跟踪消息。

所以，你知道的，只有当，你知道的，本地调用的第一个参数是用户安德烈亚·莱奥帕尔迪，第二个参数是让他们回家打电话，例如。在这种细粒度水平上，你可以触发一个跟踪消息。如果你知道的，你知道的，那就是你需要进去并解决问题的地方。而且，你知道的，这已经扩展到消息传递，到模式匹配。它只是被扩展到了很多事情。它也适用于ETS表。它在ETS表上已经运行了一段时间，但是，你知道的。所以基本上，你知道的，这个报告，关闭跟踪的功能，有点像，顺序调用到很多其他构造的地方，再次，你知道的，一个进程接收特定消息，你触发，你知道的，你开始跟踪，你知道的？

安德烈亚·莱奥帕尔迪：这是一种非常快速的方法，比如，匹配一些东西并提取信息，这就是为什么它被允许在ETS表中使用。

弗朗切斯科·塞萨里尼：这对于心脏虚弱的人来说并不容易，特别是如果你在现场系统中这样做。但是在一些很难推理和难以找到的错误中。再次强调，Erlang的一个目标是降低运营成本。这减少了系统故障排除所需的时间，找到那根针。

**Elixir编译器跟踪与机器学习的进展**

安德烈亚·莱奥帕尔迪：我认为Elixir在...我没有和它们中的任何一个合作，这就是为什么我允许自己说这个话，但它正在做一个类似于编译器跟踪和，像，代码诊断的惊人工作。真的在最近，我不知道，一年来，像改进Elixir的词法分析器和解析器以及，像，所有的代码编译器。

弗朗切斯科·塞萨里尼：所以，你正在在代码中放钩子。

Andrea Leopardi: 到处都是。所以，基本上，语言服务器变得非常精确地执行任务。比如说，现在 Elixir 能够部分标记那些有语法错误的字符串... 像，所有那些工具，这真的... 像，让我想到那个，因为，像，这真的是在编译层面上非常精确的追踪，对吧？虽然，遗憾的是我没有参与其中，但我会从中受益的，你知道。

Francesco Cesarini: 我想象他们加入错误信息中的行号时，你知道，这...

Andrea Leopardi: 特别是借助这些工具，Elixir 的编译器可以大部分用 Elixir 编写，对吧？然后还有一点点 Erlang，比如说，Elixir 本身的编译器非常高级，但非常容易... 我一直觉得，像，相对于那些需要处理优化和进行多次通过的低级编译器的语言，比如，Elixir 的编译通过更少，所以你有更容易的机会来做这种追踪编译、编译钩子和所有这些用于代码诊断的东西，所以这真的非常有趣。

Francesco Cesarini: 你知道，Elixir 正在进入许多新的垂直领域。我认为其中之一就是机器学习。你能分享一下在这个领域中正在发生的事情吗？

Andrea Leopardi: 我完全没有涉足那个领域，所以总是保持谨慎，但基本上我们已经移植... 比如说，Elixir... 尤其是肖恩·莫里亚蒂一直在主导所有这些工作，但是 Elixir 社区一直在为编译到 GPU 框架的 Elixir 编写 SLs。你知道，就像，我不认识其中任何一个。比如说，我会让自己尴尬，但基本上现在你可以在 Elixir 中做大量操作。从那里开始，就诞生了一整套与 Elixir 相关的机器学习生态系统。对我来说真正有趣的是，这不是... 就我所了解的情况而言，并不一定比 Python 更好，因为它们都编译成了 GPU 指令。最终，它们使用这些 Google 编译器来编译 GPU 指令之类的东西。所以不一定像性能更好，但有趣的事情是，这似乎是第一种语言挑战 Python 在这个领域的主导地位，对吧？

Francesco Cesarini: 嗯，它专注于用户体验和...

Andrea Leopardi: 没错，是的。看起来很不错。

Francesco Cesarini：……就像他们在机器学习中做的那样，他们在 Web 开发的 Phoenix 中降低了入门门槛，让你只需要了解 Elixir 的一部分就能高效地使用 Phoenix，而不用理解底层的任何东西，对吧？很快你就能部署网站。如果他们对机器学习也这样做，我认为这将为一整套新用户打开大门。

Andrea Leopardi：有很多关注点……仍然关注用户体验，就像我们在 Phoenix 中看到的，像我们在 LiveView 中看到的，像所有这些工具中看到的，像我们看到的……

Francesco Cesarini：也在 Nerves 上。

Andrea Leopardi：Nerves，没错。

Francesco Cesarini：所以 Nerves 是用于嵌入式的框架。

Andrea Leopardi：用于嵌入式设备，功能非常强大，非常用户友好，他们也在使用机器学习来进行相同的操作。对我来说，这非常有趣，因为你可以看到人体工学的设计差异，正确吗？就像即使性能可能不会比 Python 更好，因为它们会编译得非常相似……我什么都不知道。我可能在这里说的是完全的谎言，但我认为就是这样的。你知道，事实证明，人体工学的开发者体验和可用性对开发者来说是很重要的，对吧？我觉得这很有意思，这似乎是少数几种挑战 Python 的语言之一，因为 Python 就是机器学习领域的代表，对吧？你写 Python。相反，Elixir 正在推出，比如说，你知道，你也可以用 Elixir 来编写。这非常非常有趣，看看未来会带来什么。我完全不知道。很遗憾我没有参与其中，因为我不知道，我也没有做任何机器学习的事情，但……

Francesco Cesarini：真正让我感兴趣的是在同一内存空间中运行所有内容的能力。所以，你知道，如果你看 Phoenix 并决定使用 Python 作为后端数据库，你知道，你会有 Web 服务器，你会有你的业务逻辑和你的数据库都在同一个内存空间，这使得它极其快速。我的意思是，创建动态页面的速度比读取 Redis 缓存的静态页面更快。所以，如果机器学习也能做到同样的事情，那么那将会很棒。

Andrea Leopardi: 在我的工作中，我们大量使用   Andrea Leopardi：我们在工作中使用很多 ETS 进行缓存和快速响应请求，而且我们有一个用于开始的端点。

Francesco Cesarini：ETS 表是 BEAM 上的 Redis。BEAM 上的 Redis。

Andrea Leopardi：就像半毫秒，它会排队请求，然后我们将其刷新到……

Francesco Cesarini：你分布式了 ETS 表吗？

Andrea Leopardi：有很多工具，非常强大的工具。

**未来愿景与互操作性**

Francesco Cesarini：你对 Erlang、Elixir、Gleam 和整个生态系统的未来有什么看法？

Andrea Leopardi：好问题。我完全不知道。我的梦想就是，它们变得如此互操作，以至于我可以在...一些库中写 Elixir，一些库中写 Gleam，一些库中写 Erlang，并且它们能够像一体化一样工作。这是我的梦想，因为，我认为人们会有偏好。例如，Erlang 是一种更简单的语言，严格来说它的功能更少。像 Gleam 完全不同，它有完全不同的目录结构，你知道，静态类型等等，我想能够根据不同的用例选择使用哪种语言。比如说，我想写一个压缩算法，也许 Gleam 很合适，因为它让我可以使用静态类型并检查所有这些内容。我需要写一些与协议相关的东西。拥有静态类型真是太好了。

我想写一些复杂的东西，我想用 Erlang 来保持功能集的简洁性。我想写一些使用协议的东西。我想能够使用 Elixir。所以我的梦想是拥有一个...也拥有一个单一的共同体。比如说，我已经用 Elixir 写了很多驱动程序，比如 Cassandra。所以，我希望人们可以随意使用它们，你知道吗？因为，像 Cassandra

Francesco Cesarini：完全正确。绝对正确。我认为互操作性是关键。

Andrea Leopardi：这是我的希望。

Francesco Cesarini：我完全同意你的观点。从我的角度来看，我认为像 Erlang、Elixir 和其他 BEAM 语言正在向边缘网络、甚至 IoT 设备上迈进。例如，我认为 Gleam 将会起飞的一个简单原因是它是静态类型的，这使得语言更加安全。

Andrea Leopardi：你可以在 round time 上节省大量时间，因为

**结语**

Francesco Cesarini：确实。你在减少攻击面和外部攻击面。但最棒的是，所有这些语言都是互操作的，彼此依赖。我希望它们能够共同繁荣并继续共同成长。谢谢，Andrea。

Andrea Leopardi：谢谢。

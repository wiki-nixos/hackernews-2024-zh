<!--yml

category: 未分类

date: 2024-05-27 14:30:31

-->

# “编程的终结”将看起来很像编程 | 作者：Ben Kehoe | Medium

> 来源：[https://ben11kehoe.medium.com/the-end-of-programming-will-look-a-lot-like-programming-8b877c8efef8](https://ben11kehoe.medium.com/the-end-of-programming-will-look-a-lot-like-programming-8b877c8efef8)

# “编程的终结”将看起来很像编程

通信ACM有一篇新文章名为“编程的终结”，作者是Matt Welsh。它假设传统程序“将被AI系统替代，这些系统是*训练*而不是*编程*”（原文强调）。威尔士是“Fixie.ai的CEO和联合创始人，这是一家最近成立的初创公司，致力于开发支持软件开发团队的AI能力”。

我普遍对这些广泛的声明持怀疑态度。最重要的是，我认为当人们想象将AI（尤其是LLMs）整合到软件开发（或任何其他流程）中时，他们往往过于乐观。但我想在这里特别关注一些事情。威尔士说“[w]我们正迅速迈向一个计算基础构建块是难以捉摸、神秘和适应性代理的世界。”

我认为这是最不可能的结果。如果你不得不描述那些让用户远离产品的特征，“难以捉摸和神秘的”系统行为会排在高位（通常我们称之为“buggy”）。*特别是*因为在这个世界里，产品背后的人们可能会说，“啊，抱歉，是AI搞的。我们会看看能不能向它解释需要修复什么，也许如果我们问对了它就能修好”。

一般来说，我看到很多AI的主张认为AI将能够为一个人承担整个*任务的责任*，并隐含地认为这个人对任务的*责任*将会像…蒸发一样？比如，如果AI出错了，那不是你的错？但是如果你没有真正的方法来确保任务的正确执行，它们可能会在失败几次后找其他人来完成这个任务。

所以在一个软件仍然需要真正完成其所需功能的世界中，让我们想象一下，如果我们不再需要人类软件开发人员会是什么样子。一个人充当产品经理，向AI口述他们的业务需求，然后AI构建软件。假设结果的软件在很大程度上是功能性的（即，没有低级错误） — 我认为这还有很长的路要走，并且关于它到那时会是什么样子，还有很多可以说的，但那是另一个讨论。

如果你曾经担任过软件开发人员，你就会知道，商业需求通常是模糊的、定义不清的，甚至是用模棱两可的语言写下的相互矛盾的想法。对于这种仅靠AI开发的软件，主要问题在于，它将如何实现产品经理*意图*要做的软件？

我认为有两个一般方向，并非互斥。

第一个是AI必须询问产品经理关于每一个选择和歧义的事项。它必须这样做，因为它足够了解选择和歧义是什么，但却不足以始终猜测出正确答案。这种来回对话将从简单的语言开始，并且对产品经理来说会占用大量时间。随着时间的推移，AI的设计者们将开始提供一些快捷方式，允许在特定表述下输入需求时意味着特定的事物，这样产品经理可以从一开始就明确他们的选择。因此，我们找到了一种用形式化保证表达系统行为的方法。也就是说，我们发明了一种新的编程语言。此时，产品经理已经成为了一名软件开发人员。

另一个方向是AI足够好，可以始终正确猜测出需求中的选择和歧义的正确答案，并且足够了解何时自己没有信心能够正确猜测。要做到这一点，需要大量的人类文化知识，也可能需要对担任产品经理的具体人员有高度的了解。AI正在将业务需求翻译成形式化系统行为需求，并实施它们。在这一点上，AI现在已经是一名软件开发人员。

你可以认为第二个问题与威尔士对“编程终结”的愿景相同，因为你仍在没有正式语言的情况下工作。我说它不同，因为它不像软件开发人员（你*喜欢*与之合作的人）一样“喜怒无常和神秘” —— 它是可靠且一贯的。

我认为第二个方向，即AI作为软件开发人员，还有相当长的路要走，特别是因为文化背景和自我意识是困难的事情。我怀疑你需要AGI来实现它，但这似乎是一个很好的开始。所以，如果你对AGI持乐观态度，你可以希望我们能够尽快实现它。

我很想看到第一个方向被明确地采纳。对于 GitHub Copilot（以及类似系统），我的一个问题是，你仍然拥有生成的代码，并且它没有提供任何路径来确保它给出了正确的实现，尽管你拥有代码的正确性（我认为这也值得单独写一篇文章）。我希望它能识别常见模式并将其形式化，使开发人员可以使用某些简写来表达复杂逻辑，并确信他们得到了他们期望的结果。也许这可以通过现有系统完成，或者可能是一个全新的以 Copilot 为导向的编程语言。

我认为我在这里的主要收获是，当看待 AI 将自动化某些过程时，要看这个过程的真正困难和固有复杂性是什么，以及如果这种复杂性中注入了大量（新的）不确定性，这个过程是否会成功。对于软件开发来说，我认为答案是否定的。这并不意味着 AI 不会成功，而是我们需要更深入地审视自动化在其中的作用是什么，以及如何（以及何时）发挥作用。

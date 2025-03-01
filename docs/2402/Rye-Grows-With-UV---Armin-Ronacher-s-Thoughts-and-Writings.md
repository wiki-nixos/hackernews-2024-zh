<!--yml

category: 未分类

date: 2024-05-29 13:19:51

-->

# Rye Grows With UV | 阿尔敏·罗纳赫尔的思考和著作

> 来源：[https://lucumr.pocoo.org/2024/2/15/rye-grows-with-uv/](https://lucumr.pocoo.org/2024/2/15/rye-grows-with-uv/)

# Rye Grows With UV

2024年2月15日星期四撰写

两周前，我再次提出了关于 [Rye 应该是什么](/2024/2/4/rye-a-vision/) 的问题。有一件事我之前并未公开分享过，那就是自 Rye 存在以来，我也一直在与 [查理·马歇尔](https://twitter.com/charliermarsh/) 探讨 Python 打包和 Python 工具的问题。事实证明，我们对理想的 Python 工具生态有一些共同的想法。这导致了一些非常有趣的来回讨论。长话短说：与 Astral 发布的 [uv](https://github.com/astral-sh/uv) 一起，他们将 [接手 Rye 的管理](https://astral.sh/blog/uv)。详情请继续阅读。

对我来说，Rye 是 Python 工具可能成为的一个激动人心的试验平台。在过去的一年里，我一直在这个试验平台上进行各种实验。通过构建它，我了解了生态系统中缺失的内容以及面临的挑战。到目前为止，我最享受的是来自各方人士的反馈。我想探索 Python 版的 “cargo” 是什么样子，而越来越明显的是，它可能会是什么样子。与此同时，从一开始，我就对 [质疑它的存在](https://github.com/mitsuhiko/rye/discussions/6) 非常明确。

自从我们开始交流以来，我已经能够运行一个实验，即使用 Astral 的 uv 替换 pip-tools。如果你还不熟悉它：uv 今天是 pip-tools 和 venv 的即插即用替代品。其原因非常明确：它比 pip-tools 快得多。它几乎可以瞬间同步一个虚拟环境，而不是花费 5 秒钟。在开发者体验方面，这对影响是巨大的，难以言表。

由于完全无关的原因，Rye 今天已经开始使用一些 Astral 的工具来支持其他功能。如果你调用 rye fmt 和 rye check，它们在后台使用 Astral 的 ruff 来执行。它们速度快，足够专业，并且不需要安装到项目的虚拟环境中。如果你习惯于其他生态系统中的优秀工具，它们很快就会成为明显的选择。因此，目前 Rye 所做的三件事要么已经在选择 Astral 的工具，要么很快将默认选择它们。

这导致了一些讨论，即 Astral 是否继续在 Rye 上工作，并将其发展成为 “Python 的 cargo”。我非常确信应该有这样一个工具，查理来自 Astral 也持有同样观点。我们达成的计划看起来如下：

Rye 会继续作为 Python 工具的可能性的试验平台。我们将项目移交给 Astral 的管理，在这里我们有意愿进一步探索优质用户体验，并以非常自由的态度试验不同的事物。例如，现在安装过程非常快速，在看到是否可以移除手动调用 sync 的需求后，我非常希望尝试这样做。还有许多问题遗留，比如说如何充分利用 [indygreg 构建](https://github.com/indygreg/python-build-standalone/issues) 或 Python环境下锁文件的格式。我也想要深入探索多版本 Python导入系统的可能性。

Rye 将成为一个不同事物的滋养地。随着用户体验变得明显，uv 将从其现在的低层接口转变为具有明确迁移路径的较高层次工具，用户从 Rye 到那个新 uv。

如需在今天尝试使用 Rye 与 uv，可通过 [安装](https://rye-up.com/guide/installation/) 或更新至最新版本并启用实验性 uv 支持来获取：

```
$ rye config --set-bool behavior.use-uv=true 
```

若要了解 more 关于 uv 和 Rye，可访问 GitHub 平台：

您可能还有更多问题，所以我整理了一个基本的常见问答：

**为什么不让 Rye 成为 Python 的货物？**

这在很多方面可能看起来像是一个显而易见的问题。答案很简单：今天的 Rye 不太可能是最终解决方案。从编码层面看，它较为脆弱，是通过拼凑不同的工具构建起来的。这是应急解决方案，用于快速展开设想，供我自己的用途。然而，它对于探索可能的解决方案极为有用。

**Rye 会退休给 uv 吗？**

这不会在今天发生，但我们的目标是这些工具最终能融合为一个。

**您会继续贡献并维护 Rye 吗？**

简短回答：是的。详细回答是，我对自己工具的帮助在过去一年里有些波动。事实上，确实有一段几乎长达数月的休息期，期间 Rye 只有更新了 Python 版本并解决了小问题，并非因为其完美。实际上，问题更多是我意识到 Rye 面临的根本问题难以解决，这可能会对作为侧项目进行干预造成挫败感。因此，我希望能够继续在某个方面参与，但这是个远超我个人范围的项目，我自己没有足够的动力赋予它足够的推动力。

**我会加入 Astral 吗？**

**不会 :)**

**是否有关于 Python 包管理的歌曲？**

谢谢于 AI，现在有。

此条贴文包含标签：[公告](/tags/announcement/)，[python](/tags/python/) 和 [rye](/tags/rye/)

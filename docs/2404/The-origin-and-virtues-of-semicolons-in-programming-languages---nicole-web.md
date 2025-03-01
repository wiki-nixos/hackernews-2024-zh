<!--yml

category: 未分类

date: 2024-05-27 13:12:41

-->

# 编程语言中分号的起源和优点 | nicole@web

> 来源：[https://ntietz.com/blog/researching-why-we-use-semicolons-as-statement-terminators/](https://ntietz.com/blog/researching-why-we-use-semicolons-as-statement-terminators/)

在设计我编程语言Lilac的语法时，我探索了不同的语句终止符选择。`.` 非常吸引人，或者 `!`。最终，我可能会选择使用 `;` 或者显著的空白符，这是“无聊”的选择。

但这让我想问：为什么有那么多语言使用分号作为它们的语句终止符呢？我找到了一些[好读物](https://www.werkema.com/2022/02/10/we-dont-talk-about-semicolons/)，讨论了为什么我们需要语句终止符，但很少有关于分号相对其他选择的具体优点的讨论。

为了了解编程语言中分号的起源，我转向了历史。在早期，几乎没有几种编程语言，因此追溯起源并查看早期语言相对容易。如果我们这样做，我们会发现第一个包含分号作为语句分隔符的语言是[ALGOL 58](https://en.wikipedia.org/wiki/ALGOL_58)。

在ALGOL之前，语言通常使用空白符来标记语句，每个语句都在其自己的行上（或打孔卡上）。ALGOL引入了语句分隔符，使程序员可以更灵活地将多个语句放在一行上，或者将一个语句分布在多行上。不幸的是，当我们深入研究为什么使用分号时，并没有得到很多答案！关于它的原始论文只是描述了它是语句分隔符，但没有解释为什么。

这给我们留下了什么？当然是那些好老旧的推测！

# 推测时间

有几个原因解释为什么我们会选择分号，或者它为什么最终出现在我们的语言中的某个地方。这些都是*推测*，但推理是合理的。

**它是可用的。** 早期计算机的字符集非常有限，分号通常是可用的。一些早期的输入设备是从雷明顿键盘改编而来的，那些键盘（根据我能找到的图片）确实包括分号和冒号。这是有道理的，因为如果你想输入英文文本，偶尔会遇到分号！它并不是最常用的标点符号，但它是有用的。因为它在那里，当我们选择字符有限时，它注定会出现在某个语言中。

**它很方便。** 分号位于现代键盘上的主键行，不需要按Shift键，这部分是为什么它继续被广泛使用的原因之一。而且，它位于主键行使得输入变得非常容易，所以与像`!`这样需要两次按键和伸展的字符相比，你只需用右手小指就能输入一个`;`。说到这里，分号是主要的一个，而更常用的冒号却需要按Shift键，这不是挺奇怪的吗？

**用法与英语中类似。** 英语中分号的作用之一是分隔独立的从句；这些是可以独立存在但又密切相关的句子部分。这与语句分隔符所做的非常相似。更类似的可能是`.`，因为每个语句可以被视为一个句子，但这又引出了偏好分号的另一个原因。

**不太可能冲突。** 如果你使用句号，谦逊的 `.`，如果不小心可能会在解析时遇到困难。正如我最近的朋友对我说的那样，句号是一个如此*高价值*的符号，你必须明智地选择它的用途。在现代语言中，我们用它来访问字段和方法，定义浮点文字量，并用它作为范围运算符和展开运算符。相比之下，分号... 则几乎不用，除了偶尔用来开始注释。

这些共同的理由足以选择分号作为语句分隔符！你可以选择什么代替？浏览所有的候选项 `!@#$%^&*,./;:|-_`，我想不出有哪个更明确更好的选择！我个人的偏好可能是`.`，如果你可以解决解析问题的话，`!` 也可以是非常有趣的选择，但是谦逊的 `;` 似乎因为其稳健的好决策而留了下来，而不仅仅是为了连续性。

关于我在我的编程语言 Lilac 中所做的事情？我还不太确定！分号是一个安全的选择，但其他选择（或者根本不用分号）具有美学吸引力。我很想知道在你的梦想世界中，**你**会选择什么！

* * *

感谢 Mary 对这篇文章的反馈！你说它里面缺少分号。这里有：`;;;;;;;;;;;;;;;;;;;;`。

* * *

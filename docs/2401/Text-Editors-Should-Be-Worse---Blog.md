<!--yml

分类：未分类

日期：2024 年 5 月 27 日 14:26:19

-->

# 文本编辑器应该更糟糕 | 博客

> 来源：[`www.da.vidbuchanan.co.uk/blog/annoying-text-editors.html`](https://www.da.vidbuchanan.co.uk/blog/annoying-text-editors.html)

# 文本编辑器应该更糟糕

*作者：戴维·布坎南，2024 年 1 月 2 日*

这是一篇发泄。你已经被警告了！

我希望文本编辑器更糟糕。具体来说，我希望它们的*默认*行为尽可能接近于你在任何软件中找到的中位数文本输入框，比如普通的 HTML `<textarea>`。更现实的是，我希望有一种配置预设，让我能够选择相同的行为，而不必寻找一千个个别的设置调整。这种选择应该尽可能地全局应用，也许可以作为一个环境变量。

我的理由很简单：我讨厌上下文切换。我希望我的输入序列无论在使用什么软件时都能始终有效。试图在错误的上下文中应用根深蒂固的肌肉记忆，并且无法使其起作用，这可能会极其令人沮丧。

也许你能够从中猜到，像`vim`这样的模态文本编辑器对我没用。请将它们视为本发泄的范围之外——我只关心表面上看起来“正常”的文本编辑器（更广泛地说，是文本输入）。

让我们来看一个具体的例子：输入引号字符串。我通常的输入序列是输入`"` `"` `[左]`，也就是一次输入两个引号，然后将光标移回这两个引号的中间，准备输入字符串本身：`"|"`。这是三个按键，但在我的大脑中它是一个单一的动作，而且在我可能想要使用它的任何地方都有效。

也就是说，在编辑器方面，除了那些试图变得太聪明的编辑器之外，到处都是这种情况。有两种常见的行为，各有各的烦人之处：

+   按下`"`一次会产生`"|"`，完成输入序列后会产生`"|""`。

+   按下`"`一次会产生`"|"`，再按一次会产生`""|`，再按左键会产生`"|"`。

第一个行为显然是不可取的，因为它产生了意外的结果。

第二个产生了正确的结果，但我更加讨厌它！我讨厌它，因为它添加了一个完全多余的“太聪明”行为层，试图抵消第一个行为。也就是说，如果光标已经位于一个`"`字符前面，那么按下`"`键不会插入另一个`"`，而只会将光标移动到另一边。在这个*特定*的场景中，这样做还算合适，但在任何其他情况下，如果你碰巧想在现有的`"`前面输入一个`"`，那么这将会非常令人困惑。这听起来可能有些牵强，但这是 Firefox 的开发者控制台的默认行为，我经常被这种情况所困扰。

我相信有一个设置可以解决这个问题，但我的问题不是 Firefox；我的问题是这些烦人的行为*到处都是*，而不仅仅是与带引号的字符串有关。

当问题“随处可见”时，最佳方法似乎是忍受并习惯它。但我做不到，因为问题不是特定行为；问题是行为的*分歧*。我不可能适应它们的所有！

### 确定问题

我将这种烦恼称为“**自动输入**”。任何未经我输入的字符（或以其他方式选择的）都会被列入我那张调皮清单。这不包括输入*建议*。例如，当输入符号名称时，编辑器可能会提供一个下拉的建议完成列表，我可以使用 tab 键选择加入。这很好，因为如果我忽略建议并继续无意识地输入，一切仍然正常运作。

鼓励文本编辑器变得智能，但这种智能性不应损害基础功能。

### 例外情况

我对自动输入的唯一例外是自动缩进。当我按下回车键时，我希望新行自动填充与上一行相同的前导空格。任何试图比这更聪明的东西，特别是那些试图语言感知的东西，也可能让我恼火。而且，如果缩进是空格，按下退格键应该一次删除一个空格。这是个人偏好问题，但在这篇文章中的其他所有事情也是。

### 解决方案

我懒得认真解决这个问题，除了写这篇发牢骚，但我想提出一个`NO_AUTOINPUT`环境变量的概念。如果在首次运行应用程序时存在该变量，应设置相应的默认设置以最小化自动输入行为。之后，可以根据用户偏好调整设置。

为了统一起见，自动缩进也应使用`NO_AUTOINPUT`禁用。在我需要时，我愿意接受在某些情况下需要重新启用一个设置的附带损害。

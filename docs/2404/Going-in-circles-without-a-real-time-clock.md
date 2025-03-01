<!--yml

类别：未分类

日期：2024-05-27 13:07:52

-->

# 在没有实时时钟的情况下打转

> 来源：[https://rachelbythebay.com/w/2024/04/10/rtc/](https://rachelbythebay.com/w/2024/04/10/rtc/)

## 在没有实时时钟的情况下打转

我有一个关于使用小型Linux盒子时的纸张切口故事。

我的一个站点安装了一台老旧的树莓派，位置不太方便访问。几周前，它突然不允许远程登录。我的简单管理工具仍在运行，并报告有问题，但没有足够的详细信息来找出发生了什么。

我必须连接控制台以找出它对文件系统感到困扰，因为SD卡上显然发生了一些愚蠢的事情。我不知道为什么它不让我登录。在过去，即使磁盘完全损坏，只要缓存中还有足够的东西，你仍然可以进入机器 - inetd + telnetd + login +你的shell，或者sshd +你的shell和（当然）所有这些东西依赖的库。我猜发生了一些事情，方程的某些部分丢失了。如今，随着整个xz事务的发展，有更多的移动部件。无论如何。

所以我重新启动了它，然后继续做我的事情，直到后来我注意到那个东西的时钟已经超过一天了。chrony在运行，所以什么鬼，对吧？chrony实际上说它没有源，所以它只是坐在那里感到难过。

对我来说这有点不合理，因为chrony是其中一个更[聪明](/w/2022/12/21/boot/)的程序，会不断尝试解析源，直到它获取足够的源来进行同步。在我的标准安装中，这意味着它正在尝试使用2.debian.pool.ntp.org。

我试图在盒子上自己解决这个问题。但没用。我在另一个解析器（在另一台盒子上）上查询，结果正常。那么现在怎么办，在chrony不工作的同时，未绑定也不工作？

一点背景：这个盒子曾经在某个时候重新配置，以运行自己的递归缓存解析器，用于本地网络，因为去年我遇到了一些其他问题（*咳咳* [TP-Link](/w/2023/11/17/omada/) *咳咳*）。它还配置为**仅**使用该本地的未绑定进行DNS解析。

这开始串联起一些事实。chrony未能设置时钟，因为无法解析NTP池中的主机。无法解析主机是因为未绑定未工作。但好吧，为什么未绑定不工作呢？

好吧，问题就在这里 - 它*大部分*是。我可以正常解析其他几个域名。只是ntp.org的东西没法解析。

（如果你以前遇到过这种情况，这时你就会开始指着屏幕说。）

那么，在一个时钟超过一天的盒子上，只有一些域名解析不了... 但不是所有的...会是什么原因呢？

是的，大概那时候一切都成了一片混乱。我想他们一定在那个区域上运行了 DNSSEC（或者某个部分），并且它必须对它的某些方面有一个“不早于”的约束。我以前在 SSH 证书的问题上遇到过类似的情况，为什么不是 DNS 呢？

我添加了另一个解析器到 resolv.conf，然后 chrony 开始工作，时间向前推进，然后 unbound 开始解析池，一切恢复正常。

对于“其他一切”，我也指的是 WireGuard。你知道吗，如果你的机器时间严重不同步，它也会停止工作？我不知道它显然包括时间在它的加密中，但还有什么其他解释呢？

回溯一下，让我们谈谈发生了什么，因为大部分责任在我身上。

我有一个运行在 SD 卡上的旧树莓派。它出了问题。我花了大约一天半的时间到达它的状态，这样我就可以开始修复它了。

这台特定的树莓派没有实时时钟。最新的一些（5B）*有*，但是你必须购买一个电池并连接它。默认情况下，它们也处于同样的困境。这意味着当它们启动时，它们会在一段时间内使用一些无意义的时间。我不确定那是多少，因为……

systemd 最近做了一些事情，当它检测到时间值过于久远时，会试图将时钟调回到接近“现在”的某个地方。我怀疑它只是在日志中翻找，抓取最后的时间戳，然后继续运行。通常情况下这是挺好的，因为如果你只是执行了命令重启，差异只有几秒钟，而你的时间同步功能很快就会修复其余部分。

但是，请记住，那台机器坐在那里超过一天没有写入它的“磁盘”（SD 卡），所以它使用了那个时间戳。如果我早点到那里，我想时间不会差那么多，但那并不是一个选项。

时间差太大，导致 unbound 无法解析 ntp.org 的池服务器，进而使 chrony 无法更新时钟…… 这使得 unbound 无法解析池服务器…… 导致……

我自己的配置选择，只将 DNS 解析指向本地主机。

那么，现在怎么办？首先，我给了它第二和第三个解析器，这样特定的 DNS 异常就不会重复了。然后，我明确地给 chrony 一个“peer”源，这是一个附近的主机（另一台树莓派，不幸的是），即使连接到外部的链路出了问题，也可以在紧急情况下帮助它。

将这些小盒子视为便宜的某个问题。它们确实便宜…… 直到它们不是。用 jwz 的一句话来说，如果你的时间没有价值，树莓派只是便宜的。

像往常一样，这篇文章并不是要求“THE ONE”出现。如果你是“THE ONE”，你不会犯错。我们知道。闭嘴，离开。

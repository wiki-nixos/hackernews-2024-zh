<!--yml

类别：未分类

日期：2024-05-29 12:45:13

-->

# 量子纠缠为什么不允许超光速通信的真实原因

> 来源：[https://www.forbes.com/sites/chadorzel/2016/05/04/the-real-reasons-quantum-entanglement-doesnt-allow-faster-than-light-communication/](https://www.forbes.com/sites/chadorzel/2016/05/04/the-real-reasons-quantum-entanglement-doesnt-allow-faster-than-light-communication/)

我的博客同事伊桑·西格尔经常会有读者提问的专栏，本周的专栏涉及到我的领域，回答了一个关于[使用量子纠缠进行超光速通信的问题](http://www.forbes.com/sites/startswithabang/2016/04/30/ask-ethan-can-we-use-quantum-entanglement-to-communicate-faster-than-light/)。正如我在Twitter上开玩笑地说的，伊桑的回答对一个天文学家来说相当不错，但有些地方我不太喜欢。不是因为他给出了错误的答案——他正确指出不能使用纠缠粒子来实现超光速传输消息——而是因为这里涉及到一些微妙和复杂的问题。我以前曾经[写过这个问题](http://www.forbes.com/sites/chadorzel/2015/08/11/how-quantum-randomness-saves-relativity/#2a506baf2ce2)，但现在更有必要深入探讨一下，因为我不喜欢的措辞涉及到一些相当深奥的东西。

<fbs-accordion class="expandable" current="-1">第三方面试验的示意图，测试量子非局域性。从源... [+] 发送的纠缠光子被发送到两个快速开关，将它们导向偏振检测器。这些开关在光子飞行时迅速更改设置，有效地改变了实验的检测器设置。（Chad Orzel提供的图片）</fbs-accordion>

量子纠缠通信的基本情景看起来像这样：两个人，传统上称为**爱丽丝**和**鲍勃**，共享一对可以测量为两种量子态之一的粒子，我们称之为“0”和“1”。这些粒子被准备在一个纠缠态中，爱丽丝的粒子的状态测量与鲍勃的粒子的测量状态相关联，无论它们之间有多远。也就是说，如果爱丽丝在斯凯内克塔迪的正午时分测量她的粒子处于状态1，她知道波特兰的鲍勃不论是在缅因州的波特兰、俄勒冈州的波特兰还是雅文的一颗卫星的波特兰站，他也会测量到他的粒子处于状态1。

这看起来像是在广阔距离上发送信息的完美机制，正如伊桑所指出的：

> 现在来回答奥利维尔的问题：我们能否利用这一特性——量子纠缠——从遥远的星系向我们自己传递信息？答案是肯定的，如果你认为在远处位置进行测量是一种通信的话。但是当你说通信时，通常你想知道一些关于你目的地的信息。例如，你可以保持一个纠缠粒子处于不确定状态，将其送上飞往最近恒星的太空船，并告诉它寻找该恒星适居带内的岩石行星的迹象。如果你看到了，进行一次测量，迫使你手中的粒子处于+1态；如果你没看到，进行一次测量，迫使你手中的粒子处于-1态。

这似乎是一个非常明显的应用，事实上，一群人抓住这一点，将其作为超感知以及其他各种计划的正当理由--我推荐大卫·凯泽的[*《嬉皮士如何拯救物理学》*](http://www.hippiessavedphysics.com/)，讲述了这整个过程的迷人历史。实际上，如果上述情况是可能的--如果你可以以某种方式测量粒子的状态并迫使其产生特定结果--那么你绝对可以通过这种方式发送信息。但你做不到这一点。

<fbs-ad position="inread" progressive="" ad-id="article-0-inread" aria-hidden="true" role="presentation">这就是我对以太解释这种情况的方式有些不太同意的地方。他写道：

> 这是一个精妙的计划，但是有一个问题：只有当你询问一个粒子，“你处于什么状态？”时，纠缠才会起作用。如果你强迫一个纠缠粒子进入特定状态，你将*破坏纠缠*，而在地球上进行的测量完全独立于远处星球上的测量。如果你只是简单地测量远处粒子是+1或-1，那么你在地球上的测量结果会告诉你光年之外的粒子的信息。但是通过*强迫*那个远处粒子为+1或-1，这意味着无论结果如何，你在地球上的粒子有50/50的概率是+1或-1，与光年之外的粒子无关。

这里存在一个微妙的变化，从不可能实现的超光速通信操作转变为一种不同类型的操作，这值得详细说明。也就是说，在最初的陈述中，你“进行一次测量，迫使粒子”处于特定状态，而在第二种情况中，你“强迫一个纠缠粒子进入特定状态”，这破坏了纠缠。尽管如此--一个是测量，另一个是状态变化后的测量。

<fbs-accordion>离子阱量子计算方案的示意图。来自JQI的Monroe组：http://iontrap.umd.edu/</fbs-accordion>

想要清楚地区分这一点，想象一下这个具体实现会有所帮助。因此，想象Alice的粒子是人们经常用来进行量子信息实验的囚禁离子之一，可以处于两种内部状态中的任一种。如果她的粒子起初处于等量部分的“0”和“1”的叠加态，她将如何强制产生一个明确的测量结果，比如说“1”？

答案是执行一个我们用文字描述为“如果你处于状态0，则翻转状态，否则保持不变”的操作。对于囚禁离子系统，这是通过激光驱动从状态0到状态1的转变来完成的，中间还会经过第三种状态（术语称之为“拉曼跃迁”）。如果你仔细选择状态，可以安排使得处于状态0的原子吸收激光并翻转其状态，而处于状态1的原子则完全不与激光发生相互作用。这种选择性吸收是真实囚禁离子实验中区分状态0和1的方法（状态0吸收激光光子然后重新发出光，每秒重复几百万次，在指向离子囚禁点的摄像机上形成明亮的斑点），而其两粒子变体是如何首先纠缠离子的（操作为“如果离子A处于状态1，则翻转离子B的状态”，并给出一个输入状态，其中B肯定处于状态0，而A处于0和1的叠加态）。

如果Alice对她的粒子执行这个操作，实际上并不会以任何方式影响Bob粒子的状态——它仍然处于一个不确定的混合状态，包含0和1。不过，它确实打破了测量结果之间的相关性——Alice的粒子不再处于叠加态，而只处于状态1，因此当Bob最终进行随机选择0或1的测量时，它不一定与Alice的测量结果匹配，而后者保证是1。

Ethan描述的“纠缠的破坏”实际上是一件稍微棘手的事情，需要进行相当特定的操作才能使其生效。有时候你会听到人们断言纠缠是脆弱的，*任何*一个粒子的扰动都会搞乱事情，但那并不是真的。事实上，你可以做很多事情来改变两个粒子之一的状态，而不破坏系统的纠缠特性，只要你跟踪你对它所做的事情，并相应地调整最终的测量结果。（我有一个[博客文章](http://scienceblogs.com/principles/2012/03/14/entanglement-is-not-that-magic/)和一个[arxiv预印本](http://arxiv.org/abs/1208.6186)，更详细地讨论了这个问题...）跟踪所有纠缠态变化方式的不可能性对（我对）“退相干”过程的理解至关重要，这在[(我对)量子物理中“多世界”解释的方式中](http://www.forbes.com/sites/chadorzel/2016/01/05/what-the-many-worlds-interpretation-of-quantum-physics-really-means/#71ae159531fc)扮演了关键角色，这也是我提到这些深层次东西的原因，尽管这篇文章已经写得很长，所以我不会在这里尝试解释。

但至关重要的是，这不是人们讨论使用纠缠进行超光速通信时所说的事情。他们想要的是*强制一个特定结果的测量程序*。也就是说，他们希望Alice使用某种灵异的过程询问她的粒子：“你的状态是什么？”并使其最终变成1，从而瞬间强制Bob的粒子也进入状态1。如果存在这样的过程，你实际上可以利用它来发送消息（对因果性会造成灾难性后果）；幸运的是，[上帝和宇宙玩骰子](http://www.forbes.com/sites/chadorzel/2015/08/11/how-quantum-randomness-saves-relativity/)，量子测量结果是不可避免地随机的。这意味着虽然Alice和Bob最终得到的测量是完全相关的，但信息不会在他们之间传递。他们只能在彼此重新聚集并*比较*列表时看到这种相关性，而他们必须在或低于光速下进行这些操作。

<fbs-accordion>(来源：Graham Barclay/Bloomberg News)</fbs-accordion>

还应该注意，Ethan描述的基于纠缠的通信方式是一种特别幼稚的方式，即使是边缘物理学家也大多不接受。更可信的方案实际上是使用不同的测量基础来发送信息。也就是说，Alice不会“强迫状态为1以发送给Bob一个1”，而是会向她的粒子提出两个不同的问题。如果她想发送给Bob一个1，她会进行一次测量，询问“你是0还是1？”，但如果她想发送一个0，她会进行另一种测量，询问“你是‘0+1’还是‘0-1’？”。后一种操作会将Bob的粒子置于相应的状态中，对于他的测量有50%的机会返回0或1。因此，Bob所要做的就是为每个粒子测量这个概率分布——如果它以100%的概率是0或1，他就知道Alice在发送一个1，如果是50%的概率，则是发送一个0。

那个方案也不起作用，原因更微妙。问题在于，你无法从单次“0”或“1”的测量中确定概率分布，因此Bob需要复制他粒子的状态很多次才能区分Alice的消息。但有一个非常深刻的结果（[凯撒的书](http://www.hippiessavedphysics.com/)声称直接受到这些超光速通信方案启发），称为“无复制定理”，表明这是不可能的——你无法在不知道其内容的情况下制作一个量子态的忠实副本。Bob无法明确确定Alice进行了哪种测量，因此你回到了Alice和Bob各自拥有随机的1和0字符串的情景，只有当他们重新聚在一起并进行比较时才能发现它们完全相关。[量子随机性挽救了局面](http://www.forbes.com/sites/chadorzel/2015/08/11/how-quantum-randomness-saves-relativity/#2a506baf2ce2)。

正如我所说的，整个过程都是微妙而复杂的。不过，最终结果总是一样的：尽管它是物理学中最奇怪和最酷的现象之一，但没有办法利用量子纠缠来实现超光速的信息传输。</fbs-ad>

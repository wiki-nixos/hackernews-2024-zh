<!--yml

category: 未分类

date: 2024-05-27 14:45:55

-->

# Disney 的最新机器人展示出合作的可爱之处 - IEEE Spectrum

> 来源：[https://spectrum.ieee.org/disney-robot-2666681104](https://spectrum.ieee.org/disney-robot-2666681104)

*这是一篇客座文章。本文观点仅代表作者自己的观点，不代表* [IEEE Spectrum](https://spectrum.ieee.org/) *或 IEEE 的立场。*

如果迪士尼丰富的叙事历史教会了我们什么，那就是永远不要低估一个伟大配角的力量。即使配角不是表演的明星，它们也能通过重要的方式提供生命力和能量推动故事的发展。很难想象没有精灵的阿拉丁，或没有小叮当的彼得·潘。

在 [机器人技术](https://spectrum.ieee.org/topic/robotics/) 领域，然而，独立行动的机器人比比皆是。即使使用多个机器人，它们通常也是并行操作的。其中一个关键原因是，大多数机器人的设计使得与其他机器人直接协作变得困难。刚性、强力的机器人更容易重复和控制，但这些设计对于与其他机器人接触时产生的不完美和不匹配的容忍度很低。

让机器人共同工作，尤其是如果它们具有互补的技能集，可以在娱乐机器人领域开辟一些令人兴奋的机会。在华特·迪士尼创意工程部门，我们的研发团队一直在研究机器人之间的协作理念，我们本周在上海展示了这种合作的成果，当一个小毛绒角色打断了首次在 [*动物方城市*](https://disneyparks.disney.go.com/blog/2023/10/zootopia-opening-dec-20-2023-at-shanghai-disney-resort/) 的开场时。

* * *

我们最新的机器人角色，[杜克·韦斯尔顿](https://zootopia.fandom.com/wiki/Duke_Weaselton)，去年十二月首次登台于上海迪士尼度假区，推着一个紫色亭子，并播放流行音乐。正如下面的视频所示，观众看到他跳上亭子并试图与迪士尼体验主席乔什·达马罗博弈，寻求新工作和一些新的好处。当然，经过一番讨价还价后，杜克由团队成员理查德·兰登和路易斯·兰比温和地护送离开了舞台。

最初可能不明显的是，刚才您看到的画面不是由一个机器人实现的，而是由两个机器人。杜克·韦斯尔顿是表演的明星，但他动态的动作离不开自己的独立驱动式机器人亭子。虽然这两个机器人大不相同，但通过作为一个系统共同工作，它们能够完成任何一个单独无法完成的事情。

角色和售货亭将两种非常不同的运动形式结合在一起，并在这个过程中创造出比各自部分更多的东西。角色是一种富有表现力的两足机器人，其动画动作风格夸张而生动。看起来很棒，但并不是为了强大可靠的运动而优化。与此同时，售货亭是一个简单的轮式系统，其行为高度可预测。尽管这对于可靠性来说很好，但这意味着它本身不太可能让你感到惊讶。但当我们将这两个机器人结合在一起时，我们得到了两全其美的结果。角色机器人可以带来疯狂、不受约束的能量和兴奋，因为它在售货亭上下、旁边弹跳时，售货亭本身确保两个机器人可靠地到达他们的目的地。

哈鲁特·贾查夫金、苏菲·鲍伊、托尼·多希、比尔·韦斯特、马塞拉·德·洛斯里奥斯、鲍勃·米歇尔和摩根·波普。

这两个机器人之间的协作得以实现，是因为它们的设计是坚固而灵活的，并且其运动可以容忍大量的不确定性，同时仍然提供引人入胜的表演。这是从此前在SXSW舞台上跌倒的一款机器人中吸取的教训的直接结果，[这款机器人在今年早些时候的SXSW上摔倒](https://spectrum.ieee.org/disney-robot-indestructibles)。我们的基本见解是，一款小巧轻便的机器人可以出人意料地坚固，而这种坚固性使得在设计和执行表演时拥有新的创意自由度。

这种高韧性也使得机器人之间的协作更加容易。因为这种特性使得角色机器人十分坚固，同时其电机和关节具有一定的灵活性，因此即使在位置和姿态上存在小错误，也不会像对传统机器人那样造成大问题。角色可以倚靠电动售货亭，制造出其推动它穿过舞台的假象。然后售货亭使用绞盘将角色吊升到一个平台上，电磁铁帮助稳定其脚部。实质上，售货亭弥补了杜克本人无法攀爬并且可能在没有固定脚部的情况下有些摇摆的事实。总体结果是一个自由活动的两足机器人，其移动方式自然而引人入胜，但并不需要特别复杂的控制或高度精确的机械设计。以下是我们开发这些系统的幕后揭秘：

迪士尼梦想工程

为了编程杜克的动作，我们的团队使用了最初为[SXSW演示](https://spectrum.ieee.org/disney-robot-indestructibles)开发的动画流程，设计师可以手动调整机器人的姿势以创建新的动作。此后，我们开发了一个界面，也可以从传统动画软件工具中获取动作。动作可以根据机器人的实际物理约束进行调整，这些信息可以发送回动画工具。在开发动画时，保持售货亭和角色之间的紧密同步非常关键。该系统设计使得两个机器人的动作始终协调一致，同时支持灵活地对个别机器人或机器人的个别部位（如嘴和眼睛）进行动画设置。

在过去的九个月中，我们探索了几种不同的协作运动方法。下面的GIF展示了一些早期尝试，如骑三轮车、滑板和推箱子。在每种情况下，想法是一个机器人角色最终与另一个机器人系统合作，以稳定且可重复的方式展现角色的动作。

迪士尼希望他们的朱迪·霍普斯机器人很快能够借助机器人三轮车、箱子或滑板等来实现新型的运动方式。摩根·波普

主管该项目的首席R&D设计师托尼·多伊表示，杜克·维斯尔顿和他的售货亭的这次演示只是个开始。“今天我们展示的是迈向更大愿景的重要一步。这个项目为能够以出人意料且情感满足的方式相互作用的机器人铺平了道路。今天是一个角色和一个售货亭，但我们希望未来有多个角色可以相互交流，并与我们的客人互动。”

Walt Disney Imagineering R&D正在探索一种多方面的开发策略，用于我们的机器人角色。像杜克·维斯尔顿这样的吸引人物展示着快速原型化完整体验，使用即时可用的技术。与此同时，我们的研究团队正在开发新技术和能力，这些技术成为提升现有体验、设计和交付全新节目的基础。由莫里茨·贝克尔领导的机器人团队分享了一个这样的基础——以高度表现力和风格化的机器人行走角色体现——[在十月的IROS](https://spectrum.ieee.org/disney-robot)。那里展示的能力最终可以用来帮助像杜克·维斯尔顿这样的机器人更加灵活、更加可靠、更加壮观地表演。

“真实的角色演示非常有用，因为它们帮助我们确定哪些工具对我们开发最有价值，” Bächer 解释道。“最终，我们的目标是创建能够使我们的团队快速高效地制作和交付这些节目的工具。”这与杜克·韦瑟尔顿秀时刻背后的基本技术理念息息相关——合作至关重要！

来自您的站点文章

相关网页文章

<!--yml

category: 未分类

date: 2024-05-27 14:55:05

-->

# 采访：Linus Torvalds | Linux Journal

> 来源：[https://www.linuxjournal.com/article/3655](https://www.linuxjournal.com/article/3655)

在8月11日，我在加州圣何塞参加LinuxWorld Expo时，有幸与Linus Torvalds共进午餐。虽然我们之前有过简短的见面，但这是我第一次与他面对面交谈，而不是通过电子邮件。他是一个非常和蔼的年轻人——非常自信和口才流利。在前一天晚上的主题演讲中，他展现了同样的沉稳气场，从容地回答问题，这种自信来自于对自己专业的了解。午餐时，他坦言对公开演讲感到紧张——尽管完全看不出来——所以我猜他也是个普通人！我避开了常规话题（Linux和Transmeta），希望给你展示一个真实的Linus的形象。以下是我们的对话内容。

**玛吉**：让我们从头开始。你在哪里出生？什么时候？

**Linus**：芬兰赫尔辛基，1969年12月28日。

**玛吉**：简直是个圣诞生日呢！

**Linus**：是的，如果你喜欢收礼物，那不是一个好时机。你总是会得到组合礼物，但对我来说还算不错。今天是个好日子。在芬兰，这一天被称为“无过错的孩子之日”——不完全是“无过错”，更像是“几乎完美”。

**玛吉**：看来是真的。你是在赫尔辛基长大的，还是四处流动？

**Linus**：我一直生活在赫尔辛基，直到两年半前。在赫尔辛基，我可以算是典型的城市孩子。这不是个大城市——只有50万人口。我基本上一直住在赫尔辛基市中心。如果大自然跳出来咬我，我都认不出来。

**玛吉**：哦，你从未做过户外活动——去过山区或者……？

**Linus**：不，我从未做过户外活动。搬到硅谷就像搬到郊区一样——完全不同。我习惯于住在五层楼的建筑里。在这里，拥有一个有后院的小房子确实感觉很乡村。

**玛吉**：嗯，这里的人们不认为住在房子里是乡村生活。

**Linus**：不，我的意思是人们对生活的看法非常不同。美国的城市更加分散，因为人们想住在自己的房子里。欧洲国家历史更悠久；大多数人住在——不是摩天大楼，但确实是有五、六层甚至七层的建筑里。

**玛吉**：兄弟姐妹呢？

**Linus**：我有一个比我小16个月的妹妹，还有一个比我小9岁的同父异母的弟弟——他现在20岁。其实除此之外，我还有两个比我大女儿更小的同父异母的弟弟。我爸爸非常有生命力——比他好的生命力都不好！我能说什么呢？

**玛吉**：哦，这样也会发生。你的童年相对快乐吗？

**Linus**: 我觉得我的童年很快乐，相当正常。我小时候父母离异了。我和我妈妈还有我爷爷奶奶住在一起。我妈妈是一个职业妈妈，所以我经常在我祖父母家里度过很多时间——相当正常的岁月。也许从这样的家庭出来，你会变得相当独立。

**Margie**: 可能是吧。你父母都是新闻工作者，对吧？

**Linus**: 我整个家庭都是新闻工作者。每个人——我妈妈、我爸爸、我姐姐都进入了新闻行业，还有我叔叔、我爸爸那边的爷爷——每个人都是。

**Margie**: 哇——这对你有什么影响？

**Linus**: 宗教没什么区别，因为他们都是不同类型的新闻工作者。我妈妈是翻译家；她不是那种外出寻找新闻的记者。她在芬兰报纸做翻译和新闻制图。我爸爸是更“出风头”的广播新闻记者，所以当车臣战争进行时他非常兴奋。所以他去了那里，还得穿防弹衣——他就是那种人——记住，阳刚。我叔叔在芬兰电视台工作。我爷爷曾经是一家报纸的总编辑。总体来说，整个家庭有一种书本学习的氛围。学好英语和读书是被认为是很重要的。所以去大学之类的事情对我来说非常自然。

**Margie**: 它让你更关心政治吗？你对政治感兴趣吗？

**Linus**: 我对政治完全不感兴趣。可能因为——我不知道——家里人比较政治化，所以我可能通过对政治的不关注来做出反应。我对此不太感兴趣。在美国政治意义上来说，我比较偏左。我比较自由主义，但同时，我真的不想涉足政治。我父母在六十年代是比较激进的人——他们现在平静了很多！他们现在不再关心政治，但我是在一个相当政治化的环境中长大的。

**Margie**: 六十年代基本上是这样的。

**Linus**: 我还会遇到人们说，“哦，我认识你爸爸！我记得你还在家里的厨房桌子底下爬来爬去，那时候他们在那里开学生会议！”或者其他事情。

**Margie**: 宗教呢？

**Linus**: 嗯，完全不信仰——无神论者。我发现人们似乎认为宗教带来了道德和对自然的欣赏。我实际上认为它削弱了这两者。它给了人们借口说，“哦，自然就是创造的”，所以创造的行为被看作是一种奇迹。我欣赏这个事实，“哇，这样的事情竟然能发生”。我认为我们可以在没有宗教介入的情况下拥有道德观念，特别是有很多坏事是由于特定形式的宗教带来的。我实际上害怕组织化的宗教，因为它通常导致权力的滥用。

**Margie**: 就像圣战一样？

**Linus**: 是的，我觉得这种宗教告诉你什么能做什么不能做的东西有点让人不舒服。天主教就是这种不许可性的例子，我觉得如果你信仰有组织的宗教，很容易陷入其中。宗教是一个非常奇怪的领域。在芬兰，没人在乎这些。芬兰有很多宗教信仰者，但这不是一个政治问题。在这里，宗教已经被政治化了，所以你会看到新闻里的边缘人士。然后人们因为它具有政治含义而害怕谈论它，但这在大多数欧洲国家通常不是真的。宗教是个人的事情，但对其他事情没有影响。我觉得应该这样做。

**Margie**: 是的，我们是为了保持两者分开而成立的。然后道德大多数发现了他们有多么庞大的选民基础，然后……

**Linus**: 是的，很讽刺的是，在许多欧洲国家实际上国家和国家宗教之间有一种法律约束。但在实际生活中，宗教与日常生活毫不相关。也许会有给教会的税，但仅此而已。他们没有任何政治权力。

**Margie**: 这里称为什一献，不是税金。

**Linus**: 实际上，在芬兰他们称之为税金——你要给教会交税。如果你是教会的成员，你要给教会交2%的税。这是教会和国家之间的法律约束。除此之外，它们是完全分开的。在美国，教会和国家声称彼此分离得很彻底，但你仍然能看到教会在政治上有很大的影响力。

**Margie**: 那你小时候是害羞还是外向呢？

**Linus**: 我是绝对的极客——没有社交技巧。

**Margie**: 一个也没有，是吗？

**Linus**: 没有！

**Margie**: 不受女孩欢迎？

**Linus**: 不，我不能说我是。我完全是个书呆子。我不是不受欢迎，也不是孤独或者不友好什么的。但我绝对不是众人皆知的那种人之一。

**Margie**: 那你喜欢上学吗？

**Linus**: 是的，我喜欢。我也喜欢社交的部分。尤其是在大学期间，我的学业可能不如成为学生组织一员和参加派对之类的社交重要。但特别是在大学之前，我有我的东西，那就是电脑，那是我所做的。

**Margie**: 你是什么时候开始使用电脑的？

**Linus**: 我大概十一二岁的时候开始。相当早了，那时候没有电脑课，因为80年代初很少有人有电脑。我不知道，在这里可能也是一样。如果你学电脑，大多是自学。也许有一两个人和我一样在一个班上用电脑，每周见一次面交流心得什么的。我从来不是BBS或者上网什么的迷。

**Margie**: 那么你那么早怎么得到电脑的？

**Linus**: 我母亲那边的祖父拥有一辆摩托车。他是赫尔辛基大学的统计学教授。他买电脑是因为对他来说它是一个可编程的计算器。这是一台家用电脑，并不是很强大，但与当时的计算器相比，它领先了几个时代。他自己写程序，我帮了点小忙。虽然我并没有太大帮助，但他喜欢有我在身边。我输入程序，做一些类似的事情。他可能希望我学习，但当时我并没有意识到。我也在玩游戏。他对游戏不感兴趣。我读电脑随附的手册，做一些简单的事情：输入示例程序并进行扩展，就像人们常做的那样。并不是像，第一天看到电脑我就立即爱上了。更像是，多年来，我只是花了很多时间在电脑上，直到显而易见它是我的爱好。

**Margie**

: 你小时候有摩托车吗？

**Linus**: 不，我没有摩托车。我有辆自行车。现在也没有摩托车。我对那些该死的东西感到害怕。

**Margie**: 你是吗？

**Linus**: 嗯，你在上面感觉如此无保护。它们非常难以控制。就像你学习骑自行车一样，你也必须学会使用摩托车，而我还没有学会。

在乡下摩托车非常流行。那是人们出行的方式。在你拿到驾照之前，你仍然可以骑摩托车。但我一直住在赫尔辛基市中心的绝对中心地带，所以我可以步行到任何地方，乘坐公共交通等等。所以我从未对汽车或摩托车感兴趣，直到搬到这里之前我从未拥有过汽车。在赫尔辛基的大多数地方，一辆车带来的麻烦远远超过了它的价值。除非你因为某些特定原因需要它，比如搬运孩子。如果那时我们有孩子，我们可能会买辆车。

**Margie**: 关于体育呢？你踢足球吗？

**Linus**: 不，我没有。我在运动方面并不算糟糕，但我从未觉得它有趣。我曾经打篮球，这有点荒谬，因为我总是班里最矮的人之一。无论我是多高——5英尺8英寸——我都不会成为篮球运动员！我基本上是因为我爸爸认为我应该参加一项运动而打篮球的。

**Margie**: 哦，又是男子气概的问题...

**Linus**: 是的，他更像是一个行动派。他也非常聪明。事实上，他是我认识的更聪明的人之一，但他有他的怪癖。我从来不是什么体育迷。

**Margie**: 关于音乐呢？

**Linus**: 一样的。我现在听音乐的方式还是打开一个基本上都是经典摇滚的电台。

**Margie**: 你认为什么是经典摇滚？

**Linus**: 60年代，披头士，随便。也许披头士有点早了，不过算是经典摇滚的边缘。

**Margie**: 你上哪所大学了？

**林纳斯**：赫尔辛基大学。有两所：一所是赫尔辛基理工大学，实际上并不在赫尔辛基市内，而是在市外边境。然后有真正的赫尔辛基大学，是那种古老的、欧洲风格的大学，你可以学到很多像哲学和语言之类的课程。他们也有一个技术系，但不涉及技术。例如，计算机科学真的是计算机*科学*——它讨论复杂性分析和类似的东西。我去了真正的大学，所以我经历了所有的复杂性分析，NT完全性是什么以及球面部分。那有点有趣，人们总是想知道为什么我不去赫尔辛基理工大学，那里更加工程导向。我只是喜欢去——我也喜欢数学，所以我在赫尔辛基大学找到了自己的位置，同时，我有Linux作为一个副项目——实用的一面。

**玛吉**：你什么时候开始开发Linux？

**林纳斯**：1991年春天——八年半前。在那之前的秋季学期，我上了一门UNIX和C语言课程。我第一次真正接触UNIX是在1990年秋季，当时我在赫尔辛基大学上UNIX课程。实际上，那是赫尔辛基大学有史以来第一次开设的UNIX课程，因为之前那里是VAX和VMS的地方。他们刚刚得到一台UNIX机器来试验这个新鲜事物，结果非常成功。几年内，他们将所有系统都转换到了UNIX上。但是那台第一台机器用于这个小小的UNIX和C课程，我立刻感觉到这正是我想要的东西。这有意义。后来我买了一台个人电脑，我想在上面运行UNIX，剩下的就是历史了。

**玛吉**：有没有特别影响你的教授？

**林纳斯**：有很多人对我有很大的影响，但没有一个人是真正基础的。我是说，除了我爷爷，我通常都是做我自己的事情。我不建议别人效仿我的学习方法，因为它并不是很有条理。基本上我花了八年时间才拿到学位。

**玛吉**：这是一个硕士学位，对吧？

**林纳斯**：这是我的硕士学位，但人们不应该花八年时间才能获得一个硕士学位！但是，我的学习方式！

**玛吉**：所以你玩得很开心，对吧？

**林纳斯**：嗯，是的。

**玛吉**：社交生活也很重要。

**Linus**：是的，在芬兰，你可以慢慢来，因为大学基本是免费的，政府还给你补助来读书。所以你实际上可以靠这些补助生活，尽管生活条件不会很好。我也在大学教书，一开始是助教，然后是初级研究助理，再后来是初级研究员——慢慢地向上升职。到我开始拿到学位时，我早就意识到我其实不喜欢写论文。我写论文的时候很困难，我决定不能永远待在大学里。因为如果你不喜欢写论文，你真的不想留在大学里。所以，那时我说，“好吧”，开始考虑其他事情，结果就是搬到了美国。

**玛吉**：嗯，早期对计算机有兴趣会给你提供很多选择。

**Linus**：嗯，即使在两年半前Linux刚刚开始的时候——当时它不像现在这样出名；它只在技术圈子里知名——我也有许多有趣的工作机会。大多数从芬兰大学毕业的人去工作，都是从小事做起——诺基亚在芬兰显然是非常大的雇主。我有选择去一些非常有趣和令人兴奋的地方。

**玛吉**：你是如何决定加入Transmeta的？

**Linus**：时机很好。他们在我签署保密协议后把我飞过来，并给我进行了一次参观。第一天结束后，我只是觉得这些人太疯狂了——他们的想法太激进了。然后我回到酒店，基本上是在这个问题上睡了一觉。到第二天来参加面试时，我已经决定，“嘿，如果我想要为一个做一些令人兴奋的事情的地方工作，那它最好是有点疯狂的！”没有其他地方在做像Transmeta那样令人兴奋的事情。在Transmeta，我有这样的感觉，“好吧，这是一家在全世界其他地方都没有的公司在做的事情。”而且我现在仍然这么认为。尽管我不能说*是什么*，但Transmeta仍然是一家很好的公司。你会觉得，嘿，我们在做一些如果成功的话，会产生很大影响的事情。

**玛吉**：你和Tove在哪里认识的？

**Linus**：我们在大学里认识的；她已经是一个幼儿园老师了，那是她的真实工作。她有一个儿童保育的学位，一个学士学位。她并不一定想一辈子都做幼儿园老师，所以她也在做其他的事情。计算机科学实际上只是一个有趣的副业，所以我们在计算机科学大学相遇了。我们是这样认识的——不是很浪漫——没有在墨西哥湾进行异国巡航。

**玛吉**：啊。你什么时候遇见她的？

**Linus**：大约六年前。那是在Linux开始之后，但在它对其他人产生影响之前。

**玛吉**：一见钟情吗？

**Linus**：不。

**玛吉**：通常情况下不会吧，对吧？我记得好像听说过她是某种武术冠军之类的事情？

**Linus**: 是的，连续六年她都是芬兰空手道冠军，但后来她基本上停止了练习。她喜欢做形体，也参加一些比赛，但形体其实就是正确、精准地按照空手道的形式进行表演，以正确的速度和精确度。她参加的比赛基本上展示了她的能力。

**Margie**: 孩子们呢？告诉我们她们的名字和年龄吧。

**Linus**: Patricia是大的一个。她在我们搬来芬兰的两个月前出生的，所以她现在两岁零八个月。Daniella是小的一个；她十五个月大。她在这里出生的。

**Margie**: 她们非常漂亮而且举止端正！

**Linus**: 是的！她们非常乖巧，而且习惯了旅行。部分原因是我们搬到了这里，没有祖父母照顾她们，所以无论我们去哪里，她们都跟着我们。她们习惯与人们在一起外出和在餐馆里待着。

**Margie**: 你们打算再要孩子吗？

**Linus**: 我妻子……她还在劝说我。我已经做好迎接第三个孩子的准备了。我喜欢孩子们。第二个和第三个之间的时间会比前两个之间长一些。我想我们应该再等一段时间。有两个小孩子的生活已经相当忙碌了。

**Margie**: Tove想要个男孩吗？

**Linus**: 她总是提到要个男孩，我敢打赌，如果她再生个女孩，她会开始谈论第四个了！

**Margie**: 那你最好准备好那个男孩了！

**Linus**: 我对两个女孩很满意！也许等她们长大些，我就准备好再要一个了。

**Margie**: 对孩子们的学校有什么打算吗？你们打算留在美国让他们上学吗？

**Linus**: 嗯，这曾经是我们之间的一个主要担忧。我们见过一些奇怪的事情。Tove当时正在找幼儿园，因为在美国这里开始的很早。我仔细查看了她带回来的一份文件，发现提到了L·Ron Hubbard。我开始询问周围关于这所学校的情况，结果发现它们是一所科学教派学校，在他们的文献中根本没有提到他们与科学教派有关联。这让我有点紧张。我不想因为错误而把我的孩子送到一个科学教派学校。我们已经把Patricia注册在了当地名声很好的学校，看看会怎么样。她实际上今年开始上幼儿园了。如果一切顺利，我们就不会像过去那样太担心学校的问题了。

在这方面，美国和芬兰的差距真的很大。在芬兰，没人担心学校，甚至没人会考虑，因为显而易见你会去公立学校。不送孩子去公立学校的人有特别的理由，比如孩子需要特殊关注。有一些专门语言等方面的私立学校，但一般人不会选择那些。在这里，你必须认真考虑这个问题。有很多糟糕的学校和很多非常好的学校，这更像是一个决策。正是这种差异让我们感到紧张，所以我们会看看。

**Margie**: 那么你在美国很开心吗？

**Linus**: 我们现在更幸福。我妻子在这里也很开心，尽管一开始并不是这样。她有一个非常亲密的家庭，所以我们的电话费曾经非常可怕。我们喜欢这个地区。从纯技术角度来说，我也喜欢这里，还有天气之类的事情。我妻子也逐渐喜欢上了这里。所以我们会看看。我们肯定会在这里再呆几年，除非移民局把我们赶走。

**Margie**: 嗯，我怀疑这个！

**Linus**: 嗯，我不知道。

**Margie**: 只要你有稳定的工作，我以为他们会让你自己待着。

**Linus**: 他们有一些规定，比如我们的签证是三年一次可续签的。同时，我们正在努力申请绿卡，现在应该很接近了，但是“移民局的很接近”可能意味着一周或四年。

这个地区是整个美国最糟糕的地方。移民局简直是完全堵塞了。他们有些案件的文件都丢了，因为他们丢了这些文件，等了一两年的人又得重新开始，移民局说：“我其实不了解你。”

**Margie**: 你们平时做什么好玩的？

**Linus**: 通常我们很忙，所以平时我们只是带孩子们去附近的公园。周末的时候，我们有时会去附近的一个小动物园；我们是会员，所以可以免费入场。有时我们会去自然保护区溜达。大部分时间，我们就是呆在家里，去购物之类的。

**Margie**: 你连去看电影都不去吗？

**Linus**: 我们已经两年半没去看电影了！

**Margie**: 这是因为孩子们的缘故吗？

**Linus**: 这都是因为孩子们。他们现在正好到了一个年龄，我们开始说，“嘿，总有一天我们可以去看孩子的电影。”

**Margie**: 他们有保姆，对吧？

**Linus**: 我们有几个保姆，有时候可以出去玩。但是我们没有住得近的祖父母，可以在最后一分钟带孩子们出去玩个晚上。相反，我们必须提前一周决定下个星期五出去，找保姆—基本上，这种事几乎不会发生。

**Margie**: 关于名气呢？你看起来处理得很好。

**Linus**: 这对我影响不大。

**Margie**: 你不常被打扰吗？

**Linus**: 不。我只在会议期间才会注意到这一点。否则，一年可能只有三四次——除此之外，根本不会发生。

**Margie**: 那像我这样的人一直在打扰你做采访怎么样？

**Linus**: 我的电子邮箱完全是个灾区！多年来，每天的邮件从大约十封增长到一百封。我已经习惯了。这可能很痛苦；假期一周意味着你要事先知道，当你回来时，你将不得不花两天时间只是读邮件。

**Margie**: 你会把所有邮件都读一遍吗？

**Linus**: 不，但我会试着浏览大部分邮件。我更善于处理技术性邮件而不是非技术性邮件。技术性邮件简单多了！你可以浏览一下就知道重要与否，要么放一边要么当场处理，这是一个相对直接的决定。但对于非技术性邮件，你会想，“嗯...我该怎么办？”你没有时间当场决定处理，所以你就把它放一边然后忘记了。

**Margie**: 我觉得那可能是我收到的唯一类型的邮件——那些需要决策的邮件。社区中的很多人把你视为英雄、榜样。你的榜样是谁？

**Linus**: 我没有偶像。我从来没有过任何少年偶像或者类似的东西。我的选择可能只有我爷爷了。而且也许更多的是科学家类型的人，比如爱因斯坦，像他那样的人。我小时候觉得量子物理是最有趣的事情。但那时候，这并不是很个人化——并不是只有一个人。

**Margie**: 你爷爷对你有什么影响？

**Linus**: 我不知道；他让我对数学和计算机产生了兴趣。他是那种“心不在焉的教授”类型的人，所以即使他在那里，他的心思也不一定在那里！但同时，他可能是我最亲近的人之一。他在我15岁时去世了。他主要在我上学早期年代出现，而不是后来。

**Margie**: 好吧，有几个愚蠢的问题。如果你可以拥有世界上任何一辆车，你会选什么？

**Linus**: 天啊！我们实际上正在考虑买一辆车，并且已经选择了一辆面包车。是的，它不是那种性感的跑车。我们有很多朋友和家人从芬兰过来，每次我们去某个地方，我们都必须开两辆车，这真是个烦事。所以我们正在成为一个“真正的美国家庭”，我们将拥有一辆面包车。但这不是你想要的答案！

**Margie**: 没关系！你更想要一辆保时捷吗？

**Linus**: 不，我从来不喜欢那种肌肉车 — 柯尔维特，我不喜欢。我觉得那些很无趣 — 玩具车。我喜欢迈阿密，但它太小了；然而，宝马Z3 — 那种车 — 我喜欢。但是当你有两个孩子时，这种车实在太不实用了。我们考虑过也许买辆敞篷车。我们搬到这里的时候，没有考虑过这一点，但实际上在加利福尼亚大部分时间都是合理的。但无论如何我们都得买四座的，所以即使那样，它也不会是那种真正“有趣”的车；它会是那种实用的车。

**Margie**: 运动型多功能车有天窗吗？

**Linus**: 或许天窗可以，但不是敞篷车！

**Margie**: 您最喜欢的颜色是什么？

**Linus**: 我小时候是蓝色的 — 经典的男孩颜色。我想现在是黄色的。黄色很难把握，好吗？你可以做得太浅，看起来就像尿黄色。或者你可以做得太深，它就会变得太橙色，所以你必须小心 — 蓝色更安全。

**Margie**: 您想给我们的读者传达什么信息？

**Linus**: Linux起初并不是为了传递给大众的信息。不像理查德·斯托曼，我真的没有什么信息要传递。他有一个可以无休止谈论的信息。我只是一个工程师。让我们看看：做事情要做好！用心去做！我还能想出什么其他策略呢...？

**Margie**: 好的，谢谢您抽出时间和我交谈。

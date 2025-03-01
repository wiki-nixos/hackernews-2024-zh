<!--yml

category: 未分类

date: 2024-05-27 13:13:36

-->

# **能够熔化钢铁的微型超亮激光器** - IEEE Spectrum

> 来源：[https://spectrum.ieee.org/pcsel](https://spectrum.ieee.org/pcsel)

**2016年，日本**政府宣布了一个新型社会的计划。提议解释说，人类文明从狩猎采集者开始，经历了农业和工业阶段，正迅速接近信息时代的尾声。正如时任首相安倍晋三所说，“我们正在见证第五章的开启。”

此章节名为[Society 5.0](https://www8.cao.go.jp/cstp/english/society5_0/index.html)，将会出现按需制造的商品和机器人[看护者](https://spectrum.ieee.org/stretch-assistive-robot)，[出租车](https://spectrum.ieee.org/tag/autonomous-vehicles)，以及拖拉机。其中许多将使其成为可能的创新，如[人工智能](https://spectrum.ieee.org/topic/artificial-intelligence/)，可能是显而易见的。但有一个关键技术很容易被忽视：[激光器](https://spectrum.ieee.org/tag/lasers)。

Society 5.0时代的激光器需要满足几个标准。它们必须足够小，以适应日常设备内部。它们必须低成本，以便普通金属工人或汽车买家负担得起，这意味着它们必须易于制造和能源高效利用。由于这个黎明时代将关注大规模定制（而不是大规模生产），它们必须具有高度可控性和适应性。

半导体激光器看似是完美的候选者，但有一个致命缺陷：它们太暗了。激光亮度——定义为单位面积单位固体角内的光学功率——是衡量光线能够在激光器出口时集中的强度以及在远离时发散的狭窄程度的一种方式。材料加工的亮度阈值——切割、焊接、钻孔——约为每平方厘米每立体角1千兆瓦（GW/cm²/sr）。然而，即使是最亮的商用半导体激光器的亮度也远远低于这一标准。

对于自动化机器人和车辆中的光检测和测距（激光雷达）系统，亮度同样重要。这些系统不需要熔化金属的能力，但为了在长距离或高速度下进行精确测量，它们需要紧密聚焦的光束。如今顶级的激光雷达系统使用了超过100个半导体激光器，这些本质上发散的光束通过复杂的手动安装的透镜系统进行整流。这种复杂性导致成本上升，使激光雷达导航车辆对大多数消费者而言难以接触。

多个直径为3毫米的光子晶体半导体激光器建立在半导体晶片上。Susumu Noda

当然，其他类型的激光器也能产生超亮光束。例如，二氧化碳和[光纤激光器](https://spectrum.ieee.org/laser-weapons)，在工业应用市场上占主导地位。但与尺寸微小的半导体激光器相比，它们体积庞大。高功率的 CO[2] 激光器可以像冰箱一样大。它们也更昂贵，能效更低，控制起来更困难。

在过去的几十年里，我们在京都大学的团队一直在开发一种能突破传统表亮度极限的新型半导体激光器。我们称之为[光子晶体表面发射激光器](https://spectrum.ieee.org/tag/photonic-crystals)，简称 PCSEL（发音为“皮克塞尔”）。[最近](https://spectrum.ieee.org/photonic-crystal-lasers)，我们制造了一种 PCSEL，它可以像气体和光纤激光器一样亮——足以快速切割钢铁，并提出了一个亮度是现有激光器的10到100倍的设计。这样的设备可能会彻底改变制造和汽车行业。如果我们、我们的合作公司以及世界各地的研究小组——如台湾新竹的国立阳明交通大学、德克萨斯大学阿灵顿分校和格拉斯哥大学——能进一步提升 PCSEL 的亮度，甚至可以打开像惯性约束核聚变和光推进航天飞行这样的新领域的大门。

## 孔洞-圣杯

PCSEL 的魔力来自其独特的结构。与任何半导体激光器一样，PCSEL 包含一个轻发光材料层，称为活性层，夹在夹层层之间。实际上，为了方便理解，将这个设备想象成一个字面上的三明治是很有帮助的——比方说，一片火腿夹在两片面包之间。

现在想象一下将三明治提到嘴边，仿佛你要咬一口。如果你的三明治是一款传统的半导体激光器，它的光束将从远端辐射出去，远离你。这束光是通过在活性“火腿”层中通过电流的一个条纹来产生的。激发的火腿原子会自发释放光子，这些光子会刺激产生相同的光子，从而放大光线。条纹两端的镜子反复反射这些波；由于干涉和损耗，只有特定频率和空间模式——或模式——能够持续存在。当某个模式的增益超过损耗时，光就以一种相干的光束出现，该激光器被称为在该模式下振荡。

标准条纹方法的问题在于，很难在不牺牲光束质量的情况下增加输出功率。 半导体激光器的功率受其发射面积限制，因为极端集中的光会对半导体造成灾难性的损坏。 通过扩展条纹来提供更多功率，这是所谓的广区域激光器使用的策略。 但较宽的条纹也为振荡光提供了侧向之间的蜿蜒路径，形成所谓的高阶侧向模式。

你可以通过想象在输出光束的横截面上放置了一个屏幕来可视化侧向模式的强度模式。 沿着条带长度完美反射的光形成基础（零阶）模式，中心光束中有一个强度峰。 第一阶模式来自在角度向三明治边缘反射的光，有两个峰分别位于右侧和左侧；第二阶模式来自更小角度，有一排三个峰，以此类推。 对于每个更高阶的模式，激光器实际上作为较小发射器的组合运行，其较窄的口径使光束迅速发散。 因此，侧向模式的混合使激光光斑和扩散。

那些麻烦的模式是传统半导体激光器亮度最大约为100 MW/cm²/sr的原因。 PCSELs通过在三明治内部添加另一层来处理不需要的模式：即“瑞士奶酪”层。 这个特殊的额外层是一个半导体薄片，上面印有二维纳米孔阵列。 通过调节孔的间距和形状，我们可以控制激光内部的光传播，使其仅在基础模式中振荡，即使发射区域扩展也是如此。 结果是一个既可以*强大*又可以*狭窄*的光束。

由于它们的内部物理特性，PCSELs的工作方式与边发射激光器完全不同。 例如，来自PCSEL三明治的光束现在会向上辐射，穿过面包的顶层。 要解释这种不寻常的发射以及为什么PCSELs可以比其他半导体激光器亮度高几个数量级，我们必须首先描述瑞士奶酪的材料特性—实际上，这是一种称为光子晶体的迷人结构。

## 如何光子晶体工作

光子晶体控制光的流动方式类似于[半导体](https://spectrum.ieee.org/topic/semiconductors/)控制电子的方式。然而，光子晶体的晶格是由较大的实体（如孔洞、立方体或柱体）雕刻而成，这些实体的折射率在光波长的尺度上定期变化。尽管人工构建这些奇妙材料的追求不到40年，但科学家们已经了解到它们已经存在于自然中。例如，蛋白石、孔雀羽毛和一些蝴蝶翅膀都归功于自然工程的光子晶体内部光的复杂作用而具有辉煌的虹彩色彩。

理解光在光子晶体中的运动对于PCSEL设计至关重要。通过研究晶体的光子带结构，我们可以预测这种行为，这类似于半导体的电子带结构。一种方法是绘制频率与波数之间的关系图——即光子晶体晶格的一个单元格内可以容纳的波周期数。

例如，考虑一个由玻璃和空气交替形成的简单一维光子晶体。进入晶体的光线将通过并部分反射每个界面，产生重叠的光束，根据光的波长和方向增强或削弱。大多数波将穿过材料。但在某些点上，称为奇点点，反射与入射波完美结合形成不传播的驻波。在这种情况下，奇点发生在波从一个空气带到下一个空气带经历正好半个周期时。每当一个单元格是半波长的整数倍时，都会出现其他奇点。

我们中的一位（Susumu Noda）在这些材料甚至有名称之前就开始实验激光器，其中含有类似光子晶体结构的激光器。在上世纪80年代中期，在三菱电机公司期间，他研究了一种称为[分布反馈（DFB）激光器](https://en.wikipedia.org/wiki/Distributed-feedback_laser)的半导体激光器。DFB激光器是一种基本的条形激光器，内部带有一层额外的定期间隔填充有略有不同折射率物质的凹槽。这种周期结构类似于上述的一维光子晶体：它以单一波长反射光线，如凹槽间距所决定，从而形成驻波。因此，激光器只在该波长上振荡，这对于长距离光纤传输和高灵敏度光学传感至关重要。

正如三菱团队展示的那样，DFB激光器可以被引诱执行其他技巧。例如，当团队将器件中的凹槽间距设置为激光波长时，一些振荡光会向上衍射，使激光不仅从其活动条纹的微小前缘发出，而且还从条纹的顶部发出。然而，由于条纹的宽度较窄，这种表面光束狂暴扩散，这也使得增加输出功率变得困难。

对于野田来说，他的团队试图扩展条纹（从而增加亮度）而不引起其他问题，结果令人失望。尽管如此，这些早期的失败植入了一个有趣的想法：如果激光光束可以在*两个*维度上控制会怎么样？

## 提升亮度

后来，在京都大学，野田在这个领域开始兴起时领导了对2D和3D光子晶体的研究。1998年，他的团队建造了第一台PCSEL，自那时起我们不断完善设计，以实现各种功能，包括高亮度。

在基本的PCSEL中，光子晶体层是一个2D的正方形格子：每个单元格都是由四个孔形成的正方形。虽然2D光子晶体的能带结构比1D的更复杂，但同样会显示出预期形成驻波的奇点。对于我们的设备，我们利用了当邻近孔之间的距离为一个波长时出现的奇点。例如，一个操作在940纳米的砷化镓激光器，其内部波长大约为280纳米（考虑折射率和温度）。因此，基本砷化镓PCSEL中的孔大约设置在280纳米的间距处。

操作原理是这样的：当在活性层中产生这样长度的波时，邻近光子晶体层中的孔就像微小的镜子，将光向后和向侧弯曲。多个这种衍射的结合效果形成一个2D驻波，然后被活性层放大。其中一部分振荡光也向上和向下衍射，并从激光的顶部泄漏出来，产生单波长的表面光束。

这种设计能够有效运作的关键原因是半导体和孔内空气之间的大折射率对比。正如野田在创建第一个设备时发现的那样，低折射率对比的PCSELs，如DFB激光器，不会一致振荡。与DFB激光器不同的是，PCSEL的表面发射区域宽广且通常是圆形。因此，它可以产生具有更低散射度的高质量光束。

2014年，我们的团队报道了一款具有三角形孔隙方格网络和200x200 μm发射面积的PCSEL，可以在维持约1瓦的情况下连续运行，其发射的光斑仅散射约2度。与传统半导体激光器相比，后者的光斑通常散射角度超过30度，这一性能表现非常显著。下一步是提升光学功率，这需要更大的设备。但在这里我们遇到了问题。

根据我们的理论模型，使用单格子设计的PCSEL在不超过约200μm的情况下无法增大，因为会引发讨厌的高阶侧向模式。在PCSEL中，当一个站波的强度由于重复衍射而形成干涉图案时，多种模式会形成。在基本（即理想的）模式中，强度分布类似富士山，大部分振荡光集中在晶格中心。与此同时，每个高阶模式则有两个、三个、四个或更多的富士山。因此，当激光的发射区域相对较小时，高阶模式的强度峰值位于晶格的外围。它们的大部分光线因此从设备的侧面泄漏出来，阻止这些模式振荡并贡献于激光束。但与传统激光器一样，扩大发射区域为更多模式振荡提供了空间。

为了解决这个问题，我们在光子晶体层中添加了另一组孔洞，创建了双格子结构。在我们最成功的版本中，一个方形孔洞的正方形格子与一个椭圆孔洞的第二个正方形格子相位相差四分之一波长。因此，晶体内部的一些衍射光相互干涉破坏性地消除。这些抵消使侧向模式的强度峰值减弱和扩展。因此，当我们扩展激光的发射区域时，来自高阶模式的光仍然大量泄漏，不会振荡。

使用这种方法，我们制造了一个直径1毫米的圆形发射区域的PCSEL，并展示它可以在连续运行中产生10瓦的光束。光束仅散射0.1度，比其200μm前身更加细长和更加聚光，并且比传统半导体激光器可能的亮度高出三倍以上。当然，我们的设备还具有单模振荡的优势，而传统激光器在相当尺寸上无法做到这一点。

进一步提升PCSEL的亮度需要进一步的创新。在较大直径上，仅靠双格子方法无法足够抑制高阶模式，因此它们再次振荡。然而，我们观察到这些模式略微偏离激光器，这引起了我们对背面反射器的注意。（想象一下锡箔纸覆盖在火腿和瑞士奶酪三明治底部。）

这款50瓦的PCSEL足以切割钢材。Susumu Noda

在先前的设备世代中，这种反射器仅仅用于反射从激光发射面向下散射的光线并将其引导出去。通过调整其位置（以及光子晶体孔洞的间距和形状），我们发现我们可以控制反射，使其以对光子晶体层内振荡的二维驻波产生有用的方式干涉。这种干涉或耦合本质上诱导离开的波失去一些能量。离开波越偏斜，失去的光越多。然后，高阶模式消失了。

那就是在 2023 年，我们开发了一种PCSEL，其亮度达到了气体和光纤激光器的1 GW/cm²/sr。有了3毫米的发射直径，它可以连续激光输出高达50瓦，同时维持一个仅仅偏转了五十分之一度的激光束。我们甚至用它来切割钢铁。当这束明亮而美丽的光束在一块厚度为100微米的金属板上切割出一个圆盘时，我们整个实验室都聚在一起，惊叹地观看着。

## 更强大的PCSEL

尽管切割钢铁的演示非常令人印象深刻，但PCSEL必须更加强大才能在工业市场上竞争。例如，制造汽车零部件需要数千瓦级的光功率。

构建一个能够处理那种功率的PCSEL应该是相当简单的——要么通过组装九个3毫米的PCSEL阵列，要么通过将我们当前设备的发射面积扩展到1厘米。在这个尺寸上，高阶模式将再次出现，降低激光束的质量。但由于它们仍然像高功率气体和光纤激光器一样明亮，这种千瓦级PCSEL可能开始取代更笨重的竞争对手。

要真正改变游戏规则，1厘米的PCSEL需要通过抑制这些高阶模式来升级。我们已经想出了一种方法，通过微调光子晶体结构和反射器的位置来做到这一点。尽管我们尚未在实验室中测试过这种新配方，但我们的理论模型表明，它可以将PCSEL的亮度提高到10到100 GW/cm²/sr。想象一下，当这样集中的光可以从一个小包装中被操纵时，可以制造出多么独特和复杂的产品。

特别是对于那些高功率应用，我们需要提高激光的能效和热管理能力。即使没有任何优化，PCSEL的“壁插”效率已经达到了30到40％，超过了大多数二氧化碳和光纤激光器。更重要的是，我们找到了一条可能将效率提高到60％的路径。至于热管理，我们今天在实验室中使用的水冷技术应该足以应对1000瓦、1厘米PCSEL的需求。

高亮度的可编程光电子表面发射激光器（PCSELs）还可以用于制造更小、更经济的自动驾驶汽车和机器人传感器系统。最近，我们使用了一款500微米的PCSEL激光雷达系统。在脉冲操作下，我们将其运行在约20瓦，并获得了一个极其明亮的波束。即使在30米距离，其聚焦点尺寸也只有5厘米。对于没有外部透镜的紧凑型激光雷达系统来说，这样的高分辨率是前所未有的。随后，我们将大约与网络摄像头大小相似的原型装在机器人车上，并编程让它们在工程楼内跟随我们和彼此移动。

在另一条研究线上，我们展示了可编程光电子表面发射激光器（PCSELs）可以发射多束激光，并可以通过电子控制使其指向不同方向。通过改变光子晶体层中的孔的位置和大小，可以实现这种芯片上的光束导向。最终，它可能取代激光雷达系统中的机械光束导向。如果在同一芯片上集成光探测器，这些全电子导航系统将变得非常微小且低成本。

尽管这将是一个挑战，但我们最终希望制造出功率超过10千瓦、波束亮度达到每平方厘米1000GW的3厘米激光器——比今天任何激光器都要亮。在如此极端的亮度下，可编程光电子表面发射激光器（PCSELs）有望取代巨大且耗电量巨大的CO[2]激光器，后者用于产生等离子体脉冲，以用于极紫外光刻机，从而大大提高芯片制造效率。它们还能推动实现核聚变的努力，该过程涉及向豌豆大小的燃料胶囊发射数万兆瓦的激光功率。极亮激光还提升了光推进用于太空飞行的可能性。探测器受光推动的探测器可以在几十年内完成远行星的旅程，而不是几千年。

也许这是一个陈词滥调，但我们认为没有比这更恰当的预测来描述人类智慧的下一个篇章：未来，正如人们所说，是光明的。

*本文发表在2024年5月的印刷版上，标题为“有史以来最明亮的半导体激光器**。”*

从您的网站文章中获得

相关文章围绕着Web

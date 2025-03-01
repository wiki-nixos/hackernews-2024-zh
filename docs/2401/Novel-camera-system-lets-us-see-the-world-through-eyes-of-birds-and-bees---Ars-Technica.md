<!--yml

分类：未分类

日期：2024 年 05 月 27 日 15:11:48

-->

# 新型摄像系统让我们通过鸟类和蜜蜂的眼睛看世界 | Ars Technica

> 来源：[`arstechnica.com/science/2024/01/novel-camera-system-lets-us-see-the-world-through-eyes-of-birds-and-bees/`](https://arstechnica.com/science/2024/01/novel-camera-system-lets-us-see-the-world-through-eyes-of-birds-and-bees/)

新的摄像系统和软件包允许研究人员和电影制片人捕捉动物视角的视频。来源：Vasas 等人，2024 年。

我们中间谁不曾想过动物是如何感知世界的，通常与人类的感知方式不同？科学家、摄影师、电影制片人等人尝试用各种方法重建，比如说，一只蜜蜂在寻找适合授粉的花朵时看到的颜色。根据发表在《PLoS Biology》期刊上的一篇[新论文](http://journals.plos.org/plosbiology/article?id=10.1371/journal.pbio.3002444)，跨学科团队开发了一种创新的摄像系统，比现有系统更快、更灵活地适应光照条件，使其能够捕捉动物在其自然环境中的运动图像。

“我们一直对动物如何看待世界感到着迷。现代感觉生态学技术使我们能够推断出动物可能如何看待静态场景，”弗吉尼亚州费尔法克斯的乔治梅森大学生物学家、共同作者丹尼尔·汉利说。"然而，动物经常在移动目标上做出关键决定（例如，检测食物、评估潜在配偶的展示等）。在这里，我们为生态学家和电影制片人引入了硬件和软件工具，可以捕捉和显示动物感知的运动颜色。”

汉利及其合著者表示，不同的动物物种拥有一套独特的光感受器，对一系列波长敏感，从紫外线到红外线，取决于每种动物的特定生态需求。一些动物甚至能够检测到偏振光。因此，每个物种对颜色的感知都会有所不同。例如，蜜蜂和鸟类对紫外线光敏感，而这对人类的眼睛不可见。作者写道：“由于我们的眼睛和商用摄像机都无法捕捉到这些光的变化，因此大片的视觉领域仍然未被探索。”这使得动物视觉的假色图像变得强大而引人入胜。

然而，作者们认为目前制作假色图像的技术无法量化动物在运动中所看到的颜色，这是一个重要因素，因为运动对不同动物通过颜色外观和信号检测沟通和导航周围世界至关重要。例如，传统的光谱测色法依赖于物体反射的光来估计给定动物的光感受器将如何处理该光，但这是一种耗时的方法，并且丢失了大量的空间和时间信息。

四种不同动物眼中的孔雀羽毛：（a）孔雀；（b）人类；（c）蜜蜂；（d）狗。图片来源：Vasas 等人，2024 年。

多光谱摄影会在各种波长（包括紫外线和红外线）上拍摄一系列照片，并将它们堆叠到不同的颜色通道中，以得出与摄像机无关的颜色测量。这种方法在某种程度上牺牲了一些准确性，但提供了更好的空间信息，非常适合研究动物信号，但它只适用于静态物体，因此缺乏时间信息。

这是一个缺陷，因为"动物呈现并感知来自复杂形状的信号，这些形状会产生阴影并产生高光"，作者们写道。'这些信号在持续变化的照明和视角下变化。关于背景、照明和动态信号之间相互作用的信息很少见。然而，它构成了在自然环境中自由生活的有机体使用颜色的方式以及因此被感知的重要方面。"

因此，汉利和他的合著者们着手开发了一种能够产生高精度动物视角视频的摄像系统，该系统可以捕捉到动物在自然环境中感知到的视觉信号的全部复杂性。他们将现有的多光谱摄影方法与新的硬件和软件设计相结合。该摄像头可以同时记录四个颜色通道的视频（蓝色、绿色、红色和紫外线）。一旦将这些数据处理成"感知单位"，结果就是一个准确的视频，显示了一个多彩场景在各种动物眼中的感知，这是基于我们对它们拥有哪些光感受器的了解得出的。该团队的系统可以以 92%的准确率预测出感知到的颜色。这些摄像头已经在商业上可用，而且软件是开源的，以便其他人可以自由使用和构建。

本文顶部的视频展示了蜜蜂观察同伴在花朵上觅食和互动（甚至打斗）时所感知到的颜色——这是摄像系统捕捉自然环境中行为的能力的一个例子。在下面的画面中，汉利在野外涂抹防紫外线的防晒霜。作者们写道，他的浅色皮肤在人类视觉和蜜蜂假色视觉中看起来大致相同，"因为皮肤反射在波长较长处逐渐增加"。

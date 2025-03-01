<!--yml

类别：未分类

日期：2024-05-27 15:19:22

-->

# 变换的高阶导数 - Nosferalatu

> 来源：[`nosferalatu.com/HigherOrderDerivativesTransforms.html`](https://nosferalatu.com/HigherOrderDerivativesTransforms.html)

在之前的帖子中，我讨论了导数、对数和变换之间的关系。这篇博客文章是对那篇文章的补充，并解释了如何找到变换的二阶及更高阶导数。

### 变换的导数概念

让我们快速回顾一下我之前的博客文章。假设我们有一个变换 \(T\) 和一个初始位置为 \(x(0)\) 的点。点在时间 \(t\) 的位置以及该点的第一阶导数为

\(x(t) = T^t * x(0)\)

\(x'(t) = log(T) * x(t)\).

这里 \(log(T)\) 是变换的对数。 \(T\) 和 \(log(T)\) 都是关于 \(t\) 的常数。

### 第二阶导数是什么？

我们知道第一阶导数（\(x'(t) = log(T) * x(t)\)），所以为了找到第二阶导数，我们从这里开始

\(\dfrac{d}{dt}x'(t) = \dfrac{d}{dt}log(T) * x(t)\)

由于 \(log(T)\) 是关于时间的常数，因此我们有

\(x''(t) = log(T) * \dfrac{d}{dt}x(t)\)

而我们之前说过 \(x'(t) = log(T) * x(t)\)，所以我们只需将其代入，得到我们的答案：

\(x''(t) = log(T) * log(T) * x(t)\).

不错！换句话说，如果我们有了第一阶导数，那么第二阶导数只是再乘以 \(log(T)\)。

在之前的博客文章中，我们通过将点乘以 \(log(T)\) 来找到点的切向量。同样，我们现在可以通过将其乘以 \(log(T) * log(T)\) 来找到点的加速度向量。

### 第 \(n\) 阶导数是什么？

这种方法的美妙之处在于它是多么简单。对于第 \(n\) 阶导数，我们可以遵循同样的模式。更一般地，第 \(n\) 阶导数为

\(x^{n}(t) = log(T)^n * x(t)\)

### 交互式示例

这是一个交互式示例，在这里你可以看到切向量（绿色箭头）和加速度向量（红色箭头）随着时间从原点插值到 gizmo 的变换时的情况。您可以操作 gizmo 来平移和旋转变换。您还可以启用速度向量场或加速度向量场的可视化。

应用程序的源代码可以在 这里 找到。

### 评论

通过 Github Issues 在这篇文章上留下评论 [here](https://github.com/nosferalatu/nosferalatu.github.io/issues/2)。

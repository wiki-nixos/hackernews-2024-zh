<!--yml

category: 未分类

date: 2024-05-27 14:37:08

-->

# 如何在 2024 年三月加速 Rust 编译器 | Nicholas Nethercote

> 来源：[https://nnethercote.github.io/2024/03/06/how-to-speed-up-the-rust-compiler-in-march-2024.html](https://nnethercote.github.io/2024/03/06/how-to-speed-up-the-rust-compiler-in-march-2024.html)

自我 [上次更新](https://nnethercote.github.io/2023/08/25/how-to-speed-up-the-rust-compiler-in-august-2023.html) 关于 Rust 编译器性能的更新以来已经过去了六个多月。是时候更新一下了。

## 重大胜利

让我们从一些重要的改进开始。这个列表并不全面，只是我在这段时间内注意到的一些事情。关于顶部指标的信息可以在 [这篇文章](https://nnethercote.github.io/2022/10/27/how-to-speed-up-the-rust-compiler-in-october-2022.html) 中找到。

[#115554](https://github.com/rust-lang/rust/pull/115554): 有许多构建配置选择可以影响构建后的 Rust 二进制文件的性能。其中一种选择是使用 [单一代码生成单元](https://nnethercote.github.io/perf-book/build-configuration.html#codegen-units)，这会增加构建时间，但可以提高运行时速度和二进制文件大小。在这个 PR 中，[Jakub Beránek](https://github.com/Kobzol) 在 Linux 上使 Rust 编译器本身也使用了单一的代码生成单元。这导致在所有基准测试结果中，**平均墙时减少了 1.57%**，[平均最大 RSS 减少了 1.96%](https://perf.rust-lang.org/compare.html?start=c16823d757b376f90c5f5cbd542ce83235befbc4&end=871407a0341262d2a86703ca43b449d35fa5f236&stat=max-rss&nonRelevant=true)，同时还减小了 `rustc` 二进制文件的大小。这个改变尚未应用于 Windows 或者 Mac 的构建，因为改进效果较小，但可能很快会进行。

[#117727](https://github.com/rust-lang/rust/pull/117727): 在这个 PR 中，[Ben Kimock](https://github.com/saethlin/) 确保通过 `#[derive(Debug)]` 生成的所有 `Debug::fmt` 方法都带有 `#[inline]` 标记。这是一个听起来微不足道的小改变，却带来了惊人的结果：**平均墙时减少了 1.33%**，[在所有发布构建结果中，平均二进制大小减少了 1.32%](https://perf.rust-lang.org/compare.html?start=eae4135939881ae730342bd336ae6302c3787e27&end=0f44eb32f1123ac93ab404d74c295263ce468343&stat=size%3Alinked_artifact&nonRelevant=true&doc=false&debug=false&check=false&incrFull=false&incrUnchanged=false&incrPatched=false)。

[#119977](https://github.com/rust-lang/rust/pull/119977)：在这个PR中，[Mark Rousskov](https://github.com/Mark-Simulacrum)引入了一个缓存，帮助减少编译器内的许多哈希表查找。这导致[所有基准结果中的平均墙时减少了1.20%](https://perf.rust-lang.org/compare.html?start=92f2e0aa62113a5f31076a9414daca55722556cf&end=098d4fd74c078b12bfc2e9438a2a04bc18b393bc&stat=wall-time&nonRelevant=true)。这个想法首次出现是[6.5年前](https://github.com/rust-lang/rust/issues/45275)！

[#120055](https://github.com/rust-lang/rust/pull/120055)：在这个PR中，[Nikita Popov](https://github.com/nikic)将编译器使用的LLVM版本升级到LLVM 18。这导致[所有基准结果中的平均墙时减少了0.87%](https://perf.rust-lang.org/compare.html?start=bc1b9e0e9a813d27a09708b293dc2d41c472f0d0&end=eaff1af8fdd18ee3eb05167b2836042b7d4315f6&stat=wall-time&nonRelevant=true)。这是一系列LLVM更新的最新版本，使rustc更快。LLVM的工作非常出色！

另一则重要消息是，Cranelift代码生成后端现在可以在x86-64/Linux和ARM/Linux上[普遍使用](https://nnethercote.github.io/perf-book/build-configuration.html#cranelift-codegen-back-end)。这是rustc使用的标准LLVM代码生成后端的一个替代方案，旨在减少编译时间，但代价是生成代码质量较低。试试看吧，特别是在调试构建时！这是[由bjorn3进行了大量工作的成果](https://bjorn3.github.io/2023/10/31/progress-report-oct-2023.html)。

最后，Jakub通过[默认排除调试信息](https://kobzol.github.io/rust/cargo/2024/01/23/making-rust-binaries-smaller-by-default.html)大大减小了编译后程序的大小。对于小程序，这可以将它们在磁盘上的大小减少多达10倍！

## 我（缺乏）的改进

我第一次在没有自己提高编译速度的情况下写这些帖子。我一直使用基于配置文件的优化策略，而当你测量rustc时得到的配置文件现在非常平坦。在执行时间中，最热门的功能只占1%或2%，很难找到改进的地方。因此，我一直在处理与编译速度无关的事务。

这并不意味着没有可以改进的速度，正如前一部分所示。但是这些改进要难得多，通常需要特定领域的见解，在用通用分析器进行探索时很难获得。而且总是有其他有用的工作要做。

## 总体进展

在2023-08-23到2024-03-04期间，我们取得了一些出色的整体性能结果。

首先，[墙上时间](https://perf.rust-lang.org/compare.html?start=97fff1f2ed01f6f7c0c204530b693c74d88c2105&end=50e77f133f8eb1f745e05681163a0143d6c4dd7d&stat=wall-time&nonRelevant=true)：

+   测得了43个基准测试中的526个结果。

+   这些改进有437个，恶化有89个。平均变化是7.13%的减少，许多减少都在两位数范围内。（在我的[上篇文章](https://nnethercote.github.io/2023/08/25/how-to-speed-up-the-rust-compiler-in-august-2023.html)中，等效的减少也是7.13%。真是个巧合！）

下一个，[内存使用峰值](https://perf.rust-lang.org/compare.html?start=97fff1f2ed01f6f7c0c204530b693c74d88c2105&end=50e77f133f8eb1f745e05681163a0143d6c4dd7d&stat=max-rss&nonRelevant=true)：

+   再次，在43个基准测试中，测量了526个结果。

+   这些改进有367个，恶化有159个。平均变化是2.05%的减少，大多数变化在个位数范围内。

最后，[二进制大小](https://perf.rust-lang.org/compare.html?start=97fff1f2ed01f6f7c0c204530b693c74d88c2105&end=50e77f133f8eb1f745e05681163a0143d6c4dd7d&stat=size%3Alinked_artifact&nonRelevant=true)：

+   在43个基准测试中，测量了324个结果。

+   这些改进有318个，恶化有6个。平均变化是28.03%的减少，几乎每个结果都是两位数的减少。

+   如果我们将事物限制在[非增量发布构建](https://perf.rust-lang.org/compare.html?start=97fff1f2ed01f6f7c0c204530b693c74d88c2105&end=50e77f133f8eb1f745e05681163a0143d6c4dd7d&stat=size%3Alinked_artifact&nonRelevant=true&incrFull=false&incrUnchanged=false&incrPatched=false&check=false&debug=false&doc=false)，这对于二进制大小是最有趣的情况，有42个改进，1个恶化，平均变化是37.08%的减少。`helloworld`基准测试看到惊人的91.05%的减少。

+   这些改进主要是上述调试信息的省略，以及由Mark进行的一些元数据改进。

对于所有三个度量标准，除了少数结果未达到显著性阈值外，其余均达标。我没有分开这些结果，因为它们对主要数据影响不大。一如既往，这些测量是在Linux上进行的。

最后，Jakub最近[观察到](https://twitter.com/Beranek1582/status/1760546947352453317)，编译时间（由基准测试套件在Linux上测量）在2023年2月到2024年2月之间下降了15%。前三年的相应减少分别为7%，17%和13%，四年期间的总减少为37%。持续长时间的稳定改进确实有所帮助。

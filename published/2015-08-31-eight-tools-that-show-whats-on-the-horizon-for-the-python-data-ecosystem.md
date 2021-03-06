# 八个 Python 数据生态圈的前沿项目

Galvanize 最近在旧金山参加了 Dato 数据科学峰会，这次会议聚集了千余名来自业界和学术界的数据科学研究人员，他们交流并探讨关于数据科学、机器学习应用和预测模型的最新进展。

以下是我导师认为数据科学家将在未来数月乃至数年里使用的八个 Python 工具。

## 1.  SFrame and SGraph

Dato 数据科学峰会中重磅消息之一是 Dato 将在 BSD 协议下开源SFrame 和 SGraph。SFrame (short for Scaleable Data Frame) 提供可以优化内存效率的柱状数据结构和数据框式的界面。SGraph 具有相同的特性但是它主要用于提高画图效率。这两种数据结构最大的优点之一在于它们使得数据科学家可以做基于外存的数据分析，而不需要把数据导入内存中。

这一消息传达出 Dato 公司支持 Python 数据生态圈发展的诚意，这是 Dato 和 Python 数据社区发展的一个转折点。自从 Dato 公司推出企业版软件后，数据社区用户通常都有类似的误解，他们认为 Dato 公司会利用免费版本绑定用户，用户最终还是得付费。通过将程序库转化为开源工具，我们看出这种小把戏并不是 Dato 公司的目标。如今这两个程序库已经变成开源工具，我们希望看到其他开发者（Pandas, 说的就是你）能够充分利用 SFrame 和 SGraph 从而解决内存限制的问题。

## 2.  Bokeh

Bokeh 是一个不需要服务器就可以在网页浏览器中实现交互式可视化的 Python 程序库。Bokeh 可以处理非常大的数据集甚至是大数据流（比如实时光谱图），同时它还具有运算速度快、可嵌入和可视化新颖的特点。它对于想要快速便捷地创建交互式图表和数据应用的人来说非常有用。

Bokeh 真正表现出色的地方是大数据的可视化过程。与这些数据打交道的人应该感谢 Bokeh 致力于提升自身的性能。目前大多数的交互式工具都需要利用 Javascript 来实现，但是 Bokeh 仅利用 Python 一种语言即可实现。

## 3.  Dask

Dask是一款基于外存的Python 调度工具。它通过将数据集分块处理并根据所拥有的核数分配计算量，这有助于进行大数据并行计算。Dask 是利用 Python 语言编写的，同时也利用一些开源程序库，它主要针对单机的并行计算进程。

Dask主要有两种用法。普通用户将主要利用 Dask 提供的集合类型，它的用法类似于 NumPy 和 Pandas 这样的常规程序库，但它内部包含了画图功能。另一方面， Dask 开发者可以直接制作图表。Dask 图表利用 Python 字典、元组和函数来编码算法，而且它不依赖于 Dask 所提供的集合类型。

目前 Python 生态圈中的许多程序库功能相近。但是Blaze, Dask 和 Numba 这些程序库共同作用于数据处理过程的不同层面上。类似的，你可以把 Blaze 看成关系型数据库管理系统的查询优化器，而把 Dask 看成执行查询的引擎。关于这一点，Blaze 优化了查询或者控制命令的符号表达式，而 Dask可以根据你的硬件情况来优化执行过程。

## 4.  Ibis

如果你是一个数据科学家，可能你每天都会使用 Python 。虽然 Python 在很多方面都很优秀，但是它也存在自身的局限。其中最大的一个问题在于 Python 不能很好地适应数据集大小的变化。它对于小数据集很有效，但是对于更大的数据而言，则需要利用抽样的方法来解决数据集的规模问题，这会影响到最终的研究结果。

Ibis 是 Cloudera 实验室的新项目，它试图为具有 Python 工作经验的数据科学家和工程师们提供一个适用于任何数据规模的数据分析框架。这反映出单机版的 Python 在功能和可用性上并没有妥协，可以在处理大数据时提供相同的交互体验和全保真度分析。

Ibis 允许使用 100% 的端到端用户工作流，也整合了现有的 Python 数据生态圈（Pandas, Scikit-learn, NumPy 等）。Ibis 目前还是预览版，未来它将加入更多的功能，比如整合高级分析工具、机器学习方法和其他高性能的计算工具。

## 5.  Splash

抓取网页数据时经常碰到一个问题，许多网站使用大量的 JavaScript 代码。网页抓取工具很难执行 JavaScript 代码，所以你往往只能得到原始 HTML 数据。由 Scrapy 鼻祖 ScrapingHub 所创建的 Splash 是一种 JavaScript 渲染服务，它通过 Python 的 Twisted 和 QT 来实现。这是一个带有能够并行处理多个网页的轻量级网页浏览器，它可以执行自定义 JavaScript 代码并利用关闭图片或广告屏蔽的功能来提升渲染速度。

## 6.  Petuum

Petuum 是一个分布式机器学习框架，它试图为大规模机器学习问题提供一个通用算法和系统接口。它提供了解决大规模机器学习数据集和参数太大问题的分布式编程工具。Petuum 专门为机器学习设计，这意味着它可以利用数据的各种统计性质来优化性能。

Petuum 具有多项核心功能：Bösen 是一个为数据并行机器学习算法设计的关键值存储仓库。它利用 SSP （Stale Synchronous Parallel ）一致性模型，该模型允许在不牺牲算法正确性的情况下使用异步功能。另外一个功能是 Strads，它是一个为模型并行机器学习算法而设计的调度工具。它执行了关于机器学习更新操作的小粒度调度，而且优先计算的部分程序需要避免可能损害性能的不安全并行操作。

## 7.  Flink

Apache Flink 是可扩展的批处理和流处理的数据处理平台。Flink 的核心组件是一个提供数据分布、通信和容错功能的流数据处理引擎。它和 Apache Spark 非常相似，因为它们的主要目的之一就是替代 Hadoop 的 MapReduce 功能。

虽然 Spark 和 Flink 的 API 非常相似，但是两者处理数据的方式存在不同之处。当 Spark 处理流式数据时，它实际上利用单位时间内的数据片集合进行小批量处理。这可以视为流处理的近似过程。通常情况下它表现良好，但是在对延迟要求较高的情况下会引发一些问题。另一方面，Flink 是一个可以实现批量处理的流处理框架。换句话说，除了做简单的工作（批量处理）和对较难的工作（流程处理）以外，Flink 既可以解决较难的工作，也可以处理简单的任务。

## 8.  Pyxley

基于网页的仪表板（dashboards）是分享数据科学发现的最直观方法之一。 Shiny 包给使用 R 语言的数据科学家提供了一个不必通过编写Javascript， HTML 和 CSS就可以构建交互式网页应用程序的框架，但是在 Python 中却没有类似的功能。 Pyxley 就相当于 Python 版的 shiny ，它简化了网页应用程序开发的过程并可以通过 Flask， PyReact 和 Pandas来加入自定义的 Javascript 代码。

- 原文链接: 
http://www.galvanize.com/blog/2015/07/31/eight-tools-that-show-whats-on-the-horizon-for-the-python-data-ecosystem
- 原文作者：Bo Moore
- 翻译：Fibears

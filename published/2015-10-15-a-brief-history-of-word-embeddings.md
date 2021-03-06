#词嵌套（词向量）简史
当前自然语言处理最大的趋势是对词嵌套的使用，词嵌套是指由语义相关性所度量的相似性向量。这些向量不仅可以表示计算词语之间的相关性，同时它还是其他自然语言处理项目的基础，比如文本分类、文档聚类、词性标注、命名实体识别、情感分析，等等。从 ACL 和 EMNLP 等大型 NLP 会议的会议记录中我们可以看出词向量是 NLP 发展的大方向。这是有史以来第一次以语义为主题的 EMNLP（Empirical Methods in NLP） 会议。事实上，由于大量的文章中使用了词向量方法，一些人甚至建议将这个会议重新命名为 “Embedding Methods in NLP”。

这是一个积极的趋势（如果你喜欢语义学和词向量的话），目前在 NLP 领域中有许多正在取得进展的项目。然而，最近许多关于词向量的出版物却出人意料地无视了前人在计算机科学、认知科学和计算机语言学中的工作成果。这种不是建立在现有知识体系上的方法将会拖延学科的发展。

本篇博客的要点在于提供词向量的简史，同时对该方法的当前发展做一个总结。需要注意的是：这决不是意味着提供所有相关研究主题的完整列表；相反，它的目的是成 为有兴趣继续探索该领域的人的研究参考和起点。

首先是专业术语的标记。由于当前流行的方法主要来源于深度学习社区，词嵌套已经成为当前的主导词语。在计算语言学中，我们经常使用分布语言模型这个称谓。实际使用过程中还存在许多可供选择的术语，比如非常通用的分布式表述、更具体的语意向量空间和词向量空间。为了统一起见，我将在本篇博文中使用词嵌套这个称谓。

词嵌套的主要思想是：上下文信息可以单独构成一个可行的语义向量，这与传统的语义学和乔姆斯基理论形成鲜明的对比。这个想法具有结构主义语言学和普通语言哲学上的理论根源，特别是哈里斯、约翰·费斯和维特根斯坦所有在 19 世纪 50 年代出版的作品。最早利用特征向量来量化语义相似性的方法使用了手工计算的特征变量。查尔斯·奥斯古德在 19 世纪 60 年代编制的语义差量度表是一个很好的例子，进入 80 年代后，相似性向量开始被用于连接论和人工智能的早期作品上。

1990 年左右，利用自动生成上下文特征的方法在许多不同研究领域中得到了发展。最具影响力的模型之一是潜语义分析/索引模型（LSA/LSI），该模型是主题模型的前身，它建立在信息检索的环境中。差不多在同一时间，人们在人工神经网络的研究中开发了许多不同的模型。这些模型中最出名的当属自组织图（SOM）和简单递归网络模型（SRN），其中后者自然语言模型的前身。在计算语言学领域，辛里奇·舒尔泽所开发的基于共生词的模型被用在 HAL 模型（认知科学中我们称之为语义存储模型）中。

后来的发展基本上就是改进这些早期模型。主题模型是潜语义分析模型的细化，其中包含了概率潜语义分析模型和隐主题模型。神经语言模型和 SRN 模型拥有相同的应用程序，同时它还包含了卷积网络模型（CNN）和自动编码模型的架构。分布式语义模型则是基于 HAL 模型和随机索引模型。

这些不同模型的主要区别是它们所使用的上下文信息类型。LSA 和主题模型主要处理文档数据，而神经语言模型和分布式语义模型则处理词数据。这些不同上下文信息可以获取不同类型的语义相似度；基于文档数据的模型获得语义关联信息（比如，小船-水），而基于词数据的模型则获得语义相似性信息（比如，小船-轮船）。这个非常基本的差异经常被误解。

说到常见的误解，这里还需要揭穿两个错误的观念：

不需要利用深层神经网络模型来构建词向量。实际上，当前两个最成功的模型—— word2vec 库中的 Skipgram 模型和 CBoW 模型——和原始的 SRN 模型同是浅神经网络模型。
神经网络预测模型和基于计数的分布式语义模型之间没有本质的区别。相反，它们通过不同的计算方式来获得相同类型的语义模型。最近的一些论文从理论上和实证上证明了这些不同模型之间的相似之处。
（https://levyomer.files.wordpress.com/2014/09/neural-word-embeddings-as-implicit-matrix-factorization.pdf

http://www.emnlp2015.org/proceedings/EMNLP/pdf/EMNLP024.pdf）

以上就是词向量的简史介绍和两条关于错误观念的澄清信息。词向量的当前发展状况是什么样的呢？一个无聊的答案是，这取决于你想解决的任务和你想花多大的努力来优化模型。更愉快的回答是，无论你选择哪个流行的模型你都会获得你想要的结果，因为它们之间或多或少都是相同的。由于语义模型可以获得良好的结果并且在处理各种任务时非常稳健，所以使用语义模型（不管是使用分布式语义模型还是神经网络模型）是一个不错的选择。

对于那些对词嵌套感兴趣的朋友，我推荐以下这些资源：

独立的实现工具：word2vec、GloVe

构架：S-Space（JAVA）、SemanticVectors（JAVA）、Gensim（Python）、PyDSM（Python）、DISSECT（Python）
 

原文链接:

http://gavagai.se/blog/2015/09/30/a-brief-history-of-word-embeddings/

原文作者：Gavagai

翻译：Fibears


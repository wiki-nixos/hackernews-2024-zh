<!--yml

类别：未分类

date: 2024-05-27 15:13:05

-->

# 我们已经达到了向量数据库的顶峰吗？

> 来源：[`softwaredoug.com/blog/2024/01/24/are-we-at-peak-vector-db`](https://softwaredoug.com/blog/2024/01/24/are-we-at-peak-vector-db)

作为一个搜索专家，也是 NoSQL 时代的老手，我经常在心中想，“为什么会需要这么多向量数据库？”。

即使在我们当前的人工智能时代，每个人和他们的妈妈都在尝试构建下一个聊天/人工智能驱动的东西。即使在今天，当似乎每个人都在某处放置向量以便检索它们时…

我必须问一个艰难的问题 - 我们何时达到了向量数据库的顶峰？对于存储和检索向量的特定任务，我们有足够的选择吗？

仅仅初步列举，我可以想到以下向量数据库、库，等等：

**纯向量数据库**

+   Pinecone

+   QDrant

+   Milvus / Zilliz

+   Weaviate

+   Turbopuffer

+   MyScale

**开源搜索引擎**

+   Solr

+   Elasticsearch

+   OpenSearch

+   Vespa

**库**

+   Annoy,

+   FAISS,

+   NMSLib

+   HNSWLib

+   Lucene

+   Chroma

+   (其他无数个)

**开源数据库**

+   Redis

+   PGVector

+   Cassandra、Mongo 等等（似乎每个数据库都在获取其向量索引：wink:）

**云解决方案**

+   Google Vertex

+   Azure AI Search

（更多内容请参阅[awesome vector search](https://github.com/currentslab/awesome-vector-search)）

如果我们把向量搜索看作 NoSQL 范式中的一种数据存储类型，我们可能会把它放在自己的类别中。我们会说 Mongo 是一个文档数据库，与 CouchDB 和伙伴们一样。我们会说 Cassandra 是一个列式数据存储，与 Scylla 或 HBase 一样。

因此，在每个类别中，我们有几个（2-3）选择。然而，在向量搜索中，我们有数十种选择。作为这些选择的“客户”，这个领域变得令人难以应付。

而且向量检索越来越不是问题。解决现实世界检索的难题不仅仅是获取向量，而是与之相关的一切。

意图分类 - 给定一个“查询”，我如何知道我是否能解决这个问题（RAG）或如何将查询路由到正确的位置 推理和重新排名 - 给定一个“查询”，以及一些候选的检索到的向量/项，我如何在任意 tensorflow 模型上执行推理，以给出最相关的项？ 多样性 - 给定一个“查询”，我如何扩大候选池，不仅仅是“与向量相似”的 - 不仅仅是一个意图，而是所有可能的意图 词汇检索/混合搜索 - 给定自然语言，我如何使用直接的词汇信号（老套的 BM25，仅仅是过滤，等等）来给出相关结果

好吧，这只是词汇方面。我们正在发明与数据交互的新方法。我与之交谈的人中没有人真正创建了一个评估 RAG 上下文质量的强大方法。有新的 UX 范式 - 聊天和与聊天相关的 - 我们正在尝试。

挑战在于，世界是一个广阔的实验场，但乍一看，所有的钱都集中在技术栈的一个部分。我们没有全面地看待这个问题。

## 为什么我们还没有达到峰值向量数据库

好吧，这是一个观点，当然。

这是另一个观点。

需要一个地方来集中注意力，重新思考检索问题。就像 NoSQL 强迫我们重新思考数据库一样。资金和智慧需要一个地方来集中，以解决下一代检索 + 相关性问题。

所以，我内心中那个老式的、脾气暴躁的搜索人会说“好吧，不管怎样，人们意识到他们需要搜索引擎，然后使用 Solr / Elasticsearch。”

但这还不够。这些搜索工具感觉很深奥，在一般的“人工智能工程师”脑海中，他们会首先考虑向量检索，然后碰到我列出的所有问题。他们会学到，他们需要关心 ANN 之外的所有事情，但是只有在他们的应用程序启动之后才会这样。就像往昔的搜索工程师在承诺安装大型 Solr 或 Elasticsearch 后才会倒退到各种问题中一样。

此外，我怀疑，越来越多的界面将由某种检索式的东西驱动。搜索但不是搜索。实时推荐，但由向量（和其他类型的）检索驱动，看起来更像搜索引擎——不是像今天普遍的批量计算、夜间作业那样。2016 年，我写过关于“相关性驱动应用程序”即将发生的革命，现在，它正在发生——不是通过我曾经认为的乏味的老式搜索引擎——而是通过重新发明驱动用户体验的检索层的整个概念。

因此，我怀疑这些公司的聪明人会超越“使 ANN 更好/更可扩展”的范畴，构建完整的检索和排序系统，解决大量的问题。资金和精力将流向客户认为有问题的地方。

最后，就像在 NoSQL 中一样，我们最终可能会回到 SQL（但具有所有 NoSQL 的创新）。换句话说，我们可能最终会看到这些供应商构建一个完整的“搜索引擎”。然而，这些新的搜索引擎将包含更多的电池，用于 AI/聊天/RAG/人们越来越多地寻求的其他体验。

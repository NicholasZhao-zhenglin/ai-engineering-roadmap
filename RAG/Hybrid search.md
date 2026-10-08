# Hybrid Search 学习笔记

## 1. 什么是词法检索（Lexical Search）？
依据关键词进行检索，也就是关键词匹配检索，经典算法：BM25。
是一种Sparse Retrieval。
## 2. 什么是语义检索（Semantic Search）？
依据两个词汇之间是否语义相近进行检索。常见的做法是依据embedding后向量空间的语义相似度进行检索，也就是常说的向量检索。
涉及ANN 索引（Approximate Nearest Neighbor Index，近似最近邻索引）和HNSW（Hierarchical Navigable Small World）（暂不展开）
## 3. 为什么需要 Hybrid Search？
因为词法检索和语义检索各有优劣，二者融合能达到更好的效果。
## 4. 什么是 RRF（Reciprocal Rank Fusion）？
中文译作 “倒数排名融合” 将词法检索和语义检索进行融合的算法。
由于词法检索和语义检索得到的分数量纲不同，无法进行直接相加，所以取倒数。
公式：score(d) = SUM( 1/（k+rank(d)）)
其中k=文档总数，排名越小（靠前），分母越小，则score更高。
## 5. Hybrid Search 适合什么场景？
既需要词法检索，又需要理解语义的场景。
其实适配于绝大多数rag场景，无法穷尽列举适配场景，但是可以看一些反例。
例如：查询订单编号、员工信息这种需要精确匹配关键词的，只需要词法检索；
询问如何学习python这种比较模糊的问题的，适配于语义检索。
适配场景列举：企业库知识查询、电商QA等。
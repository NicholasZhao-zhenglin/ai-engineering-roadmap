# AI Engineering Roadmap

AI 工程方向的学习笔记。**边学边写，写成能直接用的东西** —— 不是抄概念，而是把每个模块搞到能讲清「是什么、为什么、什么时候不该用」。

---

## 当前进度

### ✅ 已完成

| 主题 | 位置 | 内容 |
| --- | --- | --- |
| **RAG · 混合检索** | [`RAG/Hybrid search.md`](./RAG/Hybrid%20search.md) | 词法检索（BM25）vs 语义检索的优劣、为什么需要融合、RRF 倒数排名融合原理与公式、适用与不适用场景 |
| **算法 · 二叉树** | [`LeetCode/二叉树.md`](./LeetCode/二叉树.md) | 层序遍历 BFS 模板、BST 性质与中序遍历的有序性 |

### 🚧 进行中 / 计划

按优先级排列：

| 主题 | 状态 | 要回答的问题 |
| --- | --- | --- |
| RAG · 文档解析 | 计划 | PDF 解析方案怎么选？MinerU / DeepDoc / PyMuPDF 的边界在哪？表格和公式怎么办？ |
| RAG · 切分策略 | 计划 | 固定长度 vs 语义切分 vs 层级切分，各自在什么场景失效？ |
| RAG · 重排（Rerank） | 计划 | 召回 100 条后怎么排？Cross-encoder 的代价与收益 |
| RAG · 评测 | 计划 | Recall@K / MRR / NDCG 怎么算？怎么构造评测集？ |
| Agent · 记忆机制 | 计划 | 短期 / 长期 / 情节记忆怎么存？什么时候该压缩、什么时候该遗忘？ |
| Agent · 规划与反思 | 计划 | ReAct / Plan-and-Execute / Reflexion 的差异与代价 |
| 工程 · 向量库选型 | 计划 | Milvus / pgvector / ES 的取舍 |
| 算法 · 高频题型 | 计划 | 双指针、滑动窗口、动态规划、图的遍历模板 |

---

## 笔记写法约定

每篇笔记尽量回答这四个问题，缺一不可：

1. **是什么** —— 用一句话说清，不用术语堆砌
2. **为什么需要** —— 它替代了什么方案，解决了什么具体痛点
3. **怎么用** —— 公式 / 伪代码 / 关键参数
4. **边界在哪** —— 什么场景下**不该**用它（这一条最容易被省，但最有价值）

---

## 目录结构

```
.
├── RAG/          检索增强生成相关
├── LeetCode/     算法与数据结构
└── README.md
```

---

## 相关项目

这些笔记的实现在其他仓库落地：

- **[adaptive-english-speaking-agent](https://github.com/NicholasZhao-zhenglin/adaptive-english-speaking-agent)** — Agent 的记忆、规划与反馈闭环
- **[cnipa-ipc-dataset](https://github.com/NicholasZhao-zhenglin/cnipa-ipc-dataset)** — 真实规模的非结构化文档解析与结构化

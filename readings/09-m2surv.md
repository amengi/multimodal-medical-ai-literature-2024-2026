# M²Surv

**论文**：[Memory-Augmented Incomplete Multimodal Survival Prediction via Cross-Slide and Gene-Attentive Hypergraph Learning](https://papers.miccai.org/miccai-2025/0555-Paper2663.html)<br>
**来源**：MICCAI 2025<br>
**代码**：[MCPathology/M2Surv](https://github.com/MCPathology/M2Surv)<br>
**标签**：WSI · genomics · survival · hypergraph · memory bank · missing modality<br>

## 简要 reading

M²Surv 将多张 FFPE/FF 病理切片和基因组表示组织成超图，以捕获跨切片和跨模态高阶关系。对于缺失病理或基因组的病例，模型从记忆库检索先前学习的配对表示进行动态补偿，从而避免为每种缺失组合单独训练模型。

论文在五个 TCGA 癌症数据集上报告生存预测结果，并分别比较完整、病理缺失和基因组缺失情况。

## 证据与疑问

- 优点：同时处理多 WSI、模态不平衡和缺失，适合真实肿瘤学数据结构。
- 风险：记忆库若在划分前构建，可能造成患者或队列信息泄漏；必须确认只使用训练患者。
- 检索到的“相似患者”并不等于当前患者缺失模态的真实值，尾部亚型尤其容易被头部病例覆盖。

## 可迁移启发

可将记忆补偿设计成带置信区间的 retrieval distribution，并评估检索邻居在癌种、分期、中心与种族上的偏差。

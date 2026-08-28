# PG-MLIF

**论文**：[PG-MLIF: Multimodal Low-rank Interaction Fusion Framework Integrating Pathological Images and Genomic Data for Cancer Prognosis Prediction](https://papers.miccai.org/miccai-2024/603-Paper1221.html)<br>
**来源**：MICCAI 2024<br>
**代码**：[panxipeng/PG-MLIF](https://github.com/panxipeng/PG-MLIF)<br>
**标签**：pathology · genomics · low-rank fusion · survival<br>

## 简要 reading

PG-MLIF 用模态注意机制过滤病理和基因组特征，以 low-rank multimodal fusion 降低高阶交互计算量，再通过最优权重拼接融合单模态和联合表示。实验在 GBMLGG 和 KIRC 上进行生存预测与风险分层。

## 证据与疑问

- 优点：低秩交互为病理高维特征与组学融合提供了计算可控的基线。
- 局限：默认两类模态完整且患者级配对，不直接解决缺失或非配对。
- 需要检查低秩分解是否丢失稀有但重要的跨模态高阶协同。

## 可迁移启发

可以把它作为 complete-data upper bound，再加入模态 dropout、尾部组合评价和不确定性门控，检验低秩融合在真实不完整场景下是否稳定。

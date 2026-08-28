# IPIC

**论文**：[Unpaired Multimodal Learning for Biological Datasets](https://proceedings.mlr.press/v315/ji26a.html)<br>
**来源**：MIDL 2026<br>
**代码**：未核验<br>
**标签**：biology · unpaired multimodal · group labels · contrastive learning<br>

## 简要 reading

IPIC 面向无法逐样本配对的生物测量，例如测量过程会破坏样本。它不要求实例配对，只使用 treatment-group 标签：在同一处理组内跨模态匹配，在处理组之间维持聚类分离，从而学习具有生物意义的共同嵌入。论文在四个整理后的生物多模态数据集上验证。

## 证据与疑问

- 优点：缺少实例配对时仍利用弱组级监督，设定符合很多组学实验。
- 隐含假设：处理组足以决定跨模态共享因素；批次效应或组内异质性可能破坏该假设。
- 组标签过强时，模型可能只编码 treatment identity，而非连续生物状态。

## 可迁移启发

患者级研究可用疾病亚型、治疗组或时间窗作弱锚点，但需加入批次对抗、组内多样性和未见组泛化实验。

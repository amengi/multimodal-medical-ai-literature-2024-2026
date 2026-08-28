# PID Framework

**论文**：[Quantifying & Modeling Multimodal Interactions: An Information Decomposition Framework](https://proceedings.neurips.cc/paper_files/paper/2023/hash/575286a73f238b6516ce0467d67eadb2-Abstract-Conference.html)<br>
**来源**：NeurIPS 2023（超出两年窗口，作为基础理论纳入）<br>
**代码**：未核验<br>
**标签**：partial information decomposition · redundancy · uniqueness · synergy · pathology<br>

## 简要 reading

论文用 Partial Information Decomposition 将两个模态关于任务的总信息拆成冗余、两个模态各自的独有信息与协同信息，并提出可扩展到高维数据的估计方法。案例包括病理、情绪预测和机器人感知。

## 信息论检查

- PID 比单一 MI 更适合回答“融合为什么有效”，因为它区分重复证据和必须联合观察才能得到的证据。
- PID 并非只有唯一公认定义；不同冗余公理和估计器可能给出不同数值。
- 高维连续医学数据上的估计仍需用合成数据、bootstrap 和估计器敏感性分析校准。

## 医学启发

在决定早期融合、晚期融合、专家路由或模态补全前，先估计数据更偏冗余、独有还是协同。若独有信息高，强对齐和确定性补全都可能有害。

# CLIMD

**论文**：[CLIMD: A Curriculum Learning Framework for Imbalanced Multimodal Diagnosis](https://papers.miccai.org/miccai-2025/0147-Paper4207.html)<br>
**来源**：MICCAI 2025<br>
**代码**：[KHan-UJS/CLIMD](https://github.com/KHan-UJS/CLIMD)<br>
**标签**：class imbalance · multimodal diagnosis · curriculum learning · complementarity<br>

## 简要 reading

CLIMD 不直接重采样或生成尾类，而是先用 intra-modal confidence 和 inter-modal complementarity 估计每个多模态样本的难度。训练调度器从相对均衡、容易的子集开始，逐轮增加样本量和类别不平衡程度，最终回到真实训练分布。

论文在 MLLC 和 BRCA 数据集上比较随机欠采样、SMOTE、VAE 过采样、加权交叉熵和 focal loss，并报告 Accuracy、Weighted F1 和 Macro F1；还将课程策略接入其他多模态模型。

## 证据与疑问

- 优点：显式把跨模态互补性纳入样本难度，而不是只按类别频率调度。
- 风险：置信度由尚未充分训练的模型产生，早期错误可能把真正重要的尾类样本判为过难并推迟学习。
- 仅两个数据集，尚不足以说明对更极端疾病长尾和标签噪声的鲁棒性。

## 可迁移启发

课程难度可以结合专家先验、模态质量和不确定性，而不是只依赖模型置信度；同时应报告 head/medium/tail 分层指标。

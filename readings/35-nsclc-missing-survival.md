# 自然缺失下的 NSCLC 多模态生存预测

- **论文**：Handling Missing Modalities in Multimodal Survival Prediction for Non-Small Cell Lung Cancer
- **作者**：Filippo Ruffini 等
- **出处**：npj Digital Medicine，2026；在线发表 2026-06-22
- **DOI**：[10.1038/s41746-026-02783-3](https://doi.org/10.1038/s41746-026-02783-3)
- **PubMed**：[PMID 42332139](https://pubmed.ncbi.nlm.nih.gov/42332139/)
- **代码**：[GitHub](https://github.com/arco-group/Handling-Missing-Modalities-in-Multimodal-Survival-Prediction-for-Non-Small-Cell-Lung-Cancer)

## 简要 reading

**问题。** 小型 NSCLC 队列中 CT、WSI 和临床变量天然不完整，complete-case 删除会进一步损失样本并改变病例构成。

**方法变化。** 预训练基础模型分别抽取三类模态特征，missing-aware 编码与中间融合直接消费任意可用子集，不生成缺失模态。论文报告三模态 C-index 74.42，并分析不同特征提取器下的模态贡献。

**证据边界。** 队列不可公开再分发；现有证据仍受样本量、治疗路径和单一临床场景限制。需要核查缺失机制、患者级划分、时间泄漏、外部中心和 C-index 置信区间；模态权重不是因果信息价值。

**研究连接。** 这是路线 A/B 的现实锚点：把 BALM/MCR 的优化平衡与该非生成架构结合，并以真实缺失模式训练；若生成式补全不能在校准和 risk–coverage 上超过它，就应拒绝补全。

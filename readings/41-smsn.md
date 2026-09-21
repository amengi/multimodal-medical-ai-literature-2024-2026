# SMSN：顺序信息瓶颈融合

- **论文**：Sequential Information Bottleneck Fusion: Towards Robust and Generalizable Multi-Modal Brain Tumor Segmentation
- **作者**：Tianyi Liu, Xi Yang, Wei Wang, Anh Nguyen, Haochuan Jiang, Kaizhu Huang
- **出处**：ICLR 2026
- **原文**：[ICLR 2026](https://iclr.cc/virtual/2026/poster/10006952) · [OpenReview](https://openreview.net/forum?id=tmV2sOZ8TV)
- **代码**：代码随补充材料提供；本轮未核验到独立公开仓库

## 简要 reading

**问题。** 并行拼接或 attention 在模态缺失时会让融合表示发生突变；论文追问逐步压缩是否能比一次性融合更稳定地保留跨模态共同信息。

**方法变化。** SMSN 随机选择可见模态作为起点并重排其余模态，通过两阶段 Information-Bottleneck Fusion Module 顺序更新共享状态，同时以独立分支恢复模态特异特征。实验覆盖 BraTS 2018/2020 和无需微调的脑转移外部集。

**信息论边界。** 目标中的互信息由变分形式实现；“更紧的上界”和更平滑的 loss landscape 不等同于真实临床缺失下更好的校准。随机顺序也没有回答哪一模态应先进入瓶颈。

**研究连接。** 把顺序从随机变量改为可证伪的“条件信息增益/检查成本”策略：若最先加入高条件独有信息且高质量的模态不能稳定改善最坏组合与外部校准，则顺序信息覆盖的解释不成立。

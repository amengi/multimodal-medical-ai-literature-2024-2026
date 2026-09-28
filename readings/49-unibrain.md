# UniBrain：统一 MRI 补全与理解

- **论文**：Unified Multimodal Model for Brain MRI Imputation and Understanding
- **作者**：Zhiyun Song, Che Liu, Tian Xia, Avinash Kori, Wenjia Bai
- **出处**：MICCAI 2026，LNCS 16894
- **原文**：[MICCAI Open Access](https://papers.miccai.org/miccai-2026/1110-Paper2626.html)
- **代码**：[GitHub](https://github.com/zhiyuns/UniBrain)

## 简要 reading

**问题。** 两阶段“先补全、后诊断”会让生成误差与诊断目标脱节；UniBrain 尝试在同一自回归序列中联合生成缺失 MRI 与医学理解。

**方法变化。** 模型使用交错、描述增强的数据流，将影像生成和理解统一训练；self-alignment 连接密集视觉表示，dynamic hidden states 缓解长上下文 exposure bias。

**证据边界。** 主要以 2D slices 接收 case-level 报告监督，存在患者内切片泄漏和弱对齐风险；缺少 OOD、放射科医师病灶忠实度评价，推理需多 GPU，且部分生成基线较旧。

**研究连接。** 与 AFM2、AdaMM 和路线 B 组合时，应把统一模型拆回可审计的“观测证据、生成证据、决策头”；以患者级切分、3D 一致性、病例错配和生成顺序置换检验所谓联合理解是否只是语言/序列捷径。

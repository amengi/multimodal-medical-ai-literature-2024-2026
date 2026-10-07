# RMoE：患者检索与可靠性专家处理不完整生存数据

- **论文**：Retrieval-Based Mixture-of-Experts for Patient-Specific Cancer Survival Prediction with Incomplete Multimodal Data
- **作者**：Minjoo Lim, Bogyeong Kang, Hyun Jung Lee, Eunjung Jo, Keun-Soo Heo, Mingxia Liu, Tae-Eui Kam
- **出处**：MICCAI 2026，LNCS 16887
- **原文**：[MICCAI Open Access](https://papers.miccai.org/miccai-2026/0893-Paper2015.html)
- **代码**：未核验到公开仓库

## 简要 reading

**问题。** 全局均值或生成模型忽略患者特异的 WSI–genomics 依赖，而单一路径也难适应不同缺失组合。

**方法变化。** RMoE 双向跨模态检索表型相似患者，以邻居特征补偿缺失模态；router 根据检索置信度和可用模态加权专门专家。在 BLCA、BRCA、UCEC 三个 TCGA 队列的 60% 训练缺失与单模态测试上比较。

**证据边界。** 主要是标准 MCAR/MAR 模拟而非真实 MNAR；风险组辅助检索可能产生近标签捷径，必须确保邻居库严格限于训练折。固定 60% 不能证明跨缺失率鲁棒，TCGA 多癌种也不等于外部医院验证；检索表示相似不保证患者级缺失组学真实。

**研究连接。** 与 M²Surv、RAM 思路和 EMMS 组合：把检索看作带可靠度的外部证据而不是 imputation，使用空证据作回退；按邻居纯度、类别/组合频率和站点漂移校准 gate，并加入邻居标签洗牌、跨站点库与尾部亚型反证。

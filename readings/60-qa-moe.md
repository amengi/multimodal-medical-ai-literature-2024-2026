# QA-MoE：质量估计与路由解耦的临床多模态专家模型

- **论文**：Quality-Aware and Stable Multimodal Mixture-of-Experts for Robust Clinical Prediction in Noisy and Missing-Modal Settings
- **作者**：Linpeng Sun, Victor S. Sheng
- **出处**：IJCAI 2026，AI and Health，6886–6894
- **DOI**：[10.24963/ijcai.2026/766](https://doi.org/10.24963/ijcai.2026/766)
- **代码**：[GitHub](https://github.com/Illidon/QA-MoE)

## 简要 reading

**问题。** 可用模态不一定可靠；若质量估计与 MoE 路由混在一起，噪声、极端缺失和模态竞争会共同放大路由不稳定与过度置信。

**方法变化。** QA-MoE 先用 Dirichlet evidential scorer 估计模态级 epistemic uncertainty，再以 bootstrap-consensus subset selector 筛掉低质量模态，最后用正/零/负三值专家贡献稳定融合。ADNI 保留真实可用率差异（基因组缺失率 84.4%），MIMIC-IV 使用不完整的 lab、ICD 和 demographics；论文同时报告 ECE 与计算量。

**证据边界。** evidential uncertainty 是模型代理而非真实信息价值；ADNI/MIMIC-IV 均未构成跨医院外部验证，missing mask 和 completion template 可能携带流程捷径。需要按 MCAR/MAR/MNAR、类别 × 组合 × 站点报告校准，并验证患者/访问级划分。

**研究连接。** 与 ShapKO、MMA-LTS 和 EMMS 组合，明确区分“观测到但低质量”“结构性缺失”“有信息但与当前专家冲突”三种状态；只有质量分数能预测真实新增模态带来的风险下降时，才把它用于检查获取。

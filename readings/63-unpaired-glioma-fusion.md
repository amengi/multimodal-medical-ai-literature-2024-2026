# 非配对病理—MRI 基础模型融合：WHO 2021 胶质瘤分型

- **论文**：Multimodal fusion of pathology and radiology foundation models for WHO 2021 glioma subtyping
- **作者**：Camillo Saueressig, Daniel Scholz, Philipp Raffler, Claire Delbridge, Benedikt Wiestler, Peter Schüffler
- **出处**：npj Precision Oncology 10, 118 (2026)
- **DOI**：[10.1038/s41698-026-01366-5](https://doi.org/10.1038/s41698-026-01366-5)
- **代码**：[GitHub](https://github.com/csaueres/radio-path-glioma-subtyping)

## 简要 reading

**问题。** 病理与 MRI 患者级配对数据少，但按同一 WHO 亚型组织的单模态队列更容易获得；问题是标签配对或完全交替训练能否产生可用融合。

**方法变化。** 冻结 MRI 与 WSI 基础模型后比较 early/late fusion 和 MoE；训练使用 772 个病理病例与 959 个 MRI 病例，在 171 个未见患者级配对病例上测试。MoE 报告独立测试 AUC 0.94；同标签随机配对与 paired 训练相近，单模态推理时也不劣于对应 unimodal baseline。

**证据边界。** 标签配对只能识别类条件共享结构，不能恢复患者级交互；TCGA 配对测试与训练来源需严防患者/切片重复，类别标签可能承载主要对齐信号。注意图与 SHAP 不足以证明生物标志物或 synergy，且 171 例外测仍需更多中心复现。

**研究连接。** 与 CALM、IPIC、Identifiable SCA 联合，显式比较 label-pairing、完全 unpaired 与 0.1%–10% 配对锚点；若患者错配不影响结果，应把主张限定为 label-conditional ensemble，而非患者级跨模态交互。

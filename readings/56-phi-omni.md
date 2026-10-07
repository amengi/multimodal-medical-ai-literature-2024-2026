# Φ-OMNI：以 PID 启发的协同信息预训练病理切片

- **论文**：Synergistic Information Disentanglement for Omni-Modal Slide Representation Learning in Computational Pathology
- **作者**：Mingxin Liu, Chengfei Cai, Anwen Lu, Pengbo Xu, Jun Li, Jinze Li, Depin Chen, Jun Xu
- **出处**：MICCAI 2026，LNCS 16891
- **原文**：[MICCAI Open Access](https://papers.miccai.org/miccai-2026/1025-Paper0048.html)
- **代码**：[GitHub](https://github.com/imicjs/PhiOmni)

## 简要 reading

**问题。** WSI、转录组与病理报告被强制对齐到共同空间时，容易只保留冗余线索并丢失跨模态协同；部署时又通常只有 WSI。

**方法变化。** Φ-OMNI 用 Synergistic Information Bottleneck 与 ΦID 目标抑制边际冗余、提取高阶交互，在乳腺和肺癌 TCGA 预训练后，仅用 WSI 在五个外部数据集的八个少样本任务迁移。

**证据边界。** “grounded in PID”不等于高维连续表示中的真实 PID 被无偏估计；目标依赖所选分解与变分代理。报告可能直接包含诊断/分子线索，患者级文本清洗和切片—报告泄漏必须审计；审稿也指出缺少 MIRROR 及 Image+Gene/Image+Text 组合比较。

**研究连接。** 与 PID framework、LSMI 和 InfoBridge 组合，先在已知冗余/独有/协同真值的合成数据校准 ΦID，再检验分数是否预测“加入真实组学”带来的任务增益；若仅 WSI 提升主要来自报告标签泄漏或同中心预训练，则不能宣称协同信息蒸馏。

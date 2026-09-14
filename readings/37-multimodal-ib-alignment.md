# 信息瓶颈用于多模态表示对齐

- **论文**：Aligning Multimodal Representations through an Information Bottleneck
- **作者**：Antonio Almudévar, José Miguel Hernández-Lobato, Sameer Khurana, Ricard Marxer, Alfonso Ortega
- **出处**：ICML 2025，PMLR 267:1250–1270
- **原文**：[PMLR](https://proceedings.mlr.press/v267/almudevar25a.html)
- **代码**：[GitHub](https://github.com/antonioalmudevar/multimodal_ib)

## 简要 reading

**问题。** 对比学习提高跨模态共享信息，但不会自动删除模态特异 nuisance，因此两个表示仍可能存在 modality gap。

**方法变化。** 在对比目标之外加入由变分近似推导的表示级信息瓶颈正则，压缩模态特异信息，并用受控实验分析温度、nuisance 保留与对齐之间的关系。

**信息论边界。** 优化的是变分代理而非真实高维 MI；更高 CKA/检索对齐也不证明医学任务所需的 private 信息被正确保留。对齐过强可能删除某一检查独有的稀有病灶。

**研究连接。** 与 InfoBridge 形成一对反向控制：前者压缩模态特异内容，后者保护条件依赖。可在医学模型中按估计的 $I(X_m;Y\mid X_{-m})$ 自适应选择瓶颈强度，而不是全局固定 beta。

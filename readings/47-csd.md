# CSD：类别感知的共享/特异语义解耦

- **论文**：Towards Class-Aware Semantic Decoupling in Multi-modal Disease Diagnosis with Missing Modalities
- **作者**：Feixiang Zhou 等
- **出处**：MICCAI 2026，LNCS 16885
- **原文**：[MICCAI Open Access](https://papers.miccai.org/miccai-2026/1073-Paper1452.html)
- **代码**：未核验到公开仓库

## 简要 reading

**问题。** 全局 shared/private 解耦会把不同疾病的证据混在一起；同一模态对不同标签可能分别提供冗余、独有或冲突信息。

**方法变化。** CSD 用疾病查询在类别语义空间分别提取 shared/specific 表示，以语义相关性加权跨模态对齐，并做类别条件融合；在 IU-Xray 图文与 MIMIC 图像–表格的模拟缺失上评估到 90% missing rate。

**证据边界。** 类别查询不是正式 PID 分解，InfoNCE/MMD 与 margin 也不证明获得独有信息；缺失为对称模拟，且论文页明确指出 per-class、临床解释和真实缺失仍不足。

**研究连接。** 与 CXR-LT、EyeCLIP、LSMI 组合，把 class × modality-combination 的交互作为评价单位；先验证类别条件表示能否预测真实新增模态收益，再决定是否用于尾部路由，避免 query 仅学习标签共现先验。

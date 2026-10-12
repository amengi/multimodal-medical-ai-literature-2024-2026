# CALM：完全非配对影像—遗传数据的可解释对齐

- **论文**：CALM: Interpretable Cross-Modal Alignment for Biomarker Discovery from Unpaired Data
- **作者**：Jueqi Wang, Zachary Jacokes, John Darrell Van Horn, Kevin A. Pelphrey, Michael C. Schatz, Archana Venkataraman
- **出处**：MICCAI 2026，LNCS 16882（页码与 DOI 尚未生成）
- **原文**：[MICCAI Open Access](https://papers.miccai.org/miccai-2026/0144-Paper2961.html)
- **代码**：[GitHub](https://github.com/jueqiw/CALM)

## 简要 reading

**问题。** 大型神经影像与遗传队列常来自完全不重叠人群，既无患者级配对，也难以直接验证脑区—通路对应关系。

**方法变化。** CALM 以类条件 MMD 对齐 ASD/对照组内分布，用 supervised contrastive loss 保持诊断分离，并以正交约束的线性投影读出 ROI–pathway association。模型在 ABIDE/SSC 非配对训练，在未见的 ACE 配对队列验证；association matrix 与 paired baseline 的相关系数报告为 0.87。

**证据边界。** 类条件对齐只在标签充分消除混杂时才有解释力；MMD、对比与正交并不证明患者级对应、MI 分解或因果生物标志物。外部 paired 测试仍需站点、祖源、年龄与诊断标签泄漏控制，生物学验证目前主要是文献一致性。

**研究连接。** 把 CALM 作为路线 C 的“零锚点分布对齐”端点，与 Identifiable SCA 和少量真实配对锚点组成标度实验；用标签置换、站点匹配和锚点洗牌判断 association 是共享生物学还是 cohort shortcut。

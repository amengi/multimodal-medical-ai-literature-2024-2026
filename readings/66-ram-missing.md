# RAM-Missing：检索增强的真实缺失 CT 融合

**论文。** Fulin Li, Qing Cai, Shugang Zhang, Jinxing Li. *RAM-Missing: Retrieval-Augmented Missing-Aware Fusion for Robust Lung Cancer Subtyping*. MICCAI 2026, LNCS 16886, pp. 582–592；MICCAI 页面中的章节 DOI 仍待补充。

**实际问题。** TCGA 肺癌队列的 WSI、RNA 与 CT 并非完整三元组，75.4% 病例缺 CT；零填充或从现有模态生成单个 CT 表示，容易把不可恢复的患者独有信息伪装成证据。

**方法变化。** 方法仅从训练折完整病例建立 CT memory bank，以 WSI+RNA 查询 top-k 代理 CT；检索权重的 Shannon entropy 作为路由可靠性信号，连同缺失掩码输入条件 MoE，并只在完整病例上施加 proxy-consistency loss。作者使用 StratifiedGroupKFold 和折内 memory bank，降低患者跨折泄漏。

**证据边界。** missing-CT 子集 AUC 从约 0.509 提升到 0.564，绝对增益有限；没有独立三模态外部验证。检索 entropy 不是校准后的不确定性，也不能证明代理 CT 属于该患者；类/站点相似邻居可能把头部捷径带入尾部。

**研究连接。** 可与 IB-GPID、RMoE 和 MMA-LTS 组合：先估计 CT 相对 WSI+RNA 的可恢复冗余与不可恢复独有/协同信息，再决定“检索、直接融合或拒绝”，并以 risk–coverage 和外部站点校准而非平均 AUC 判定价值。

# PriOrGen：多器官长尾病理报告生成的先验锚定去偏

**论文。** Feng Yang, Jie Liu, Yubo Pang, Peilin Chen, Xinheng Lyu, Shiqi Wang, Howard Leung, Ping Chen. *Prior-Anchored Debiasing for Long-Tailed Multi-Organ Pathology Report Generation*. MICCAI 2026, LNCS 16891, pp. 407–417；官方页面的章节 DOI 仍待补充。

**实际问题。** 多器官 WSI–报告数据同时存在器官频率长尾、疾病概念长尾和文本模板共现偏差；普通报告生成器容易把头部器官语言先验覆盖尾部病理证据。

**方法变化。** PriOrGen 在视觉侧引入 prototype-anchored bottleneck，在文本侧建立 meta-report prior bank，再由跨模态解码器生成报告。ML-Path 含 4,686 对 WSI–报告、11 个 TCGA 癌种，头部每类约 879–977，尾部约 38–60；作者报告患者不跨划分。

**证据边界。** 尾部组相对基线的 B-M/MTR/R-L 提升约 8.9%/16.5%/10%，但证据主要是单一 TCGA 来源的自动词面指标，缺少外部中心、病理医师事实性、罕见病灶幻觉和校准评估。所谓 information bottleneck 目前应视作原型压缩结构，不是已核验的 MI/PID 估计。公开仓库存在，但本轮仅见 README，尚未核验实现代码。

**研究连接。** 可与 RadDiag、EyeCLIP 和 Neglected Tails 组合，把“器官频率 × 疾病概念 × 文本模板”拆成二维/三维长尾；用反事实模板交换和病理概念核验，区分真正的视觉尾部学习与语言先验复述。

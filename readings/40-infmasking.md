# InfMasking：以随机掩码促进协同信息

- **论文**：InfMasking: Unleashing Synergistic Information by Contrastive Multimodal Interactions
- **作者**：Liangjian Wen, Qun Dai, Jianzhuang Liu 等
- **出处**：NeurIPS 2025 Main Conference
- **DOI**：[10.52202/085713-0525](https://doi.org/10.52202/085713-0525)
- **原文**：[NeurIPS](https://proceedings.neurips.cc/paper_files/paper/2025/hash/16fe204707eac76cfd0e94296fe98cef-Abstract-Conference.html)
- **代码**：[GitHub](https://github.com/brightest66/InfMasking)

## 简要 reading

**问题。** 普通融合可能只利用容易的冗余证据，而没有学习必须联合模态才能出现的协同模式。

**方法变化。** 训练时随机遮蔽各模态大部分特征，构造大量部分交互模式，再让未遮蔽融合表示与这些表示通过 MI 代理保持一致，以近似无限掩码下的协同信息提取。

**信息论边界。** InfMasking loss 是对计算不可行 MI 目标的近似；性能提升不能单独证明 PID 意义上的 synergy 增大。医学中强遮蔽还可能鼓励捷径或抹掉小病灶。

**研究连接。** 可与真实缺失训练结合，但掩码分布应拟合临床 $p(R\mid A,S,Y)$ 而非均匀采样；用 LSMI、模态置换和新增模态干预同时验证“协同增强”是否可测且能改善最坏组校准。

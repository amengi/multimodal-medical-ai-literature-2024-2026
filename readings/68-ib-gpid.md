# IB-GPID：以 Gaussian PID 解释多组学生存融合

**论文。** Zeruo Yang, Shiqi Wu, Shujian Yu. *Information bottleneck-driven Gaussian PID enables modality-level interpretability in multimodal survival prediction*. Computer Methods and Programs in Biomedicine 286 (2026):109566. DOI: 10.1016/j.cmpb.2026.109566。

**实际问题。** 多组学生存模型的性能提升无法回答每个模态提供的是冗余、独有还是只有联合观察才出现的协同信息，也无法据此判断缺失模态是否可被安全补偿。

**方法变化。** 工作先用 information-bottleneck-driven 特征选择压缩各组学，再将连续生存靶标 Gaussianize，并用 bias-corrected Gaussian PID 分解两模态关于靶标的 redundancy、unique 和 synergy。作者在 TCGA-BRCA/LUSC 建模，并扩展到 17 个 TCGA 队列的四类分子模态对；代码仓库还提供 104 例外部乳腺癌 RNA+甲基化队列流程。

**证据边界。** 随机变量可写为两组学表示 $Z_1,Z_2$ 与 Gaussianized 生存靶标 $T$。这里计算的是依赖协方差与 Gaussian 假设的 PID atoms，不是神经 MI 下界；结果对 PID 定义、靶标变换、特征选择和小样本协方差估计敏感。需严格保证特征选择只在训练折完成，并在外部队列报告 bootstrap 稳定性。

**研究连接。** 这项工作可为 RAM-Missing/RMoE 提供“是否值得检索”的群体级先验：只有可恢复冗余占主导时才允许代理补全；独有或协同信息高时，应转向获取真实检查或选择性拒绝，并用真实 hide/reveal 收益校验 PID 排序。

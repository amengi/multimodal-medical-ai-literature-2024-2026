# SYNPRED：把“协同”拆成可检验的经验主张

- **论文**：SYNPRED: A Synergistic Approach to Multimodal Learning for Clinical Prediction
- **作者**：Ivana Janíčková, Yen Y. Tan, Thomas H. Helbich, Philipp Seeböck, Julieta Di Marco, Zsuzsanna Bago-Horvath, Ulrike Heber, Thomas Spiegel, Georg Langs
- **出处**：MICCAI 2026，LNCS 16887
- **原文**：[MICCAI Open Access](https://papers.miccai.org/miccai-2026/1029-Paper2011.html)
- **代码**：[GitHub](https://github.com/cirmuw/SYNPRED)

## 简要 reading

**问题。** 只对齐 DCE-MRI 与 RNA 的共享信息会忽视任务相关的模态特异与联合信号；部署时 RNA 又常不可得。

**方法变化。** SYNPRED 以多模态 VAE 分出 task-relevant multimodal、task-relevant unimodal 与 task-irrelevant instance-specific latent，MoE 聚合后用 task-conditioned KL/fusion 训练；在多中心 BreastDCEDL 的治疗反应预测中，多模态预训练改善 image-only 推理。

**证据边界。** 作者明确把 synergy 定义为经验增益而非正式 PID；moment-matched MoE 也不是完整生成密度。单一疾病任务、有限样本和 RNA 强模态使结论可能是蒸馏而非不可约协同；缺少 CoMM 等更贴近的基线与充分可复现细节。

**研究连接。** 把它作为 Φ-OMNI 的反例对照：同一数据上分别报告正式 PID 代理、fusion ablation 和真实新增 RNA 的风险下降；若所谓 synergy 分数不能预测单模态获益，论文主张应降级为多模态正则化。

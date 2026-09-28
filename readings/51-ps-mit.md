# PS-MIT：后验采样生成任意缺失 MRI

- **论文**：Posterior Samplings are Missing Modalities Generators for Medical Image Translation
- **作者**：Jonghun Kim
- **出处**：ECCV 2026
- **原文**：[ECCV Accepted Papers](https://eccv.ecva.net/Conferences/2026/AcceptedPapers) · [arXiv](https://arxiv.org/abs/2607.18763)
- **代码**：[GitHub](https://github.com/jongdory/PS-MIT)

## 简要 reading

**问题。** 固定 source→target 翻译需要为每种 MRI 缺失组合重训，而且多目标串行生成会累计误差。

**方法变化。** PS-MIT 学习完整模态联合 flow prior，把缺失生成写成线性逆问题；推理时以观测一致性引导后验轨迹，并用 many-to-one sampling 减少多目标误差传播。BraTS/IXI 上覆盖任意组合，并评估合成图像的肿瘤分割效用。

**证据边界。** “后验”仍受 joint prior 与 measurement model 失配影响；更高 PSNR/分割分数不证明个体病灶覆盖，公开数据缺失多由人工遮挡。必须报告多样本后验覆盖与校准，而非只给最佳样本。

**研究连接。** 与 CMCM 和 EMMS 形成三角对照：联合 latent 后验、像素后验与不生成空证据；同一 backbone/coverage 下比较 C-index/Dice、ECE、病灶 false-positive 和拒绝率，才能判断何时生成有净收益。

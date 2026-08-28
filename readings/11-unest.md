# UNest

**论文**：[Structural Attention: Rethinking Transformer for Unpaired Medical Image Synthesis](https://papers.miccai.org/miccai-2024/736-Paper0456.html)<br>
**来源**：MICCAI 2024<br>
**代码**：[HieuPhan33/MICCAI2024-UNest](https://github.com/HieuPhan33/MICCAI2024-UNest)<br>
**标签**：unpaired synthesis · MR/CT/PET · structural attention · SAM<br>

## 简要 reading

UNest 关注 Transformer 在无配对监督时缺少局部结构归纳偏置的问题。模型先利用 Segment Anything 提取主要前景结构，再把结构注意力限制在关键解剖区域，使跨模态合成优先保持器官轮廓和组织关系。论文覆盖 MR、CT、PET 间六个合成任务，并报告相对近期方法的改善。

## 证据与疑问

- 优点：把非配对合成失败归因到结构归纳偏置，而不是简单增加循环一致性损失。
- 风险：SAM 的前景掩码若遗漏小病灶，结构注意力可能进一步抑制这些区域。
- 常用 PSNR/SSIM 或分布指标不能证明病理真实性；需要病灶保持率和下游临床任务验证。

## 可迁移启发

非配对合成应将“解剖守恒”和“病理守恒”分开评价，并设置不能由模型随意改变的病灶级约束。

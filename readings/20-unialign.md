# UNIALIGN

**论文**：[UNIALIGN: Scaling Multimodal Alignment within One Unified Model](https://openaccess.thecvf.com/content/CVPR2025/html/Zhou_UNIALIGN_Scaling_Multimodal_Alignment_within_One_Unified_Model_CVPR_2025_paper.html)<br>
**来源**：CVPR 2025<br>
**代码**：论文页面称将发布，当前未核验<br>
**标签**：unpaired data · universal alignment · MoE · LoRA · distillation<br>

## 简要 reading

UNIALIGN 用一个共享编码器处理图像、文本、音频和点云等六类模态，结合模态感知 MoE 与 LoRA 控制参数增长。soft modality binding 利用跨数据集非配对样本，anchor modality 和已有多模态模型的蒸馏信号负责把各模态拉入统一空间。

## 证据与疑问

- 优点：提供了跨数据集利用非配对单模态资产的可扩展方案，训练参数仅约 7.8M。
- 风险：对 anchor 和教师模型依赖较强，教师偏差可能被传播到所有模态。
- 统一空间中的接近不一定代表临床语义一致，可能只对 benchmark retrieval 有利。

## 医学启发

可用放射报告或诊断编码作为锚点，连接不同医院中互不配对的 MRI、CT、病理和 EHR，但需防止标签泄漏。

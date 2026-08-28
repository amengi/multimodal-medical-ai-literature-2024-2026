# TITAN

**论文**：[A multimodal whole-slide foundation model for pathology](https://www.nature.com/articles/s41591-025-03982-3)<br>
**来源**：Nature Medicine 2025<br>
**代码**：[mahmoodlab/TITAN](https://github.com/mahmoodlab/TITAN)<br>
**标签**：whole-slide pathology · vision-language · rare cancer · retrieval · report generation<br>

## 简要 reading

TITAN 的三阶段训练包括：在 335,645 张 WSI 上做视觉自监督；对齐 423,122 个 ROI 与 PathChat 生成的细粒度描述；再对齐约 183,000 对 WSI 与病理报告。模型输出通用 slide embedding，可用于线性探测、少样本/零样本分类、罕见癌症检索、预后和报告生成。

## 证据与疑问

- 优点：把 patch 级基础模型能力提升到整张 WSI，并系统测试低数据和罕见病场景。
- 风险：大量合成描述可能把 PathChat 的知识盲点和语言偏差蒸馏进视觉表征。
- rare retrieval 的良好表现不等同于对罕见癌症进行可靠诊断，仍需病例级特异度与临床审核。

## 可迁移启发

合成文本可缓解配对报告不足，但必须设置真实报告对齐、合成描述质量和去除合成数据三类消融。

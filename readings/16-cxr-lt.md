# CXR-LT 2024

**论文**：[CXR-LT 2024: A MICCAI challenge on long-tailed, multi-label, and zero-shot disease classification from chest X-ray](https://pubmed.ncbi.nlm.nih.gov/40735106/)<br>
**来源**：Medical Image Analysis 2025<br>
**标签**：chest X-ray · long-tail · multi-label · zero-shot · benchmark<br>

## 简要 reading

CXR-LT 2024 是胸片长尾、多标签和零样本疾病识别挑战的总结论文。它扩展疾病覆盖范围，统一评价罕见类别与未见类别，并整理参赛方法，包括视觉–语言模型、生成式增强、噪声标签处理和零样本策略。

## 证据与疑问

- 价值：为长尾医学分类提供共同数据、划分和指标，是方法比较的重要起点。
- 边界：主要输入仍是单一胸片模态；多模态成分往往来自文本知识或预训练，而非病例级多检查融合。
- 多标签任务中类别共现可能成为捷径，尾类提升不一定来自真正识别尾类影像征象。

## 可迁移启发

多模态长尾基准应同时提供图像、报告、EHR 和真实检查缺失掩码，并按疾病频率和模态组合频率进行二维分层评价。

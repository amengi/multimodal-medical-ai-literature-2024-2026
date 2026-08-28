# 检索与证据说明

## 科学问题

多模态医学模型如何在以下现实条件下可靠工作：模态异质、训练或推理阶段模态缺失、疾病类别及模态组合呈长尾分布、跨模态样本不能逐例配对。

## 检索策略

- 时间：2024-08-28—2026-08-28。
- 医学来源：Nature、Nature Medicine、Nature Communications、Medical Image Analysis、npj Digital Medicine、MICCAI、MIDL。
- 通用 AI 来源：CVPR、ICCV、NeurIPS、ACM MM、WACV。
- 关键词族：`missing modality`、`incomplete multimodal`、`modality dropout`、`modality imputation`、`long-tailed multimodal`、`modality combination imbalance`、`unpaired multimodal`、`shared private representation`、`multimodal medical fusion`。
- 优先引用出版社、会议 proceedings、CVF、PMLR 和 MICCAI Open Access 页面。

## 纳入标准

1. 正式同行评议论文优先；仅预印本的工作不进入主清单，除非已明确标注后续会议版本。
2. 至少直接覆盖一个目标问题，或对医学研究具有明确可迁移性。
3. 将 arXiv 与正式版本去重，优先链接正式版本。
4. 不把普通类别不平衡自动视为“多模态长尾”；需考察其是否分析跨模态交互。

## 阅读边界

这些是定向简读，不等同于逐公式复现。对于未公开数据、未报告统计显著性或只在模拟缺失上验证的工作，笔记会明确指出证据边界。

## 三种“长尾”

- **类别长尾**：罕见疾病或标签样本少。
- **模态频率不平衡**：不同检查模态被获取的概率不同。
- **模态组合长尾**：少数模态组合占据大多数患者，某些组合非常稀有。

三者的优化对象不同，不应只用统一的重采样或加权损失处理。

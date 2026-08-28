# 检索与证据说明

## 科学问题

多模态医学模型如何在以下现实条件下可靠工作：模态异质、训练或推理阶段模态缺失、疾病类别及模态组合呈长尾分布、跨模态样本不能逐例配对。

## 检索策略

- 时间：2024-08-28—2026-08-28。
- 医学来源：Nature、Nature Medicine、Nature Communications、Medical Image Analysis、npj Digital Medicine、MICCAI、MIDL。
- 通用 AI 来源：CVPR、ICCV、NeurIPS、ACM MM、WACV。
- 关键词族：`missing modality`、`incomplete multimodal`、`modality dropout`、`modality imputation`、`long-tailed multimodal`、`modality combination imbalance`、`unpaired multimodal`、`shared private representation`、`multimodal medical fusion`。
- 信息论关键词族：`multimodal information bottleneck`、`conditional mutual information multimodal`、`partial information decomposition multimodal`、`modality competition mutual information`、`redundancy uniqueness synergy`。
- 优先引用出版社、会议 proceedings、CVF、PMLR 和 MICCAI Open Access 页面。

## 纳入标准

1. 正式同行评议论文优先；仅预印本的工作不进入主清单，除非已明确标注后续会议版本。
2. 至少直接覆盖一个目标问题，或对医学研究具有明确可迁移性。
3. 将 arXiv 与正式版本去重，优先链接正式版本。
4. 不把普通类别不平衡自动视为“多模态长尾”；需考察其是否分析跨模态交互。
5. 信息论条目必须说明实际优化的是 MI、条件 MI、变分界、对比下界还是仅借用了瓶颈结构；不把代理损失写成形式保证。

## 阅读边界

这些是定向简读，不等同于逐公式复现。对于未公开数据、未报告统计显著性或只在模拟缺失上验证的工作，笔记会明确指出证据边界。

链接于 2026-08-28 重新核验。优先使用正式落地页而非直接 PDF；集中入口见 [paper-links.md](paper-links.md)。部分出版社或 OpenReview 页面可能有地区、Cookie 或浏览器验证限制，因此保留 PubMed、项目页或代码作为备用入口。

## 三种“长尾”

- **类别长尾**：罕见疾病或标签样本少。
- **模态频率不平衡**：不同检查模态被获取的概率不同。
- **模态组合长尾**：少数模态组合占据大多数患者，某些组合非常稀有。

三者的优化对象不同，不应只用统一的重采样或加权损失处理。

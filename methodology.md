# 检索与证据说明

## 科学问题

多模态医学模型如何在以下现实条件下可靠工作：模态异质、训练或推理阶段模态缺失、疾病类别及模态组合呈长尾分布、跨模态样本不能逐例配对。

## 检索策略

- 时间：滚动 24 个月；本轮为 2024-09-28—2026-09-28。
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

链接于 2026-09-28 重新核验。优先使用正式落地页而非直接 PDF；集中入口见 [paper-links.md](paper-links.md)。部分出版社或 OpenReview 页面可能有地区、Cookie 或浏览器验证限制，因此保留 PubMed、PMC、项目页或代码作为备用入口。

## 三种“长尾”

- **类别长尾**：罕见疾病或标签样本少。
- **模态频率不平衡**：不同检查模态被获取的概率不同。
- **模态组合长尾**：少数模态组合占据大多数患者，某些组合非常稀有。

三者的优化对象不同，不应只用统一的重采样或加权损失处理。

## 2026-09-14 周检索记录

- **检索式族**：精确任务（missing/incomplete modality）、同义扩展（modality dropout/imputation/absence）、方法导向（information bottleneck/conditional MI/copula/PID/synergy）、venue 导向（CVPR 2026、ICML/NeurIPS 2025、MICCAI 2025）、综述/benchmark。
- **权威来源**：CVF Open Access、PMLR、NeurIPS Proceedings、MICCAI Open Access、Nature/npj Digital Medicine、PubMed/PMC；代码仅在论文页或对应公开仓库可交叉确认时记录。
- **筛选**：标题/摘要候选 24 篇；去除已收录、非目标问题、只有普通融合而无现实缺失/长尾/非配对机制、以及元数据不足条目后，纳入 8 篇。
- **年份处理**：NSCLC 工作以 npj Digital Medicine 2026 正式在线版本替代 2026-01 预印本；其余均按正式 proceedings 或期刊年份记录。

## 2026-09-21 周检索记录

- **检索式族**：精确任务（missing/incomplete modality medical）、同义扩展（modality dropout/imputation/distillation）、方法导向（information bottleneck/conditional MI/synergy/alignment）、venue 导向（ICLR/CVPR 2026、MICCAI 2025、MedIA/TPAMI）、综述与 benchmark。
- **权威来源**：OpenReview/ICLR、Medical Image Analysis/PubMed、IEEE TPAMI DOI/PubMed、CVF、PMLR、MICCAI Open Access；代码仅在论文正文、PubMed 或作者仓库可交叉确认时记录。
- **筛选**：标题/摘要候选 19 篇；排除已收录、仅预印本、普通融合但未分析目标机制、非高价值 venue 与元数据不足条目后，纳入 4 篇。
- **本轮新增**：SMSN（医学顺序信息瓶颈）、AdaMM（缺失 MRI 蒸馏与六类策略比较）、AFM2（基础模型缺失模态生成 benchmark）、Fusion–Alignment（动态融合/对齐与弱模态激活）。
- **状态处理**：AdaMM 以 MedIA 2026 正式版本替代 arXiv；AFM2 与 Fusion–Alignment 以 TPAMI DOI/期刊状态为准；SMSN 以 ICLR 2026 正式 OpenReview 条目为准。

## 2026-09-28 周检索记录

- **检索式族**：精确任务（missing modality multimodal medical）、同义扩展（incomplete/dropout/imputation）、方法导向（information bottleneck/conditional MI/evidential/posterior sampling）、venue 导向（MICCAI/ECCV 2026）、问题导向（unpaired/weakly paired/long-tail/uncertainty）。
- **权威来源**：MICCAI Open Access、ECCV 官方 accepted-papers 列表、IEEE TMI DOI、PubMed 与论文作者代码仓库；MICCAI DOI 尚未生成时保留官方论文落地页。
- **筛选**：标题/摘要候选 31 篇；排除已收录、普通融合、仅低价值预印本、元数据或方法边界无法核验者后，纳入 8 篇。
- **本轮新增**：EMMS、BrainAnytime、CSD、ProMoE-FL、UniBrain、OT-Coupled Flow、PS-MIT、MUST-VS。
- **证据处理**：区分真实与模拟缺失、完全无配对与不完整配对、分布级伪对应与患者级恢复；代码只在官方论文页或公开仓库可交叉确认时标记为已核验。

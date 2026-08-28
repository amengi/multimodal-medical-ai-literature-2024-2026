# MUSK

**论文**：[A vision–language foundation model for precision oncology](https://www.nature.com/articles/s41586-024-08378-w)<br>
**来源**：Nature 2025<br>
**代码**：[lilab-stanford/MUSK](https://github.com/lilab-stanford/MUSK)<br>
**标签**：pathology · vision-language · unpaired pretraining · masked modeling · precision oncology<br>

## 简要 reading

MUSK 用统一掩码建模分别吸收大规模非配对病理图像和专业文本：5000万张病理图像来自 11,577 位患者，文本规模约 10 亿 token；随后再使用约 100 万图文对做跨模态对齐。模型在检索、VQA、分类、分子标志物、复发、预后和免疫治疗响应等 23 个任务上评估。

其核心价值不是完全消除配对需求，而是证明大部分表征学习可以利用非配对单模态资产，只把稀缺配对数据用于最终对齐。

## 证据与疑问

- 优点：任务跨度和临床终点广，包含多种低数据和零样本设置。
- 关键边界：MUSK 不是纯 unpaired 方法；跨模态语义对齐仍依赖百万级配对样本。
- 风险：病理文本分布与目标医院报告风格不同，可能带来语言捷径和站点偏差。

## 可迁移启发

医学非配对预训练可以采用“单模态规模化预训练＋少量高质量配对校准”，并系统研究配对比例与性能、校准和尾部病种之间的标度关系。

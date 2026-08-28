# OMIB

**论文**：[Learning Optimal Multimodal Information Bottleneck Representations](https://proceedings.mlr.press/v267/wu25x.html)<br>
**来源**：ICML 2025<br>
**代码**：未核验<br>
**标签**：information bottleneck · modality imbalance · variational bound · multimodal fusion<br>

## 简要 reading

OMIB 质疑常见多模态信息瓶颈中凭经验选择正则权重的做法。论文推导达到最优多模态信息瓶颈时正则系数应满足的范围，并对不同模态动态调节权重，以防任务信息较少或优化较慢的模态被强模态掩盖。

## 信息论检查

- 随机变量是多模态输入、联合表示和任务标签；目标同时压缩输入信息并保留任务相关信息。
- 实际训练使用变分近似，因此理论最优性依赖变分族和优化是否足够表达。
- “模态信息较少”不等于“模态无用”；条件独有信息可能在边缘 MI 较低时仍然关键。

## 医学启发

可把每个 MRI 序列、组学层或检查组合的瓶颈系数设为可学习量，并在 head/tail 疾病与 head/tail 模态组合上检验是否真正改善弱模态，而不是只提升平均指标。

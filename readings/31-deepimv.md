# DeepIMV

**论文**：[A Variational Information Bottleneck Approach to Multi-Omics Data Integration](https://proceedings.mlr.press/v130/lee21a.html)<br>
**来源**：AISTATS 2021（较早，但直接连接信息瓶颈、医学多组学与缺失模态）<br>
**代码**：未核验<br>
**标签**：variational information bottleneck · incomplete multi-view · multi-omics · product of experts<br>

## 简要 reading

DeepIMV 对各组学视图的边缘表示和联合表示分别施加变分信息瓶颈，并用 Product-of-Experts 将任意已观测视图组合成联合后验，从而在不同缺失模式下共享一个预测框架。

## 信息论检查

- 目标近似最大化表示与标签的 MI，同时用 KL 项限制表示携带的输入信息。
- PoE 在多个专家一致时会迅速变得尖锐；模态冲突、批次效应或错误置信度可能导致过度自信。
- 缺失组学的获取机制若与病情相关，忽略缺失掩码会产生选择偏差。

## 当前研究启发

它是把 OMIB、真实 MNAR 和医学多组学连接起来的好基线。可加入模态质量温度、缺失倾向模型和校准项，检验 PoE 是否在尾部组合上过度自信。

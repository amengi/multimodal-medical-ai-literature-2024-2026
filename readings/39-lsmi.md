# LSMI：样本级多模态信息交互估计

- **论文**：Efficient Quantification of Multimodal Interaction at Sample Level
- **作者**：Zequn Yang, Hongfa Wang, Di Hu
- **出处**：ICML 2025，PMLR 267:71302–71317
- **原文**：[PMLR](https://proceedings.mlr.press/v267/yang25aj.html)
- **代码**：[GitHub](https://github.com/GeWu-Lab/LSMI_Estimator)

## 简要 reading

**问题。** 群体平均 PID 无法直接告诉路由器某个病例更依赖冗余、独有还是协同信息。

**方法变化。** LSMI 从 pointwise information 出发，先估计较可分解的样本级 redundancy，再以适配连续分布的高效熵估计扩展到一般交互；作者展示了样本分区、蒸馏和集成用途。

**信息论边界。** “样本级 interaction”高度依赖密度/熵估计、表示尺度和训练分布；它不是患者级因果解释，也不自动等同于某模态的临床价值。医学应用前必须先在已知生成机制的合成数据校准偏差和方差。

**研究连接。** 它为路线 D 提供了缺失的控制信号候选：用样本级交互选择 late fusion、private branch 或 cross-attention，但路由标签必须通过真实模态新增/屏蔽干预验证。

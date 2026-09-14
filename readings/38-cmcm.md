# CMCM：变分 Copula 跨模态对齐

- **论文**：Cross-Modal Alignment via Variational Copula Modelling
- **作者**：Feng Wu, Tsai Hor Chan, Fuying Wang, Guosheng Yin, Lequan Yu
- **出处**：ICML 2025，PMLR 267:67128–67146
- **原文**：[PMLR](https://proceedings.mlr.press/v267/wu25d.html)
- **代码**：[GitHub](https://github.com/HKU-MedAI/CMCM)

## 简要 reading

**问题。** 拼接或 Kronecker product 难以表达多模态潜变量的高阶联合依赖，也难以在缺失时形成一致的条件分布。

**方法变化。** 各模态边缘用 Gaussian mixture 建模，再以 Copula 连接联合分布；联合模型既用于对齐，也用于生成缺失模态表示。论文在公开 MIMIC 数据上验证。

**证据边界。** Copula 把边缘与依赖分开，但 Gaussian-mixture 边缘和所选 Copula 家族仍是强结构假设；潜表示拟合优度不等同于患者级缺失值可识别。需检查患者/住院划分、时间泄漏和自然缺失机制。

**研究连接。** 可把路线 B 从单点 latent completion 升级为条件分布：比较 Copula 后验区间是否覆盖完整病例真实 latent，并以校准、风险覆盖和尾部亚组失败决定是否拒绝补全。

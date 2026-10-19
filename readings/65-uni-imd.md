# Uni-IMD：统一的不完整多模态医学诊断

**论文。** Chongwen Lyu, Kai Han, Jun Chen, Jiaqi Zhang, Qiaoying Teng, Wei Xu, Zhe Liu. *A unified medical incomplete multimodal diagnosis framework based on optimal feature disentanglement*. Pattern Recognition, online 2026，卷期封面年为 2027，183(B):115047. DOI: 10.1016/j.patcog.2026.115047。

**实际问题。** 完整与缺失病例常被不同网络或不同缺失组合分支处理，参数量随模态数增长，并可能让共享表示混入模态特异噪声。

**方法变化。** Uni-IMD 用同一双模式架构处理完整与不完整输入，将特征拆为 common/specific 部分，以互信息最小化代理约束二者，并用最优传输净化共享特征、重建缺失表示；网络对数量随模态数线性增长。

**证据边界。** 论文在 Indiana 胸片–报告数据和私有 MLLC 数据上验证。患者级划分、缺失是自然发生还是由完整样本模拟、MI 估计器的偏差与跨站点泛化仍需按正文/代码进一步复核；本轮未核验到公开代码。标题中的“optimal”不应被理解为全局最优或可识别的信息分解。

**研究连接。** 可与 DRIM/InfoBridge 组合：先用真实 hide/reveal 干预检验 common/specific 分解能否预测新增模态的条件收益，再决定 OT 对齐强度；若 MI 代理与干预收益不一致，就应把它降级为表示正则而非信息论解释。

# ShapKO：用 Shapley 效用动态决定模态 knockout

- **论文**：ShapKO: Shapley-Adaptive Modality Knockout for Robust Multimodal Learning
- **作者**：Nusrat Binta Nizam, Fengbei Liu, Sunwoo Kwak, Minh Nguyen, Ruining Deng, Mert R. Sabuncu
- **出处**：MICCAI 2026，LNCS 16896
- **原文**：[MICCAI Open Access](https://papers.miccai.org/miccai-2026/0956-Paper3767.html)
- **代码**：[GitHub](https://github.com/sumona00/ShapKO)

## 简要 reading

**问题。** 固定 modality dropout 不能随训练中模态效用变化，强模态仍可能主导优化，使弱模态在测试缺失时不可用。

**方法变化。** ShapKO 周期性在验证集上评估所有模态子集，以任务指标定义 coalition utility，计算模态 Shapley value，再提高强模态的 knockout 概率；无需改变融合架构，并在前列腺 MRI、MIMIC 多任务和四模态生存任务上验证。

**证据边界。** Shapley value 是当前模型与验证分布下的平均边际效用，不是互信息、因果贡献或个体检查价值；精确子集枚举随模态数指数增长。结构性缺失和人工 knockout 使用不同占位符时，模型可能学习检查流程捷径，且实验尚未直接覆盖真实 MNAR 与最坏组合优化。

**研究连接。** 与 UniMIX-AD、BALM、LSMI 组合：用 ShapKO 提供群体级训练分布，用真实新增模态干预监督病例级路由，并比较平均效用、最坏组效用和条件信息代理；若 knockout 轨迹不能预测外部中心的边际收益，就只把它视为优化启发式。

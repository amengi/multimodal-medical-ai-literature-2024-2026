# ANGA：Anchor-Guided Gradient Alignment

- **论文**：Anchor-Guided Gradient Alignment for Incomplete Multimodal Learning
- **作者**：Zhi-Hao Guan, Longfei Huang, Yang Yang
- **出处**：CVPR 2026，pp. 37896–37905
- **原文**：[CVF](https://openaccess.thecvf.com/content/CVPR2026/html/Guan_Anchor-Guided_Gradient_Alignment_for_Incomplete_Multimodal_Learning_CVPR_2026_paper.html)
- **代码**：论文页称已公开，但本轮未核验到稳定仓库地址

## 简要 reading

**问题。** 严重缺失时，检索/重建样本数量可能压过完整样本，使优化方向被低可靠伪模态主导。

**方法变化。** ANGA 先检索相似实例补充缺失模态，再用熵驱动课程构造含完整样本的优化锚点，并把重建样本梯度向锚点方向校准；动态 prompt adapter 继续利用检索语义。

**证据边界。** 主要实验是 HateMemes、MM-IMDb、Food-101 等非医学图文数据；缺失机制为构造设定。熵只表示模型置信度，不等同于重建内容真实或临床安全。

**研究连接。** 可与 PASSION/BALM 的模态梯度平衡及路线 B 的拒绝机制结合：只有重建后验可靠且梯度不与完整病例冲突时才参与更新；在医学数据中必须增加病灶保持、患者级划分和真实缺失验证。

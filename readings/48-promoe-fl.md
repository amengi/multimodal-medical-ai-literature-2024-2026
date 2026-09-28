# ProMoE-FL：跨机构原型引导的缺失模态 MoE

- **论文**：ProMoE-FL: Prototype-conditioned Mixture of Experts for Multimodal Federated Learning with Missing Modalities
- **作者**：Aavash Chhetri, Bibek Niroula, Eduard Vazquez, Yash Raj Shrestha, Prashnna Gyawali, Loris Bazzani, Binod Bhattarai
- **出处**：MICCAI 2026
- **原文**：[MICCAI Open Access](https://papers.miccai.org/miccai-2026/0817-Paper1724.html)
- **代码**：[GitHub](https://github.com/bhattarailab/ProMoE-FL)

## 简要 reading

**问题。** 不同医院既有 non-IID 分布，又可能系统性缺少影像或报告；单一跨模态生成器容易把头部站点原型当成所有人的替代。

**方法变化。** ProMoE-FL 建立 client-aware global prototype bank，并用模态方向与原型条件的 MoE 合成缺失特征；在 MIMIC-CXR、NIH Open-I、PadChest、CheXpert 的同质/异质联邦划分上验证，无需额外公共数据。

**证据边界。** 这是特征合成而非患者真实报告恢复；共享原型可能泄漏站点或稀有亚组统计，并强化大客户端偏差。论文评审也指出与既有 feature-imputation FL 的区别偏增量。

**研究连接。** 把原型贡献拆成 site、disease 和 modality 三层，并让 EMMS 式 vacuous evidence 在原型冲突时触发回退；报告最坏客户端、tail label、校准和成员/属性泄漏，而不只看全局平均 AUC。

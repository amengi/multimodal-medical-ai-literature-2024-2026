# GMENet：多中心不完整 MRI 的生成式专家融合

- **论文**：Generative Mixture of Experts Network for Multi-Center Glioma Diagnosis with Incomplete Imaging Sequences
- **作者**：Pengfei Song, Fangjin Liu, Wenwen Zeng, Yonghuang Wu, Chengqian Zhao, Feiyu Yin, Xuan Xie, Jinhua Yu
- **出处**：IJCAI 2026，AI and Health，6877–6885
- **DOI**：[10.24963/ijcai.2026/765](https://doi.org/10.24963/ijcai.2026/765)
- **代码**：[GitHub](https://github.com/spf-sd/GMENet)

## 简要 reading

**问题。** 多中心胶质瘤 MRI 中 T1c/FLAIR 序列不完整会迫使 complete-case 训练丢弃大量病例，也使跨中心分布偏移与缺失机制纠缠。

**方法变化。** GMENet 用 cross-attention gated generation 在特征层补全缺失序列，以 MSE、KL 与 cycle consistency 预训练并冻结生成器，再用 confidence-aware MoE 联合预测 IDH、1p/19q 与病理类型。六中心 1,241 例使可用训练数据相对 complete-case 增加 97%。

**证据边界。** 生成器主要由完整病例随机遮挡学习，而现实缺失可能为 MAR/MNAR；cycle consistency 不证明患者级病灶语义真实。需核查患者级切分、各中心缺失率与类别交叉、生成特征的病灶幻觉、校准和真正留一中心外测。

**研究连接。** 与 PS-MIT、EMMS、QA-MoE 组合：把单点补全改成多样本后验，并以空证据和低质量拒绝作为零假设；若补全分支在相同 coverage 下不优于 observed-only MoE，就关闭生成路径。

# BrainAnytime：任意可用脑影像预训练

- **论文**：BrainAnytime: Anatomy-Aware Cross-Modal Pretraining for Brain Image Analysis with Arbitrary Modality Availability
- **作者**：Guangqian Yang, Tong Ding, Wenlong Hou, Yue Xun, Ye Du, Qian Niu, Shujun Wang, ADNI
- **出处**：MICCAI 2026，Oral，LNCS 16880
- **原文**：[MICCAI Open Access](https://papers.miccai.org/miccai-2026/0119-Paper3498.html)
- **代码**：[GitHub](https://github.com/guangqianyang/BrainAnytime)

## 简要 reading

**问题。** 临床脑影像按升级路径获取，T1、T2、FLAIR 与 amyloid-PET 的可用组合高度不均衡；固定输入模型不能复用大量不完整扫描。

**方法变化。** BrainAnytime 在五个数据源、34,899 个 3D scans 上训练共享 Multi-MAE3D，以 reciprocal cross-modal distillation 学 MRI–PET 对应，并用 atlas-guided curriculum masking 强调 AD 易损区域；单模型接受任意模态子集。

**证据边界。** 下游重点仍是 ADNI；AD/Braak 先验、MNI 配准和 MRI 序列分组可能限制疾病迁移并掩盖序列独有信息。预训练数据跨队列时必须核查同一患者、重复扫描和下游 split 泄漏。

**研究连接。** 它可作为路线 A 的强预训练主干，但不要把 atlas 权重当作信息价值；用真实新增检查计算边际收益，并比较 atlas、质量、组合频率和 CMI 代理谁能预测外部中心的 tail-combination 改善。

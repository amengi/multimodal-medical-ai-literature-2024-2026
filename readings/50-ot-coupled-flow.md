# OT-Coupled Flow：无配对 CT→TEE 模拟

- **论文**：OT-Coupled Flow: Towards Realistic TEE Simulation via Unpaired Cross-Modality Translation with Anatomical Consistency
- **作者**：Yunhao Li, Yidan Feng, Ho-On Alston Conrad Chiu, Simon Cheung-Chi Lam, Yan Pang, Qiong Wang, Chun-Ka Wong, Jing Qin
- **出处**：MICCAI 2026，LNCS 16893
- **原文**：[MICCAI Open Access](https://papers.miccai.org/miccai-2026/0750-Paper0555.html)
- **代码**：[GitHub](https://github.com/yunhaoli24/OTC-Flow)

## 简要 reading

**问题。** 静态 3D CT 与动态、操作者依赖的 2D TEE 天然无法逐例严格配对，普通无配对翻译又可能牺牲解剖对应。

**方法变化。** OTC-Flow 在 TEE 数据上预训练 adversarial VQ-VAE，以最优传输为 CT 条件特征和 TEE latent 建立伪对应，再做 flow matching，并用 CT 几何构造无标签 anatomical consistency loop。

**证据边界。** OT coupling 选择的是代价最小伪对应，不保证患者级语义可识别；报告缺少标准差、运行时与真实 TEE 下游泛化。高感知质量不能证明探头运动或病变形态真实。

**研究连接。** 可把路线 C 的少量配对锚点加入 OT plan：比较 0、0.1%、1%、5% anchors，并做锚点洗牌、病变注入和操作者/设备外测；若伪对应对锚点错误不敏感，就不能宣称患者级跨模态恢复。

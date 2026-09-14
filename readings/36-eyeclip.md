# EyeCLIP：多模态眼科视觉–语言基础模型

- **论文**：A Multimodal Visual–Language Foundation Model for Computational Ophthalmology
- **作者**：Danli Shi, Weiyi Zhang, Jiancheng Yang 等
- **出处**：npj Digital Medicine 8, 381 (2025)；发表 2025-06-21
- **DOI**：[10.1038/s41746-025-01772-2](https://doi.org/10.1038/s41746-025-01772-2)
- **全文**：[PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC12181238/)
- **代码**：[GitHub](https://github.com/Michi-3000/EyeCLIP)

## 简要 reading

**问题。** 眼科真实数据跨 11 类检查模态，文本只覆盖少量患者，稀有疾病又处于视觉、文本和共现三重长尾。

**方法变化。** 单一视觉编码器结合图像自重建、多检查图像对比和分层图文对比，在 2,777,593 张图像、11,180 份报告和 128,554 名患者上预训练，并在 14 个数据集评估零样本、少样本、检索和 VQA。

**证据边界。** 多模态病例并非都完整配对；共享表示的成功不能证明保留了罕见模态的独有信息。训练人群以中国队列为主，论文已报告跨族群性能差异；代码仓库 2026-02 修复过文本编码器权重，旧 checkpoint 不应继续使用。

**研究连接。** 可作为路线 E 的强医学骨干，但要把类别频率、模态频率、文本提及频率和图文共现频率分别分桶，并用 LSMI/模态屏蔽验证稀有病提升究竟来自视觉证据、共享语义还是语言先验。

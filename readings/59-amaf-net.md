# AMAF-Net：真实临床变量缺失与类别长尾联合建模

- **论文**：Missingness-Aware Multimodal Learning for Four-Class Adrenal Tumor Classification
- **作者**：Dehua Chen, Jing Fang, Qihong Wu, Pengfei Xia, Huimin An
- **出处**：MICCAI 2026，LNCS 16885
- **原文**：[MICCAI Open Access](https://papers.miccai.org/miccai-2026/0660-Paper1243.html)
- **代码**：[GitHub](https://github.com/fj-sunny/AMAF-Net)

## 简要 reading

**问题。** 真实肾上腺肿瘤队列同时存在结构化临床变量缺失与四类别不平衡，常规插补和总体准确率会掩盖少数肿瘤失效。

**方法变化。** AMAF-Net 显式编码临床缺失模式，用 reliability descriptor 调节 CT、临床和交互分支权重；分布感知 prototype regularization 同时压缩类内、扩大类间距离。在 1,108 名单中心患者上报告 macro-F1、balanced accuracy 和少数类 recall 改善。

**证据边界。** 单中心回顾队列的缺失模式可能直接编码临床流程与标签，必须做禁止 mask 输入和 propensity 敏感性分析；prototype margin 可能让极少数类过拟合。尚缺外部中心、时间切分、缺失变量机制和类别 × missing-pattern 交叉置信区间。

**研究连接。** 它是路线 A 的现实基准：把疾病长尾、变量缺失率与组合长尾同时分桶，并与 class-balanced loss、missing indicator、简单 late fusion 比较；若去掉 CT/临床值后只靠 missing mask 仍很强，就说明模型学到的是工作流捷径。

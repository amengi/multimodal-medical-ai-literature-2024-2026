# AdaMM：缺失 MRI 的自适应蒸馏

- **论文**：No Modality Left Behind: Adapting to Missing Modalities via Knowledge Distillation for Brain Tumor Segmentation
- **作者**：Shenghao Zhu, Yifei Chen, Weihong Chen, Shuo Jiang, Guanyu Zhou, Yuanhan Wang, Feiwei Qin, Changmiao Wang, Qiyuan Tian
- **出处**：Medical Image Analysis 112:104108，2026
- **DOI**：[10.1016/j.media.2026.104108](https://doi.org/10.1016/j.media.2026.104108)
- **代码**：[GitHub](https://github.com/Quanato607/AdaMM)

## 简要 reading

**问题。** 单模态和弱模态组合尤其容易漏检或产生假阳性，而统一模型常把所有缺失组合当作同一种退化。

**方法变化。** AdaMM 为 15 种 MRI 可见组合使用适配器，并以图引导特征精炼、双瓶颈蒸馏和病灶存在性可靠性头，从完整教师向缺失学生传递结构/纹理知识。论文还系统比较生成、检索、dropout、多任务与蒸馏等六类策略。

**证据边界。** BraTS 2018/2024 与 Pretreat-MetsToBrain-Masks 上的缺失主要来自完整病例的人工组合；完整教师在真实 MNAR 队列中未必可得。15 个组合适配器也可能把组合频率差异固化进模型。

**研究连接。** 可把教师—学生差异作为“不可恢复信息”诊断，而不是继续增强蒸馏：当差异大且学生不确定时拒绝补全/分割；按 disease × modality-combination 分层校准，并以真实新增模态干预验证可靠性头。

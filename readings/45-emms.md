# EMMS：把缺失模态视为空证据

- **论文**：Evidential Fusion Network for Multimodal Survival Prediction Under Missing Modalities
- **作者**：Yucheng Xing, Hailan Mo, Zi Wang, Ling Huang, Mengling Feng
- **出处**：MICCAI 2026，LNCS 16887
- **原文**：[MICCAI Open Access](https://papers.miccai.org/miccai-2026/0355-Paper6476.html)
- **代码**：[GitHub](https://github.com/YuchengXing99/EMMS)

## 简要 reading

**问题。** WSI–RNA 生存模型在模态缺失时不仅应继续预测，还应让不确定性随证据减少而上升，而不是用伪特征制造确定性。

**方法变化。** EMMS 用 Dempster–Shafer 与 Gaussian Random Fuzzy Numbers 融合各模态生存证据，分离 aleatoric/epistemic uncertainty，并让缺失模态贡献 vacuous evidence；四个 TCGA 癌种上比较完整与多种人工缺失比例。

**证据边界。** 缺失主要由完整队列模拟，外部中心与真实 MNAR 未验证；对病理和组学预测施加对称 KL 对齐可能抹掉互补信息。公开实现使用 TITAN 特征，需严格按患者划分并审计特征/生存 split。

**研究连接。** 与自然缺失 NSCLC、CMCM 和 InfoBridge 组合：把“空证据”作为不生成基线，再检验后验补全是否在相同 coverage 下真正降低风险；若不确定性不能排序错误或跨中心失准，就不能把 evidence mass 当作临床可信度。

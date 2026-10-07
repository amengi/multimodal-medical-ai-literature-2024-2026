# MMA-LTS：按缺失组合与空间位置校准分割置信度

- **论文**：Missing Modality-Aware Calibration for Trustworthy Brain Tumor Segmentation
- **作者**：Sol Lee, Hyunji Kim, Sungrae Hong, Donghee Han, Mun Yong Yi
- **出处**：MICCAI 2026，LNCS 16882
- **原文**：[MICCAI Open Access](https://papers.miccai.org/miccai-2026/0659-Paper1236.html)
- **代码**：未核验到公开仓库

## 简要 reading

**问题。** 缺失 MRI 序列造成的过度置信取决于“缺哪一种”和肿瘤空间位置，而不是简单随可用模态数量单调变化。

**方法变化。** MMA-LTS 是冻结分割模型后的 voxel-wise temperature scaling：由模态可用性 token 与局部难度分数预测空间温度场，在 BraTS 2020 和 FeTS 2024 的多种缺失组合上改善校准而不改变分割输出。

**证据边界。** 这是 post-hoc 校准而非缺失机制建模；如果校准集中没有覆盖某个组合，线性组合 token 未必能外推。两套公开脑肿瘤数据仍以人工遮挡为主，尚缺真实临床缺失、跨扫描仪、统计比较和组合条件 coverage 保证。

**研究连接。** 与 EMMS、AdaMM、ShapKO 组合，把“哪个组合”作为校准条件，并在 disease × site × combination 上测 ECE/Brier 与 risk–coverage；再加入组合条件 conformal prediction，区分平均置信度变好与每种缺失模式都达到目标覆盖。

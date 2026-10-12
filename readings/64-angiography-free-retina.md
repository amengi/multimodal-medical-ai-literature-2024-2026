# Angiography-free：以多模态特征库支持单模态眼底诊断

- **论文**：Angiography-free diagnosis of retinal diseases via interpretable multi-modal learning
- **作者**：Jinkui Hao, Wenlong Li, Hong Qi, Yalin Zheng, Huazhu Fu, Alejandro F. Frangi, et al.
- **出处**：npj Digital Medicine 9, 491 (2026)
- **DOI**：[10.1038/s41746-026-02641-2](https://doi.org/10.1038/s41746-026-02641-2)
- **代码**：[GitHub](https://github.com/iMED-Lab/IMIG)

## 简要 reading

**问题。** FFA 侵入性强、并非总能获取；目标是在训练期使用精确配对 CFP–FFA，推理期只输入 CFP，同时避免直接合成 FFA 的病理幻觉。

**方法变化。** 该框架将共享/特异特征存入分层、疾病感知的库，推理时由 CFP 检索并完成 FFA-relevant latent，而不生成可视 FFA。内部训练涉及 14,357 张 CFP 与 88,247 张 FFA，九个公开来源的 16,569 张 CFP 用于外部验证；论文报告内部/外部 AUC 0.98/0.96。

**证据边界。** 训练要求精确配对，推理缺失是固定的 FFA-only 缺失，不代表任意 MCAR/MAR/MNAR；图像数不等于患者数，必须核验患者级切分及双眼/序列泄漏。特征库仍可能产生类原型幻觉，九源外测的标签定义与设备差异需逐源报告校准。

**研究连接。** 与 EyeCLIP、RMoE 和 EMMS 组合，把“检索到的 FFA 证据”视为带来源的不确定证据而非恢复值；以病灶存在/不存在、罕见病和跨设备 tail 为单位比较 observed-only、检索补全与拒绝策略。

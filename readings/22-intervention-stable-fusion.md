# Intervention-Stable Feature Learning

**论文**：[Multi-Modal Image Fusion via Intervention-Stable Feature Learning](https://openaccess.thecvf.com/content/CVPR2026/html/Wang_Multi-Modal_Image_Fusion_via_Intervention-Stable_Feature_Learning_CVPR_2026_paper.html)<br>
**来源**：CVPR 2026<br>
**代码**：未核验<br>
**标签**：image fusion · intervention · modality dropout · robustness<br>

## 简要 reading

该工作认为常规融合容易学习数据集相关的伪相关，因此设计三类干预：不同模态使用互补空间遮挡、相同区域随机遮挡，以及完整模态 dropout。Causal Feature Integrator 优先选择在这些干预下仍稳定的重要特征，以捕获更可靠的跨模态依赖。

## 证据与疑问

- 优点：用可操作干预检验互补性，而不是只观察注意力权重。
- “受 Pearl 启发”不等于建立了完整因果模型；人工遮挡也不一定模拟临床检查缺失。
- 融合图像的视觉质量提升不必然转化为诊断增益。

## 医学启发

可把干预改成病灶、器官、扫描协议和检查获取层面的结构化干预，并在下游分割/诊断中验证稳定特征。

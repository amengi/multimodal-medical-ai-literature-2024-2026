# BALM：不均衡缺失率下的平衡多模态学习

- **论文**：BALM: A Model-Agnostic Framework for Balanced Multimodal Learning under Imbalanced Missing Rates
- **作者**：Phuong-Anh Nguyen, Tien Anh Pham, Duc-Trong Le, Cam-Van Thi Nguyen
- **出处**：CVPR 2026，pp. 30246–30256
- **原文**：[CVF](https://openaccess.thecvf.com/content/CVPR2026/html/Nguyen_BALM_A_Model-Agnostic_Framework_for_Balanced_Multimodal_Learning_under_Imbalanced_CVPR_2026_paper.html)
- **代码**：[GitHub](https://github.com/np4s/BALM_CVPR2026)

## 简要 reading

**问题。** 各模态缺失概率不同会同时扭曲表示分布与梯度动力学，普通共享缺失率训练无法代表这一情形。

**方法变化。** Feature Calibration Module 用全局上下文校准单模态表示；Gradient Rebalancing Module 从梯度幅值和方向两侧平衡优化，可作为插件接入不同骨干。

**证据边界。** 验证集中在音频–视觉–文本情感数据，未处理临床 MNAR、疾病类别长尾、站点偏移或校准。所谓 model-agnostic 不代表医学任务上无需重调。

**研究连接。** 与 UniMIX-AD 的组合图、PASSION 的不均衡缺失和 MCR 的模态竞争直接衔接。最关键的新实验不是再报平均准确率，而是检验梯度平衡能否改善 disease tail × modality-combination tail 的最坏组风险。

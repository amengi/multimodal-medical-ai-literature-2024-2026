# M³FeCon

**论文**：[Missing as Masking: Arbitrary Cross-modal Feature Reconstruction for Incomplete Multimodal Brain Tumor Segmentation](https://papers.miccai.org/miccai-2024/520-Paper0067.html)<br>
**来源**：MICCAI 2024<br>
**代码**：未核验<br>
**标签**：brain tumor segmentation · missing modality · feature reconstruction · masking<br>

## 简要 reading

M³FeCon 将缺失 MRI 序列类比为 masked token，在特征层利用现有序列重建近似完整的跨模态表征，再执行脑肿瘤分割。与像素级生成相比，特征重建不必追求视觉逼真的 MRI，也能围绕下游分割任务优化。

## 证据与疑问

- 优点：统一处理任意输入子集，且避免把合成图像直接交给临床人员。
- 风险：特征空间没有可直接审阅的医学意义，错误重建更难被发现。
- 典型 BraTS 设置通常配准良好且缺失由人工模拟，对真实扫描协议和运动伪影的代表性有限。

## 可迁移启发

特征补全应配套异常检测或 conformal abstention；当现有模态不足以恢复关键信息时，模型需要拒绝而非强行补全。

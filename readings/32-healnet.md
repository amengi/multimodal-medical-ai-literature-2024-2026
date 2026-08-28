# HEALNet

**论文**：[HEALNet: Multimodal Fusion for Heterogeneous Biomedical Data](https://proceedings.neurips.cc/paper_files/paper/2024/hash/765871e77d2ca65126d3d64d31aa6908-Abstract-Conference.html)<br>
**代码**：[konst-int-i/healnet](https://github.com/konst-int-i/healnet)<br>
**来源**：NeurIPS 2024<br>
**标签**：heterogeneous biomedical data · WSI · multi-omics · missing modality · survival<br>

## 简要 reading

HEALNet 用共享潜空间中的混合早期融合注意力整合图像、表格和图结构数据，同时保留模态结构；模型可在训练和推理时处理缺失模态，并在四个 TCGA 癌种上进行 WSI–多组学生存分析。

## 信息论视角与疑问

HEALNet 本身不是显式 MI 方法，但很适合作为信息论诊断对象：共享潜空间究竟保存了冗余、独有还是协同信息？如果简单移除一个模态性能变化很小，可能是冗余充分，也可能是模型从未学会该模态。

## 当前研究启发

可将它作为医学融合骨架，再加入 PID/CMI 只做诊断或轻量正则，避免直接堆叠多个信息损失。必须额外检查患者级切分、TCGA 站点偏差、外部验证和生存校准。

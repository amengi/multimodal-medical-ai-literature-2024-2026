# MulModSeg

**论文**：[MulModSeg: Enhancing Unpaired Multi-Modal Medical Image Segmentation with Modality-Conditioned Text Embedding and Alternating Training](https://openaccess.thecvf.com/content/WACV2025/html/Li_MulModSeg_Enhancing_Unpaired_Multi-Modal_Medical_Image_Segmentation_with_Modality-Conditioned_Text_WACV_2025_paper.html)<br>
**来源**：WACV 2025<br>
**代码**：[ChengyinLee/MulModSeg_2024](https://github.com/ChengyinLee/MulModSeg_2024)<br>
**标签**：unpaired CT/MR · segmentation · text conditioning · alternating training<br>

## 简要 reading

MulModSeg 用冻结文本编码器生成模态条件 embedding，并以交替训练方式在互不配对的 CT 和 MR 数据集之间共享分割模型。这样既不需要患者级 CT–MR 配对，也不必为每个模态设计独立编码器/解码器。实验覆盖腹部多器官和心脏结构，并在 CNN 与 Transformer 骨干上测试。

## 证据与疑问

- 优点：改动小、训练流程清楚，适合作为 unpaired multimodal segmentation 基线。
- 模态名称文本只提供粗粒度条件，难以描述扫描协议、磁场强度、对比剂和中心差异。
- 交替训练可能学习到模态不变解剖结构，也可能只是通过数据集特征识别来源域。

## 可迁移启发

可把简单模态 prompt 扩展成结构化 acquisition prompt，并以未知中心留出实验判断模型是否真正学到可迁移模态条件。

# MADAT

**论文**：[MADAT: Missing-aware dynamic adaptive transformer model for medical prognosis prediction with incomplete multimodal data](https://pubmed.ncbi.nlm.nih.gov/41621207/)<br>
**出版社**：[Medical Image Analysis / ScienceDirect](https://www.sciencedirect.com/science/article/pii/S1361841526000277)<br>
**来源**：Medical Image Analysis, 2026<br>
**代码**：未核验<br>
**标签**：prognosis · missing modality · wavelet alignment · adaptive fusion<br>

## 简要 reading

MADAT 面向不完整多模态预后预测。其门控卷积模块提取现有模态信息，小波域对齐模块生成缺失表示，cross-agent attention 根据当前病例动态融合完整与生成模态。作者特别指出，直接重建容易产生幻觉，因此尝试在频率域约束生成过程。

实验使用三个私有鼻咽癌数据集，说明方法更接近具体临床预后场景，而不是仅在玩具数据上验证。

## 证据与疑问

- 优点：把缺失补全和动态融合放在统一框架中，并关注高频细节与低频结构。
- 局限：私有数据降低了可复现性，也难以判断预处理、缺失机制和中心差异。
- 频域一致不保证病理语义正确；仍需要病灶级和临床变量级验证。

## 可迁移启发

生成模态应同时接受频率、解剖和任务三层审计，并报告生成不确定性，而不是只用最终预后指标证明生成有效。

# Identifiable Shared Component Analysis

**论文**：[Identifiable Shared Component Analysis of Unpaired Multimodal Mixtures](https://proceedings.neurips.cc/paper_files/paper/2024/hash/e6c967a0e4168df9614a81ed4195ba78-Abstract-Conference.html)<br>
**来源**：NeurIPS 2024<br>
**代码**：未核验<br>
**标签**：unpaired multimodal · identifiability · shared/private components · distribution matching<br>

## 简要 reading

论文研究一个更基础的问题：当不同模态的样本完全不对齐时，共享潜变量是否仍可识别。作者在线性共享/私有混合模型下，通过跨模态分布差异最小化推导充分可识别条件，并讨论少量配对样本如何放宽这些条件。

## 证据与疑问

- 优点：为大量依赖“分布对齐即可得到共享语义”的应用论文提供理论边界。
- 理论主要基于线性混合、满秩及分布条件，医学影像和组学通常是复杂非线性生成过程。
- 分布匹配只能识别到一定变换等价类；没有额外结构时，语义方向仍可能不唯一。

## 医学启发

设计非配对医学模型前，应明确列出可识别性来自何种侧信息：解剖结构、疾病组标签、少量配对患者、时间顺序或因果约束。

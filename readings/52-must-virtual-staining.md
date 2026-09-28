# MUST-VS：不完整配对的多染色虚拟生成

- **论文**：MUST: Multi-Style Virtual Staining With Incomplete Pairs
- **作者**：Jiaxin Zhuang, Yao Du, Xiaoyu Zheng, Linshan Wu, Chao He, Lin Luo, Hao Chen
- **出处**：IEEE Transactions on Medical Imaging 45(9):4797–4808，2026
- **DOI**：[10.1109/TMI.2026.3709810](https://doi.org/10.1109/TMI.2026.3709810)
- **PubMed**：[PMID 42397993](https://pubmed.ncbi.nlm.nih.gov/42397993/)
- **代码**：[GitHub](https://github.com/JiaxinZhuang/MUST)

## 简要 reading

**问题。** 连续切片虽可配准，但组织退化和处理伪影会导致 patch-level 染色标签不完整；这不同于完全无配对翻译，也不同于随机缺失整种模态。

**方法变化。** MUST-VS 用 cross-modality cross-attention 条件的 latent diffusion 做 collaborative denoising，并以对比 semantic preservation 和高置信伪标签利用无 GT patches；三个病理数据集上学习多染色转换。

**证据边界。** 伪标签置信度可能复制头部组织形态偏差；结构相关染色的成功不能外推到分子信息不可由 H&E 决定的 IHC。必须按患者/切片分割，避免相邻 patch 泄漏，并核查伪染色的病理幻觉。

**研究连接。** 它为路线 C 提供“部分边存在”的 pairing graph：用锚点密度和空间可靠性决定监督、OT 伪配对或后验生成；在稀有病灶上报告配对缺失率 × 类别频率的交叉结果，而非只报总体图像质量。

# 动态融合—对齐：从模态失衡到弱模态激活

- **论文**：Understanding Multimodal Learning From Modality Fusion and Alignment Perspectives
- **作者**：Yang Yang, Fengqiang Wan, Qing-Yuan Jiang, Tianxi Zhu, Yi Xu
- **出处**：IEEE TPAMI，2026，online ahead of print
- **DOI**：[10.1109/TPAMI.2026.3729627](https://doi.org/10.1109/TPAMI.2026.3729627)
- **PubMed**：[PMID 42678858](https://pubmed.ncbi.nlm.nih.gov/42678858/)
- **代码**：未核验到公开仓库

## 简要 reading

**问题。** 只平衡各模态优化速度仍可能让弱模态没有被真正利用；融合负责完成任务，而对齐可能为弱模态提供来自强模态的正向干预。

**方法变化。** 论文从预测、表示和混合层面统一 fusion 与 alignment，并用启发式或双层优化动态选择二者强度，覆盖监督与半监督设定。

**证据边界。** 证据来自声音、表情、讽刺、手势等非医学 benchmark；对齐提升不证明保留了稀有病的模态独有信息。在缺失或站点偏移下，强模态还可能把捷径传给弱模态。

**研究连接。** 将“是否对齐”改为条件决策：仅当真实新增模态干预显示共享证据占优时对齐；条件独有信息高时保留 private branch。与 BALM 比较时要统一 backbone/compute，并报告弱模态单独性能、尾部 AUPRC 与外部校准。

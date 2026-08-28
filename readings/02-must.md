# MUST

**论文**：[MUST: Modality-Specific Representation-Aware Transformer for Diffusion-Enhanced Survival Prediction with Missing Modality](https://openaccess.thecvf.com/content/CVPR2026/html/Kim_MUST_Modality-Specific_Representation-Aware_Transformer_for_Diffusion-Enhanced_Survival_Prediction_with_Missing_CVPR_2026_paper.html)<br>
**来源**：CVPR 2026<br>
**标签**：pathology · genomics · missing modality · latent diffusion · survival prediction<br>

## 简要 reading

MUST 认为缺失模态的信息包含两部分：可由其他模态推断的共享上下文，以及真正不可替代的模态特异成分。模型通过低秩共享子空间和代数约束进行分解，再以条件潜扩散生成无法直接推断的特异表示，最后用于多模态生存预测。

与直接从病理生成基因组特征相比，这种“只生成不可恢复残差”的思路更有科学解释，也减少了生成器承担的任务范围。论文在五个 TCGA 癌症数据集上比较完整、缺病理和缺基因组三类条件。

## 证据与疑问

- 优点：问题分解清楚，明确讨论了共享信息与不可替代信息。
- 风险：所谓“模态特异”由模型约束定义，并不自动等价于真实生物特异性。
- 风险：扩散生成的潜表示可能产生对预后有利、但不存在于患者真实生物学中的信号。

## 可迁移启发

缺失模态方法不应只优化平均 C-index；还应检查生成表示的校准、病例级不确定性，以及通过真实模态回填后的反事实一致性。

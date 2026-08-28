# DRIM

**论文**：[DRIM: Learning Disentangled Representations from Incomplete Multimodal Healthcare Data](https://papers.miccai.org/miccai-2024/246-Paper1276.html)<br>
**来源**：MICCAI 2024<br>
**代码**：[Lucas-rbnt/DRIM](https://github.com/Lucas-rbnt/DRIM)<br>
**标签**：MRI · WSI · RNA-seq · methylation · shared/private representation · survival<br>

## 简要 reading

DRIM 为每个模态设置共享编码器和特异编码器。共享表示通过跨模态监督式对比目标聚合患者共同信息；特异表示通过减少其与共享表示的重叠来保留模态独有信息。可用模态被组织为可变长度序列并送入 masked Transformer，因此单一模型能处理多种缺失组合。

论文面向胶质瘤生存预测，融合 DNA methylation、RNA-seq、MRI 和 WSI。相比只重建缺失模态，它直接利用现有信息，避免把生成模态当成真实观测。

## 证据与疑问

- 优点：模态覆盖广，且固定比较方法的编码器以减少融合实验的不公平性。
- 论文答辩材料承认 C-index 相对 max fusion 的增益较小，主要优势还体现在 IBS/INBLL 校准指标。
- 信息论疑问：最小化共享与私有表示之间的互信息，可能同时删除对预后有用的协同信息；“低 MI”等于“解耦”需要更强论证。

## 可迁移启发

共享/私有分解应加入可检验的干预实验：删除共享或特异成分后，分别观察跨模态检索、单模态任务和联合任务的变化。

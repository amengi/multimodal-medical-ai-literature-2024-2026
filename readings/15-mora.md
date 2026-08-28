# MoRA

**论文**：[MoRA: LoRA Guided Multi-modal Disease Diagnosis with Missing Modality](https://papers.miccai.org/miccai-2024/532-Paper1536.html)<br>
**来源**：MICCAI 2024<br>
**代码**：[zhiyiscs/MoRA](https://github.com/zhiyiscs/MoRA)<br>
**标签**：LoRA · parameter-efficient tuning · missing modality · diagnosis<br>

## 简要 reading

MoRA 在预训练多模态模型的首个 block 中加入模态感知 LoRA：不同模态共享低维下投影，但使用各自的上投影进行特异适配。模型由当前可用模态触发相应适配器，从而以少量参数覆盖不同缺失组合。论文报告可训练参数少于完整微调的 1.6%。

## 证据与疑问

- 优点：适合资源受限场景，并把模态特异性集中在低秩适配器。
- 局限：它主要解决“如何便宜地适配缺失组合”，没有显式建模为什么缺失、缺失信息是否可恢复。
- 将适配集中在第一个 block 是否足以覆盖复杂跨模态交互，需要更系统的层位置消融。

## 可迁移启发

MoRA 很适合作为工程基线，可与真实缺失机制、质量感知门控或尾部组合专家结合，而无需全量微调基础模型。

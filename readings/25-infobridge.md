# InfoBridge

**论文**：[InfoBridge: Balanced Multimodal Integration through Conditional Dependency Modeling](https://openaccess.thecvf.com/content/ICCV2025/html/Li_InfoBridge_Balanced_Multimodal_Integration_through_Conditional_Dependency_Modeling_ICCV_2025_paper.html)<br>
**项目页**：[CUHK AIM Group / InfoBridge](https://cuhk-aim-group.github.io/InfoBridge/)<br>
**来源**：ICCV 2025<br>
**标签**：conditional mutual information · over-alignment · modality-specific information · balanced fusion<br>

## 简要 reading

InfoBridge 将融合表述为条件互信息优化：在促进跨模态共享的同时加入保护边界，避免把模态特异信息在对齐过程中抹去；条件变量用于指导上下文相关的细粒度交互。

## 信息论检查

- 相比无条件 InfoNCE，条件 MI 更接近“给定语义上下文后，一个模态还为另一个模态提供多少信息”。
- 保护边界说明“对齐越强越好”并不成立。
- 论文中的 CMI 仍依赖对比估计器和负样本构造；固定超参数不能自动保证所有医学队列都处于不过度融合的区域。

## 医学启发

把患者状态、解剖部位、采集站点或缺失掩码作为条件变量，研究何时共享信息、何时保留模态特异信号。对罕见病尤其应避免将尾部征象强行拉向头部公共语义。

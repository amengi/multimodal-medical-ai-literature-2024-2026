# PASSION

**论文**：[PASSION: Towards Effective Incomplete Multi-Modal Medical Image Segmentation with Imbalanced Missing Rates](https://arxiv.org/abs/2407.14796)<br>
**来源**：ACM Multimedia 2024<br>
**代码**：[Jun-Jie-Shi/PASSION](https://github.com/Jun-Jie-Shi/PASSION)<br>
**标签**：MRI segmentation · imbalanced missing rates · self-distillation · modality rebalancing<br>

## 简要 reading

PASSION 区分了 perfect data training 与 imperfect data training：后者在训练阶段就没有完整模态，而且不同模态的缺失率不同。方法以多模态预测作为动态教师，对每个可用单模态进行像素级和语义原型级自蒸馏；再用 relative preference 衡量某个模态相对其他模态的学习优势，据此调节任务损失和梯度更新速度。

实验覆盖 BraTS2020 和 MyoPS2020，并将模块接入多种不完整模态分割骨干，说明它更像训练策略而不是特定架构。

## 证据与疑问

- 优点：首次将“不均衡缺失率”作为独立问题明确建模，评价也按不同组合展开。
- 局限：缺失矩阵仍从公开完整数据构造，不能代表由病情、费用和医嘱决定的 MNAR 缺失。
- 隐含假设：多模态教师总比单模态可靠；如果某个模态严重伪影或配准错误，该假设可能失败。

## 可迁移启发

可以把 relative preference 从性能差扩展为带不确定性的模态价值估计，并允许高噪声模态被拒绝，而非强制所有模态向教师靠拢。

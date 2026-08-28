# SimMLM

**论文**：[SimMLM: A Simple Framework for Multi-modal Learning with Missing Modality](https://openaccess.thecvf.com/content/ICCV2025/html/Li_SimMLM_A_Simple_Framework_for_Multi-modal_Learning_with_Missing_Modality_ICCV_2025_paper.html)<br>
**来源**：ICCV 2025<br>
**代码**：[LezJ/SimMLM](https://github.com/LezJ/SimMLM)<br>
**标签**：dynamic MoE · missing modality · monotonicity · BraTS<br>

## 简要 reading

SimMLM 由 Dynamic Mixture of Modality Experts 和 More-vs-Fewer ranking loss 构成。每个可用模态由专家处理，门控网络根据当前组合调整贡献；MoFe 则约束拥有更多模态的预测不应比其任意子集更差。

该约束把一个常被忽略的合理性问题显式化：不少融合模型加入模态后性能反而降低。论文在 BraTS 2018 分割、UPMC Food-101 和 avMNIST 分类上验证通用性。

## 证据与疑问

- 优点：结构和目标简单，适合作为任意缺失融合的强基线。
- 隐含假设：新增模态总是有益或无害；现实中严重伪影、错误配准或过期检查可能确实降低可信度。
- BraTS 2018 规模较小，无法充分说明对扫描仪和站点变化的适应性。

## 可迁移启发

将硬单调性改为“质量条件单调性”：只有当模态可靠性超过阈值时，才约束加入模态不能降低性能。

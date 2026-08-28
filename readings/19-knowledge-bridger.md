# Knowledge Bridger

**论文**：[Knowledge Bridger: Towards Training-Free Missing Modality Completion](https://openaccess.thecvf.com/content/CVPR2025/html/Ke_Knowledge_Bridger_Towards_Training-Free_Missing_Modality_Completion_CVPR_2025_paper.html)<br>
**来源**：CVPR 2025<br>
**代码**：[Guanzhou-Ke/Knowledge-Bridger](https://github.com/Guanzhou-Ke/Knowledge-Bridger)<br>
**标签**：training-free · missing modality · knowledge graph · LMM · OOD<br>

## 简要 reading

Knowledge Bridger 不在目标数据集重新训练补全网络，而是让大多模态模型从可用模态抽取领域知识图谱，再通过生成和偏好排序得到缺失模态候选。论文同时测试通用和医学场景，重点强调域外泛化。

## 证据与疑问

- 优点：摆脱完整目标训练集，适用于数据稀少或缺失组合变化的场景。
- 依赖领域先验和大模型能力；知识图谱的结构正确不保证生成图像中的细粒度病灶正确。
- “training-free”指目标任务不训练，不代表没有使用大规模外部训练数据。

## 医学启发

更安全的迁移方式可能是用知识图谱辅助预测和检索，而不是生成可被误认为真实检查的影像。

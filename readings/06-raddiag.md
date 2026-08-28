# RadDiag

**论文**：[Large-scale long-tailed disease diagnosis on radiology images](https://www.nature.com/articles/s41467-024-54424-6)<br>
**来源**：Nature Communications 2024<br>
**代码**：[qiaoyu-zheng/RP3D-Diag](https://github.com/qiaoyu-zheng/RP3D-Diag)<br>
**标签**：radiology · 2D/3D · multi-scan fusion · long-tail · knowledge enhancement<br>

## 简要 reading

RadDiag 试图统一不同解剖部位、不同成像模态和 2D/3D 扫描。视觉编码器处理每个扫描，加入模态 embedding 后，Transformer 在病例级融合任意数量的扫描；文本知识编码器则利用疾病同义词、描述和层级关系指导视觉分类。

RP3D-DiagDS 含 40,936 个病例、195,010 次扫描、5,568 个疾病名称和 930 个 ICD-10-CM 类别，呈明显多标签长尾。论文分别报告 head、medium、tail，并比较融合与知识增强模块。

## 证据与疑问

- 优点：少见地同时覆盖多扫描、多模态、2D/3D 与类别长尾。
- 数据来自互联网临床案例资源，虽经审阅，但可能偏向典型、罕见或教学价值高的病例。
- AUC 在极端长尾下可能显得乐观，应同时关注 AP、固定低假阳性率下召回率和每类病例数。

## 可迁移启发

后续研究可把病例级 set Transformer 与检查获取时间、报告文本和缺失组合建模结合，并在真实医院连续队列上做外部验证。

# A Theory of Multimodal Learning

**论文**：[A Theory of Multimodal Learning](https://proceedings.neurips.cc/paper_files/paper/2023/hash/b316495425d076b4abffc065a64c2cca-Abstract.html)<br>
**来源**：NeurIPS 2023（超出两年窗口，作为理论基础纳入）<br>
**代码**：不适用<br>
**标签**：generalization theory · heterogeneity · modality connection · sample complexity<br>

## 简要 reading

论文解释为什么多模态训练有时能改善单模态测试：当模态之间既有连接又有异质性时，多模态学习可获得优于单模态学习的泛化界，在特定设定下优势可达到与样本量平方根相关的量级。

## 理论边界

这是泛化理论而非 PID 或信息瓶颈。其结论依赖论文设定中的模态连接和异质性条件，不能直接推出任意融合网络都会获益，也不能保证缺失、噪声或站点偏移下仍成立。

## 医学启发

融合前应先验证“连接 + 异质性”：若两个模态只是重复记录同一站点偏差，多模态不会自动带来真正的样本效率；若它们具有互补病理机制，则可以设计小样本标度实验验证理论趋势。

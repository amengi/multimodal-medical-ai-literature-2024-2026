# UniMIX-AD

**论文**：[Taming arbitrary modality missingness and imbalance: A unified graph-MoE framework for Alzheimer’s disease diagnosis](https://www.sciencedirect.com/science/article/pii/S1361841526002914)<br>
**来源**：Medical Image Analysis, 2026（在线页面已发布，卷期标注 2026 年 9 月）<br>
**代码**：[SDH-Lab/UniMIX-AD](https://github.com/SDH-Lab/UniMIX-AD)<br>
**标签**：missing modality · modality-combination long tail · graph · sparse MoE · Alzheimer’s disease<br>

## 简要 reading

这篇工作针对两个经常被分开研究的问题：患者拥有任意模态组合，以及不同组合的出现频率高度不均。框架包含 Unified Missing-modality Imputation，用任意可观测组合估计缺失表示；随后以图协调的 Sparse-MoE 路由不同患者，并从高频组合向低频组合迁移结构化知识。

它的重要性在于把“模态组合”视为长尾学习单元，而不是只统计每个模态的边缘缺失率。该问题比均匀随机 modality dropout 更接近 ADNI 一类真实队列。

## 证据与疑问

- 优点：同时覆盖任意缺失、动态融合和尾部组合，是本列表中与目标问题交叉最完整的工作。
- 需核查：训练缺失模式究竟来自真实临床采集还是从完整病例模拟；如果主要是模拟组合，现实有效性仍有限。
- 需核查：稀有组合是否有足够独立病例支持 MoE 专家，而不是依赖共享路由产生表面增益。

## 可迁移启发

应同时报告类别频率、单模态可用率和联合模态组合频率。未来可以加入检查获取倾向模型，把 combination-long-tail 与 MNAR acquisition 统一起来。

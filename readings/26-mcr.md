# MCR

**论文**：[Balancing Multimodal Training Through Game-Theoretic Regularization](https://proceedings.neurips.cc/paper_files/paper/2025/hash/f5784de266e45bd09333721b0a602b61-Abstract-Conference.html)<br>
**代码**：[kkontras/MCR](https://github.com/kkontras/MCR)<br>
**来源**：NeurIPS 2025<br>
**标签**：modality competition · conditional mutual information · game theory · training balance<br>

## 简要 reading

MCR 把多模态训练中的模态竞争写成博弈式正则问题。方法用互信息分解描述每个模态的独有任务贡献和共享信息，改进相关上下界，并用潜空间置换降低条件 MI 估计成本。

## 信息论检查

- 优点是把“弱模态梯度小”提升为“弱模态独有任务信息是否被利用”的问题。
- 潜空间置换近似条件分布，效率更高，但可能破坏医学数据中的患者亚型、站点或时间依赖。
- 博弈均衡不等于临床最优；稀有但关键模态可能需要风险加权而非平均公平。

## 医学启发

可与 PASSION 的梯度平衡和 UniMIX-AD 的组合长尾结合：不仅平衡收敛速度，还显式保护尾部模态组合的条件独有信息。

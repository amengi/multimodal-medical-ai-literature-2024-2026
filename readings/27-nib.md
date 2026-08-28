# Narrowing Information Bottleneck

**论文**：[Narrowing Information Bottleneck Theory for Multimodal Image-Text Representations Interpretability](https://openreview.net/forum?id=INqLJwqUmc)<br>
**代码**：[LMBTough/NIB](https://github.com/LMBTough/NIB)<br>
**来源**：ICLR 2025<br>
**标签**：information bottleneck · CLIP · interpretability · attribution<br>

## 简要 reading

NIB 面向图文表示解释，试图绕开传统瓶颈解释方法的强假设和随机性，使归因更符合一组解释公理。它不是缺失模态方法，但提供了检查“融合表示究竟依赖哪个模态、哪些 token”的工具视角。

## 信息论检查

- 论文关注的是解释瓶颈，不是训练时压缩表示；不能把解释分数直接当作互信息估计。
- OpenReview 落地页可能触发浏览器验证，因此同时保留代码入口。
- 医学应用必须检查解释稳定性、病灶定位和跨中心一致性，不能只看定性热图。

## 医学启发

可用于审计病理–报告或影像–文本模型是否依赖模板词、扫描标记和头部概念，并比较完整/缺失模态时归因是否发生不合理漂移。

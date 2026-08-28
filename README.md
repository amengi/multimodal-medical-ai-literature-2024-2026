# Multimodal Medical AI Literature (2024–2026)

近两年多模态医学 AI 文献库，重点关注：

- 模态融合（modality fusion）
- 模态缺失（missing/incomplete modality）
- 类别、模态与模态组合长尾（long-tailed learning）
- 非配对或弱配对学习（unpaired/weakly paired learning）

检索窗口为 **2024-08-28 至 2026-08-28**。正式发表于 MICCAI 2024、ACM MM 2024 等会议的论文按 proceedings/会议时间纳入。另收录少量略早但具有直接方法启发的论文，并单独标明。

## 快速入口

- [综合比较矩阵](comparison-matrix.md)
- [研究版图、关键空白与选题建议](research-gaps.md)
- [检索与证据说明](methodology.md)
- [全部论文 reading](readings/README.md)

## 优先阅读路线

1. **真实缺失与不平衡**：PASSION → SimMLM → UniMIX-AD
2. **共享/私有表示与生成补全**：DRIM → MUST → MADAT
3. **类别长尾**：RadDiag → CXR-LT → CLIMD
4. **非配对学习**：UNest → MUSK → UNIALIGN → Identifiable SCA

## 核心论文

| 方向 | 推荐论文 |
|---|---|
| 缺失 × 模态组合长尾 | [UniMIX-AD](readings/01-unimix-ad.md) |
| 缺失 × 表征分解 × 生成 | [MUST](readings/02-must.md) |
| 不均衡缺失率 | [PASSION](readings/03-passion.md) |
| 共享/私有表征 | [DRIM](readings/04-drim.md) |
| 非配对图文预训练 | [MUSK](readings/05-musk.md) |
| 类别长尾 × 多扫描融合 | [RadDiag](readings/06-raddiag.md) |
| 动态专家与单调性 | [SimMLM](readings/07-simmlm.md) |
| 自适应缺失模态预后 | [MADAT](readings/08-madat.md) |
| 病理–基因组缺失 | [M2Surv](readings/09-m2surv.md) |
| 多模态类别不平衡 | [CLIMD](readings/10-climd.md) |
| 非配对医学图像合成 | [UNest](readings/11-unest.md) |
| 非配对 CT/MR 分割 | [MulModSeg](readings/12-mulmodseg.md) |

## 使用说明

每篇 reading 都区分：论文明确报告的事实、阅读后的批判性判断、以及可迁移的研究启发。未在论文主页或正文中核验的代码会标记为“未核验”。

本仓库仅保存阅读笔记和公开链接，不重新分发受版权保护的论文全文。论文内容和图表版权归原作者及出版方所有。

# Paper Readings

单篇 reading 保持简短；更深入的“如何结合、如何创新、怎样做关键反证”见 [跨论文创新路线图](../innovation-roadmap.md)。

## 面向后续研究的组合索引

| 研究路线 | 核心论文组合 | 每篇论文承担的角色 |
|---|---|---|
| A. MNAR × 三重长尾 × 信息覆盖路由 | UniMIX-AD + PASSION + SimMLM + BALM + AdaMM + MCR + LSMI | 组合图、缺失不平衡、动态专家、蒸馏、竞争诊断、样本级信息 |
| B. 可拒绝的非幻觉补全 | MUST + MADAT + M³FeCon + DeepIMV + CMCM + AFM2 + NSCLC missing-aware | shared/private、生成审计、条件分布、不生成现实基线 |
| C. 少量锚点可识别非配对学习 | MUSK + IPIC + UNIALIGN + Identifiable SCA + I²M² | 单模态规模化预训练、组标签、无配对对齐、可识别条件、依赖分解 |
| D. PID 引导自适应融合 | PID + LSMI + InfoBridge + HEALNet + InfMasking + SMSN + Fusion–Alignment | 群体/样本诊断、保护独有信息、顺序瓶颈、动态对齐 |
| E. 长尾医学 VLM | EyeCLIP + RadDiag + CXR-LT + MUSK + TITAN + Neglected Tails | 眼科与放射长尾、基础模型、尾部机制、模态依赖审计 |

## 医学论文

1. [UniMIX-AD](01-unimix-ad.md) — 任意缺失与模态组合长尾
2. [MUST](02-must.md) — 可恢复/不可恢复信息分解与潜扩散
3. [PASSION](03-passion.md) — 不均衡缺失率下的自蒸馏
4. [DRIM](04-drim.md) — 不完整影像、病理和组学的共享/私有表示
5. [MUSK](05-musk.md) — 非配对图文预训练与精确肿瘤学
6. [RadDiag](06-raddiag.md) — 大规模多扫描长尾放射诊断
7. [SimMLM](07-simmlm.md) — 动态专家与 More-vs-Fewer 约束
8. [MADAT](08-madat.md) — 缺失感知预后预测
9. [M2Surv](09-m2surv.md) — 记忆增强病理–基因组生存分析
10. [CLIMD](10-climd.md) — 多模态不平衡诊断课程学习
11. [UNest](11-unest.md) — 结构保持的非配对医学图像合成
12. [MulModSeg](12-mulmodseg.md) — 非配对 CT/MR 统一分割
13. [TITAN](13-titan.md) — 多模态全切片基础模型
14. [M³FeCon](14-m3fecon.md) — 将模态缺失视为掩码重建
15. [MoRA](15-mora.md) — 模态感知低秩适配
16. [CXR-LT 2024](16-cxr-lt.md) — 胸片多标签长尾基准
17. [IPIC](17-ipic.md) — 生物数据非配对对比学习
18. [PG-MLIF](18-pg-mlif.md) — 病理–基因组低秩交互融合
19. [HEALNet](32-healnet.md) — 异质生物医学数据、缺失模态与生存分析
20. [Missing-aware NSCLC survival](35-nsclc-missing-survival.md) — CT/WSI/临床变量的自然缺失生存预测
21. [EyeCLIP](36-eyeclip.md) — 11 类眼科模态、部分文本与稀有病长尾
22. [SMSN](41-smsn.md) — 顺序信息瓶颈与缺失 MRI 分割
23. [AdaMM](42-adamm.md) — 15 种模态组合的知识蒸馏与可靠性

## 可迁移的非医学论文

20. [Knowledge Bridger](19-knowledge-bridger.md)
21. [UNIALIGN](20-unialign.md)
22. [Identifiable Shared Component Analysis](21-identifiable-sca.md)
23. [Intervention-Stable Feature Learning](22-intervention-stable-fusion.md)
24. [The Neglected Tails in Vision-Language Models](23-neglected-tails.md)
25. [ANGA](33-anga.md) — 重建样本与完整样本的梯度对齐
26. [BALM](34-balm.md) — 不均衡缺失率下的特征与梯度平衡
27. [AFM2](43-afm2.md) — 基础模型生成缺失模态的系统评测与自验证
28. [Fusion–Alignment](44-fusion-alignment.md) — 动态平衡任务融合与弱模态对齐

## 信息论与多模态机制

25. [OMIB](24-omib.md) — 最优多模态信息瓶颈与模态信息不平衡
26. [InfoBridge](25-infobridge.md) — 条件互信息与防止过度融合
27. [MCR](26-mcr.md) — 信息分解与模态竞争
28. [Narrowing Information Bottleneck](27-nib.md) — 图文表示解释
29. [I²M²](28-i2m2.md) — 模态内/模态间依赖联合建模
30. [PID Framework](29-pid-framework.md) — 冗余、独有与协同信息
31. [A Theory of Multimodal Learning](30-theory-multimodal.md) — 连接、异质性与泛化
32. [DeepIMV](31-deepimv.md) — 缺失多组学的变分信息瓶颈
33. [Multimodal IB alignment](37-multimodal-ib-alignment.md) — 压缩模态特异 nuisance 与 modality gap
34. [CMCM](38-cmcm.md) — Copula 联合依赖和缺失表示分布
35. [LSMI](39-lsmi.md) — 样本级冗余、独有与协同信息估计
36. [InfMasking](40-infmasking.md) — 随机掩码与协同信息代理

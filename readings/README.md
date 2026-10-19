# Paper Readings

单篇 reading 保持简短；更深入的“如何结合、如何创新、怎样做关键反证”见 [跨论文创新路线图](../innovation-roadmap.md)。

## 面向后续研究的组合索引

| 研究路线 | 核心论文组合 | 每篇论文承担的角色 |
|---|---|---|
| A. MNAR × 三重长尾 × 信息覆盖路由 | UniMIX-AD + BALM + ShapKO + AMAF-Net + MMA-LTS | 组合长尾、效用驱动 knockout、真实变量缺失、组合条件校准 |
| B. 可拒绝的非幻觉补全 | MUST + EMMS + PS-MIT + GMENet + Angiography-free + AFM2 | 空证据、后验生成、生成/检索审计、现实缺失 |
| C. 锚点图驱动的非配对学习 | MUSK + IPIC + CALM + Glioma unpaired fusion + Identifiable SCA | 无配对预训练、类条件对齐、标签配对、锚点与可识别边界 |
| D. PID 引导自适应融合 | PID + LSMI + InfoBridge + Φ-OMNI + SYNPRED + InfMasking | 正式/经验 synergy、群体/样本诊断、独有信息保护、估计器审计 |
| E. 长尾医学 VLM | EyeCLIP + RadDiag + CXR-LT + MUSK + TITAN + Neglected Tails | 眼科与放射长尾、基础模型、尾部机制、模态依赖审计 |
| F. 联邦 MNAR 与站点长尾 | ProMoE-FL + EMMS + BALM + Missing-aware NSCLC | 客户端原型、证据回退、梯度平衡、真实检查倾向 |
| G. 成本感知主动检查获取 | SAGEAgent + ShapKO + MMA-LTS + EMMS + SMSN | 顺序价值、群体边际效用、组合校准、空证据回退 |

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
24. [EMMS](45-emms.md) — 缺失模态的空证据与生存不确定性
25. [BrainAnytime](46-brainanytime.md) — 34,899 个脑影像扫描上的任意模态预训练
26. [CSD](47-csd.md) — 类别感知的共享/特异语义解耦
27. [ProMoE-FL](48-promoe-fl.md) — 联邦 non-IID 与系统性模态缺失
28. [UniBrain](49-unibrain.md) — 统一 MRI 补全和医学理解
29. [OT-Coupled Flow](50-ot-coupled-flow.md) — 无配对 CT→TEE 与解剖一致性
30. [PS-MIT](51-ps-mit.md) — 后验采样生成任意缺失 MRI
31. [MUST-VS](52-must-virtual-staining.md) — 不完整配对多染色虚拟生成
32. [ShapKO](53-shapko.md) — Shapley 效用驱动的动态模态 knockout
33. [MMA-LTS](54-mma-lts.md) — 缺失组合与空间条件的置信度校准
34. [SAGEAgent](55-sageagent.md) — 成本感知的顺序模态获取
35. [Φ-OMNI](56-phi-omni.md) — PID 启发的病理协同信息预训练
36. [RMoE](57-rmoe.md) — 患者检索与可靠性专家的缺失生存预测
37. [SYNPRED](58-synpred.md) — 经验协同多模态 VAE 与缺失测试
38. [AMAF-Net](59-amaf-net.md) — 真实临床变量缺失与类别长尾
39. [QA-MoE](60-qa-moe.md) — 质量估计与缺失/噪声路由解耦
40. [GMENet](61-gmenet.md) — 多中心不完整 MRI 的生成式 MoE
41. [CALM](62-calm.md) — 完全非配对影像–遗传对齐
42. [Glioma unpaired fusion](63-unpaired-glioma-fusion.md) — 标签配对/非配对病理–MRI 融合
43. [Angiography-free retina](64-angiography-free-retina.md) — 训练期 CFP–FFA、部署期 CFP 检索补全
44. [Uni-IMD](65-uni-imd.md) — 统一共享/特异分解、OT 与缺失重建
45. [RAM-Missing](66-ram-missing.md) — 真实缺失 CT 的折内检索增强
46. [PriOrGen](67-priorgen.md) — 多器官长尾病理报告生成
47. [IB-GPID](68-ib-gpid.md) — 多组学生存的 Gaussian PID 解释

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

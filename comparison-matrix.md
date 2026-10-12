# 综合比较矩阵

## 医学论文

| 论文 | 模态 | 配对设定 | 缺失处理 | 长尾类型 | 生成补全 | 主要任务 | 主要证据边界 |
|---|---|---|---|---|---|---|---|
| UniMIX-AD | AD 多模态 | 患者级不完整 | UMI + Graph Sparse-MoE | 模态组合 | 表示级 | 诊断 | 真实/模拟缺失比例需核查 |
| MUST | WSI + genomics | 患者级配对 | 共享/特异分解 | 未专门建模 | 潜扩散 | 生存 | TCGA；生成特异信号可解释性 |
| PASSION | 多序列 MRI | 空间配准但训练不完整 | 自蒸馏 + 梯度平衡 | 模态频率 | 否 | 分割 | 缺失由完整公开数据模拟 |
| DRIM | MRI/WSI/RNA/methylation | 患者级部分配对 | 可变序列 + 共享/私有表示 | 未专门建模 | 否 | 生存 | 单疾病；MI 解耦假设 |
| MUSK | 病理 + 文本 | 大规模非配对后少量配对 | 不以缺失为主 | 可支持尾部任务 | 否 | 多任务 | 最终对齐仍需百万图文对 |
| RadDiag | 多种 2D/3D 影像 | 病例级多扫描 | 任意数量 set fusion | 疾病类别 | 否 | 多标签诊断 | 互联网病例选择偏倚 |
| SimMLM | MRI/图像文本/音视频 | 完整训练、缺失测试为主 | Dynamic MoE | 未专门建模 | 否 | 分割/分类 | BraTS 2018；单调性假设 |
| MADAT | 影像 + 临床多模态 | 不完整 | 小波对齐 + 动态注意 | 未专门建模 | 表示级 | 预后 | 三个私有队列 |
| M²Surv | 多 WSI + genomics | 部分配对 | 记忆检索补偿 | 模态不平衡 | 检索式 | 生存 | 记忆泄漏和头部邻居偏差 |
| CLIMD | 多模态诊断数据 | 完整为主 | 不针对缺失 | 疾病类别 | 否 | 分类 | 两个数据集；置信度自举 |
| UNest | MR/CT/PET | 不配对 | 不针对缺失 | 无 | 图像生成 | 合成 | 解剖保持不等于病理保持 |
| MulModSeg | CT/MR | 不配对数据集 | 单模型交替训练 | 可测不均衡训练 | 否 | 分割 | 可能学习数据集来源捷径 |
| TITAN | WSI + 报告/合成描述 | 配对和合成配对 | 不针对缺失 | 稀有病种 | 文本生成 | 检索/分类/报告 | 合成描述偏差 |
| M³FeCon | 多序列 MRI | 空间配准 | 特征重建 | 无 | 特征级 | 分割 | 模拟缺失、特征不可审阅 |
| MoRA | 多模态诊断 | 缺失组合 | 模态感知 LoRA | 无 | 否 | 诊断 | 解决适配成本而非缺失机制 |
| CXR-LT | X-ray + 语言知识 | 单影像为主 | 非核心 | 疾病类别 | 部分方法使用 | 多标签分类 | 模态融合属性较弱 |
| IPIC | 生物多模态 | 完全不配对、组标签 | 不针对单例缺失 | 组分布可不均衡 | 否 | 表征学习 | 依赖处理组标签 |
| PG-MLIF | WSI + genomics | 完整配对 | 无 | 无 | 否 | 生存 | 可作完整模态融合基线 |
| HEALNet | WSI + multi-omics | 患者级不完整 | 共享潜空间与缺失模态训练 | 未专门建模 | 否 | 生存 | TCGA；需外部验证与校准 |
| Missing-aware NSCLC survival | CT + WSI + 临床变量 | 患者级自然不完整 | missing-aware 中间融合 | 模态组合可不均衡 | 否 | 生存 | 小型私有 NSCLC 队列；需外部中心、时间泄漏和 MNAR 审计 |
| EyeCLIP | 11 类眼科影像 + 少量报告 | 部分患者级配对 | 重建 + 图像/图像与图文对比 | 疾病、模态、图文共现 | 否 | 分类/检索/VQA | 中国预训练人群占主；共享表示可能压缩稀有模态独有信息 |
| SMSN | T1/T1ce/T2/FLAIR MRI | 空间配准、人工缺失组合 | 顺序信息瓶颈 + 特异特征恢复 | 未专门建模 | 特征级 | 脑肿瘤分割 | BraTS 为主；随机顺序与变分 MI 代理未证明真实 MNAR 校准 |
| AdaMM | T1/T1Gd/T2/FLAIR MRI | 空间配准、15 种可见组合 | 组合适配器 + 完整教师蒸馏 | 模态组合可不均衡 | 否 | 脑肿瘤分割 | 完整教师与人工缺失；组合适配器可能固化频率偏差 |
| EMMS | WSI + RNA | 患者级配对后人工缺失 | DS/GRFN 证据融合，缺失给空证据 | 未专门建模 | 否 | 生存 | 四个 TCGA 队列；真实 MNAR、外部校准与对称 KL 风险待检验 |
| BrainAnytime | T1/T2/FLAIR/PET | 跨队列部分可用、空间标准化 | 共享 Multi-MAE3D + reciprocal distillation | 模态组合高度不均衡 | 重建预训练 | AD 分期/分割/预测 | 34,899 scans；AD atlas 先验和患者/重复扫描泄漏需审计 |
| CSD | CXR+文本、CXR+表格 | 完整数据人工遮挡 | 类别查询的 shared/specific 语义 | 类别 × 组合 | 否 | 多标签诊断 | 对称模拟缺失；类别查询不等于正式 PID，真实缺失未验证 |
| ProMoE-FL | CXR + 报告 | 多客户端、站点系统性缺失 | 客户端原型条件 MoE 补特征 | 客户端/标签/模态 | 特征级 | 联邦诊断 | 原型可能泄漏站点并偏向大客户端；不是患者报告恢复 |
| UniBrain | 多序列脑 MRI + 报告 | case-level 弱配对 | 自回归联合补全与理解 | 未专门建模 | 图像级 | 生成/诊断 | 2D slice、case report；OOD、病灶忠实度与患者级切分需加强 |
| OT-Coupled Flow | 3D CT + 2D TEE | 完全不配对 | OT 伪对应 + flow matching | 无 | 图像级 | TEE 模拟 | OT plan 非患者对应；真实 TEE 下游、标准差和设备外测不足 |
| PS-MIT | 多序列 MRI | 完整训练、任意人工缺失 | 联合 flow prior + measurement-guided posterior | 组合可不均衡 | 图像级后验采样 | 翻译/分割 | BraTS/IXI；需多样本覆盖、真实 MNAR 和病灶假阳性验证 |
| MUST-VS | H&E + 多染色病理 | 不完整 patch 配对 | 协同去噪 + 伪标签 | 配对缺失 × 病灶类别 | 图像级 | 虚拟染色 | 仅结构相关染色；相邻 patch 泄漏与稀有病灶幻觉需审计 |
| ShapKO | MRI / EHR+CXR+文本 / WSI+omics 等 | 结构缺失 + 人工 knockout | Shapley utility 自适应 masking | 模态/组合效用不均衡 | 否 | 分类/生存 | utility 非 MI/因果价值；精确枚举指数复杂，需真实 MNAR 和最坏组验证 |
| MMA-LTS | T1/T1ce/T2/FLAIR MRI | 完整数据人工遮挡 | 组合 token + voxel difficulty 的温度场 | 组合条件校准 | 否 | 脑肿瘤分割 | post-hoc；未见组合、真实缺失与外部扫描仪的条件 coverage 未保证 |
| SAGEAgent | demographics + MRI + WSI + genomics | 固定临床获取顺序 | LLM + uncertainty + episodic/semantic memory 主动获取 | 获取成本/组合 | 否 | 生存与检查决策 | 170 个完整 glioma 病例；无外部验证，成本权重与策略迁移未知 |
| Φ-OMNI | WSI + transcriptomics + report | 预训练配对，测试仅 WSI | SIB + ΦID 协同信息蒸馏 | 少样本任务 | 否 | 表征/分类 | PID 代理非无偏真值；报告标签泄漏、文本清洗与配对组合消融需审计 |
| RMoE | WSI + genomics | 训练/测试不完整 | 双向患者检索 + reliability-aware MoE | 缺失组合 | 检索式 | 生存 | 三个 TCGA、固定 60% 缺失；risk-label 检索捷径、MNAR 与外部库未验证 |
| SYNPRED | DCE-MRI + RNA | 配对训练、测试可缺失 | shared/unimodal/instance latent VAE | 模态可用率 | latent 生成 | 治疗反应 | synergy 为经验增益非正式 PID；单任务、小样本与 RNA 主导限制外推 |
| AMAF-Net | 非增强 CT + 临床变量 | 真实变量级不完整 | missing pattern 条件融合 + prototype regularization | 类别 × missing pattern | 否 | 四类肾上腺肿瘤 | 1,108 名单中心；mask 可能编码流程/标签，外部与时间验证不足 |
| QA-MoE | ADNI 五模态；MIMIC-IV 三类 EHR | 真实结构性不完整 | evidential quality + subset selection + ternary MoE | 类别 × 模态可用率 | 模板级 | AD 分期/住院时长 | 两个公开 benchmark、无外部站点；质量代理、mask 捷径与患者划分需审计 |
| GMENet | T1c + FLAIR MRI | 多中心真实不完整 + 完整病例随机遮挡 | cross-attention 特征生成 + confidence MoE | 中心 × 序列 × 类别 | 特征级 | 胶质瘤多任务诊断 | 1,241 例六中心；cycle consistency 不证明病灶真实，需留中心外测与 MNAR 分层 |
| CALM | 脑区形态 + 遗传通路 | 完全不重叠人群 | 类条件 MMD + supervised contrastive + 线性投影 | 未专门建模 | 否 | ASD 分类/生物标志物 | 外部 paired 队列；标签/站点/祖源混杂与不可识别性仍在，正交非信息分解 |
| Glioma unpaired fusion | WSI + 多参数 MRI | label-paired 或完全交替训练 | frozen FM + early/late/MoE fusion | 亚型 × 模态 | 否 | WHO 2021 胶质瘤分型 | 1,731 单模态训练、171 配对测试；类条件共享不等于患者交互，需泄漏审计 |
| Angiography-free retina | CFP + FFA | 训练精确配对、推理固定缺 FFA | 疾病特征库检索与 latent completion | 疾病 × 设备 | 特征级 | 七类视网膜病诊断 | 多源外测但固定缺失；图像/患者计数、双眼泄漏、逐源校准与罕见病幻觉需核查 |

## 信息论及理论论文

| 论文 | 核心量/理论 | 主要问题 | 是否直接医学 | 对本课题的价值 | 主要边界 |
|---|---|---|---|---|---|
| OMIB | 信息瓶颈、变分界 | 模态任务信息不平衡 | 否 | 融合、弱模态保护、长尾 | 理论依赖变分族和优化质量 |
| InfoBridge | 条件互信息 | 共享与特异信息平衡 | 否 | 防止过度对齐 | CMI 估计受负样本和条件变量影响 |
| MCR | MI 分解、博弈正则 | 模态竞争 | 否 | 梯度平衡升级为信息贡献平衡 | 潜空间置换可能破坏真实依赖 |
| NIB | 瓶颈解释 | 图文归因 | 否 | 审计医学 VLM 的模态依赖 | 解释分数不是 MI 的直接估计 |
| I²M² | 条件依赖/生成分解 | 模态内与模态间依赖 | 部分 | 医疗融合的依赖图建模 | 标签作为共同生成源的假设需验证 |
| PID framework | redundancy / unique / synergy | 量化模态交互 | 含病理案例 | 选择融合、补全和路由策略 | PID 定义与高维估计不唯一 |
| Theory of Multimodal Learning | 泛化界 | 多模态为何提高样本效率 | 否 | 检验连接与异质性条件 | 不覆盖任意噪声、缺失和偏移 |
| DeepIMV | 变分 IB、PoE | 缺失多组学 | 是 | 缺失模态与信息压缩直接基线 | PoE 冲突时可能过度自信 |
| ANGA | 熵课程、梯度方向对齐 | 重建样本压制完整样本 | 否 | 缺失补全后的优化安全 | 非医学构造缺失；熵不是病理真实性 |
| BALM | 表示校准、梯度幅值/方向重平衡 | 不均衡模态缺失率 | 否 | 三重长尾下的优化基线 | 音视文本情感数据；未覆盖 MNAR/站点偏移 |
| Multimodal IB alignment | 表示级 IB 变分代理 | modality gap 与 nuisance 保留 | 否 | 对齐强度和 private 信息保护 | 代理界与 CKA 不证明任务信息正确分解 |
| CMCM | Gaussian-mixture 边缘 + Copula 联合依赖 | 复杂交互与缺失表示生成 | 是（MIMIC） | 条件分布补全和依赖建模 | Copula/边缘族假设；患者级可识别性未自动成立 |
| LSMI | pointwise information、样本级 entropy estimator | 样本级 redundancy/unique/synergy | 否 | 为 PID 路由提供候选控制量 | 密度估计偏差；不是个体因果解释 |
| InfMasking | 无限掩码 MI 代理 | 协同模式学习不足 | 否 | 缺失组合训练与 synergy 压力测试 | 代理提升不等于正式 PID synergy 增大 |
| AFM2 | 多候选生成 + 自验证代理 | 基础模型的缺失图像/文本生成 | 否 | 生成范式 benchmark 与验证门控 | FID/MER 不代表病灶忠实度；同源自验证可能自洽幻觉 |
| Fusion–Alignment | 动态 fusion/alignment 双层优化 | 弱模态激活与模态失衡 | 否 | 将对齐强度变成条件控制量 | 非医学 benchmark；对齐可能传播强模态捷径并删除 private 信息 |
| Φ-OMNI | SIB + ΦID（PID 启发代理） | 抑制冗余、蒸馏协同交互 | 是 | 首个直接病理协同信息路线之一 | 代理受 PID 定义/变分估计影响，需合成真值与泄漏审计 |
| SYNPRED | task-conditioned KL + VAE latent factorization | 经验协同与缺失测试 | 是 | 区分经验增益和正式 synergy 的对照 | 作者明确非正式信息论 synergy；moment matching 非完整密度 |
| ShapKO | coalition utility / Shapley value | 动态模态 dominance | 是 | 将平均边际贡献接入训练分布 | Shapley utility 不是 MI、因果贡献或个体检查价值 |

## 最适合作为实验基线的组合

- 任意缺失、非生成：SimMLM、MoRA、DRIM、BrainAnytime、EMMS。
- 不均衡缺失率与动态 dropout：PASSION、UniMIX-AD、ShapKO。
- 生成式补全：MUST、MADAT、M³FeCon、UniBrain、PS-MIT。
- 病理–组学生存：PG-MLIF、DRIM、M²Surv、MUST。
- 非配对/不完整配对：UNest、MUSK、IPIC、CALM、Glioma unpaired fusion、OT-Coupled Flow、MUST-VS。
- 类别长尾：RadDiag、CXR-LT、CLIMD、AMAF-Net。
- 自然缺失临床基线：Missing-aware NSCLC survival、CMCM。
- 不均衡缺失与梯度平衡：PASSION、BALM、ANGA。
- 样本级信息诊断：LSMI；协同训练压力测试：InfMasking。
- 顺序融合与缺失 MRI：SMSN；弱组合蒸馏：AdaMM。
- 生成式基础模型审计：AFM2；融合—对齐控制：Fusion–Alignment。
- 联邦系统性缺失：ProMoE-FL；类别条件缺失诊断：CSD。
- 缺失组合校准：MMA-LTS；主动检查获取：SAGEAgent。
- 协同信息：Φ-OMNI（PID 代理）、SYNPRED（经验 synergy）；检索证据：RMoE。
- 质量感知真实缺失：QA-MoE；多中心生成式缺失 MRI：GMENet；单模态部署：Angiography-free retina。

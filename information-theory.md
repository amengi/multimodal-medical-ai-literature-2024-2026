# 信息论 × 多模态：阅读地图

本专题把信息论当作可检验的建模语言，而不是装饰性术语。设模态为 \(X_1,\ldots,X_M\)，任务标签为 \(Y\)，融合表示为 \(Z\)。核心问题不是简单地“最大化互信息”，而是区分：

- **冗余信息**：多个模态各自都能提供的任务信息；
- **独有信息**：只有某一模态相对其他模态额外提供的信息，如 \(I(X_i;Y\mid X_{-i})\)；
- **协同信息**：必须联合观察多个模态才能得到的信息；
- **无关信息**：与任务无关但可能被模型记忆的扫描仪、站点或文本风格信号。

## 与四个目标方向的对应关系

| 方向 | 信息论视角 | 最值得测量的量 | 直接启发 |
|---|---|---|---|
| 模态融合 | 融合应保留独有与协同信息，而非只扩大冗余 | PID、条件互信息 | InfoBridge、PID framework、I²M²、SMSN |
| 模态缺失 | 缺失模态中只有冗余部分原则上可从现有模态恢复 | \(I(X_m;Y\mid X_{obs})\)、预测熵 | DeepIMV、OMIB、HEALNet |
| 长尾/模态竞争 | 头部或强模态可能压制弱模态的梯度和任务信息 | 各模态任务 MI、条件 MI 下界 | OMIB、MCR |
| 非配对学习 | 没有样本级联合分布时，普通 MI 目标未必可识别 | 分布级依赖、少量锚点下的 CMI | Identifiable SCA、PID framework |
| 个体化融合 | 群体平均信息结构不能直接决定单病例路由 | pointwise redundancy/unique/synergy + 估计不确定性 | LSMI、InfMasking |

## 三条关键判断

1. **最大化跨模态 MI 可能导致过度对齐。** 如果两个编码器只保留公共部分，罕见但关键的模态特异信号可能被删除。InfoBridge 的意义正是引入条件依赖与保护边界。
2. **最小化 shared/private MI 也不自动等于解耦正确。** 在高维连续变量上，MI 通常只通过变分界或对比下界间接估计；估计器偏差可能比方法差异更大。
3. **补全不等于恢复。** 当 \(I(X_m;Y\mid X_{obs})\) 很大时，缺失模态包含不可由现有模态确定的独有任务信息；生成器最多给出条件分布样本，不应把它当作患者真实观测。

## 推荐阅读顺序

1. [PID framework](readings/29-pid-framework.md)：先建立 redundancy / uniqueness / synergy 词汇表。
2. [OMIB](readings/24-omib.md) 与 [MCR](readings/26-mcr.md)：理解信息不平衡和模态竞争。
3. [InfoBridge](readings/25-infobridge.md)：看条件 MI 如何避免过度融合。
4. [DeepIMV](readings/31-deepimv.md) 与 [HEALNet](readings/32-healnet.md)：映射到缺失组学、病理和生存分析。
5. [A Theory of Multimodal Learning](readings/30-theory-multimodal.md)：区分一般化理论与信息分解理论。
6. [Multimodal IB alignment](readings/37-multimodal-ib-alignment.md)：理解对齐与 private-information 保留之间的张力。
7. [CMCM](readings/38-cmcm.md) 与 [LSMI](readings/39-lsmi.md)：分别从联合分布和样本级交互补足条件建模。
8. [InfMasking](readings/40-infmasking.md)：把“增强 synergy”的算法主张与可测 PID 证据分开审计。
9. [SMSN](readings/41-smsn.md) 与 [Fusion–Alignment](readings/44-fusion-alignment.md)：比较顺序压缩和动态对齐；重点检查它们是否保留任务相关 private 信息。

## 可执行的研究假设

这些假设在 [深度创新路线图](innovation-roadmap.md) 中被展开为模型原型、关键对照和可证伪条件。

### A. PID-aware 模态组合长尾

假设：尾部组合性能差不只是样本少，还因为路由器偏向头部组合的冗余信息。可在 UniMIX-AD 式组合图上，为每个组合估计独有/协同信息，并把专家分配目标从频率平衡改成信息覆盖平衡。

### B. 可拒绝的缺失模态补全

假设：当估计的条件独有信息超过阈值时，补全风险显著上升。模型应输出条件分布和不确定性，并允许拒绝预测，而不是生成单个确定性伪模态。

### C. MNAR 条件信息瓶颈

令缺失掩码为 \(R\)。临床检查获取通常是非随机的，因此目标应比较 \(I(Z;Y\mid R)\) 与 \(I(Z;R)\)，同时做获取倾向敏感性分析，避免模型只利用检查流程预测疾病。

### D. 对齐—独有信息的自适应瓶颈

Multimodal IB alignment 希望压缩模态特异 nuisance，InfoBridge 则警惕过度对齐删除条件独有信息。可按模态和亚组估计 $I(X_m;Y\mid X_{-m})$：条件独有信息高时减弱瓶颈并保留 private branch；低且 nuisance 明显时加强压缩。这里优化的仍是变分界/代理，必须用真实模态屏蔽与新增干预验证。

### E. Copula 后验与可拒绝补全

CMCM 给出联合潜变量分布，路线 B 可据此输出 $p(z_m\mid z_{obs},R,S)$ 而不是单点伪模态。关键可测量不是 latent 重建误差，而是后验覆盖率、下游风险校准、尾部病种覆盖和拒绝后的 risk–coverage；若 Copula 族失配或区间不覆盖真实完整病例，应回退到非生成融合。

### F. 样本级交互只作为可验证控制信号

LSMI 将 redundancy/unique/synergy 下沉到样本级，适合给路由器提供候选标签；InfMasking 则可作为协同训练干预。二者组合时，必须先检验 LSMI 分数能否预测“新增一个真实模态”带来的边际收益，并报告估计器跨 batch、表示尺度和站点的稳定性。若不能预测真实干预收益，则不得把分数当作个体临床解释。

### G. 顺序瓶颈不是固定序列

SMSN 表明顺序融合可作为并行融合的替代，但随机重排没有把临床价值、质量与成本纳入顺序。可定义候选模态的条件价值代理
\(V_m=\widehat I(X_m;Y\mid X_R)-\lambda c_m-\mu u_m\)，其中 \(c_m\) 是检查成本、\(u_m\) 是估计不确定性；只用该代理选择融合/采集顺序，不把它宣称为真实 MI。必须用真实“新增模态”干预、顺序置换和外部中心复现验证 \(V_m\) 是否预测风险下降。

## 实验注意事项

- 先在已知 PID 的合成数据验证估计器，再进入医学数据。
- 报告估计器、负样本构造、batch size 和变分分布；这些会显著影响 MI 数值。
- 不把 MI 下界的上升直接解释成真实 MI 上升。
- 同时报告任务性能、校准、最坏模态组合、外部中心和真实缺失子集。
- 对生成补全加入病灶一致性、反事实敏感性和拒绝率，而不仅是 PSNR/SSIM。

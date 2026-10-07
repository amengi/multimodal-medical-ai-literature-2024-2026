# SAGEAgent：按成本顺序获取下一项模态

- **论文**：SAGEAgent: A Self-evolving Agent for Cost-Aware Modality Acquisition in Multimodal Survival Prediction
- **作者**：Chongyu Qu, Can Cui, Zhengyi Lu, Junchao Zhu, Tianyuan Yao, Junlin Guo, Juming Xiong, Yanfan Zhu, Yuechen Yang, Bennett A. Landman, Yuankai Huo
- **出处**：MICCAI 2026，LNCS 16878
- **原文**：[MICCAI Open Access](https://papers.miccai.org/miccai-2026/0915-Paper0802.html)
- **代码**：[GitHub](https://github.com/Chongyu1117/SAGEAgent)

## 简要 reading

**问题。** 被动容忍缺失没有回答“是否值得为这个患者继续做更昂贵检查”；真实流程还有 demographics→radiology→pathology→genomics 的顺序约束。

**方法变化。** 冻结生存预测器和 Qwen2.5-7B，以校准不确定性工具、相似病例 episodic memory 与可更新 semantic rules，让代理逐步执行 ACQUIRE/STOP；在 170 个完整 glioma 病例的 nested 5×5 CV 中把平均 burden 降低 55%，C-index 与全检查基线差异未显著。

**证据边界。** 主要结论来自单一 glioma 数据构造和 170 个完整病例，无外部/前瞻验证；成本权重和固定检查顺序未必跨医院成立。LLM 决策可能利用文本化风险捷径，且较高 hypervolume 不等于临床净收益；需预定义 non-inferiority margin 与决策校准。

**研究连接。** 与路线 D、SMSN 和 Idea 4 组合，把顺序融合升级为顺序检查决策：用真实新增检查的风险下降训练轻量 value head，LLM 只解释而不决定主策略；对成本、站点与缺失倾向做敏感性分析，并用 oracle value 和不确定性阈值作强基线。

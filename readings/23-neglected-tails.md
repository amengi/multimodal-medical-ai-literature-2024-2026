# The Neglected Tails in Vision-Language Models

**论文**：[The Neglected Tails in Vision-Language Models](https://openaccess.thecvf.com/content/CVPR2024/html/Parashar_The_Neglected_Tails_in_Vision-Language_Models_CVPR_2024_paper.html)<br>
**来源**：CVPR 2024；略早于严格 24 个月窗口，作为关键方法背景保留<br>
**标签**：vision-language model · concept frequency · long tail · retrieval augmentation<br>

## 简要 reading

论文用 LLM 估计大规模视觉–语言预训练语料中概念的出现频率，发现 CLIP 等模型的零样本性能与概念频率显著相关；视觉聊天和文本生成图像模型同样难以处理尾部概念。作者提出 retrieval-augmented learning 缓解不均衡。

## 证据与疑问

- 价值：说明“零样本”不代表不受训练频率影响，预训练语料长尾会直接传导到下游。
- LLM 计数依赖同义词集合和文本检索质量，只是概念频率近似。
- 自然图像概念与医学疾病的标签层级、共病和诊断不确定性不同。

## 医学启发

医学 VLM 应公开或估计疾病、征象和解剖概念在预训练语料中的频率，并报告其与零样本诊断性能、幻觉率之间的关系。

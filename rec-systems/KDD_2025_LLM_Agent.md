# KDD 2025 | 搜广推应用大模型及智能体的文章集锦

> **原文链接**: [https://zhuanlan.zhihu.com/p/1989694242503823913](https://zhuanlan.zhihu.com/p/1989694242503823913)  
> **点赞数**: 12  
> **平台**: 知乎专栏

---

以下是KDD 2025中12篇聚焦搜广推×大模型×智能体的代表性论文，覆盖推荐系统、搜索广告、多模态交互与智能体协同等方向，包含完整标题、核心摘要、获取链接与关键亮点：

一、推荐系统×大模型（核心研究轨道）
1. RPG: Recommendation with Parallel Semantic ID Generation
作者：Meta团队
核心摘要：提出并行语义ID生成框架，解决LLM在大规模商品推荐中面临的离散Item ID适配难题，通过单步生成替代传统多级检索，在Amazon数据集上提升推荐质量（Recall/NDCG），同时将推理效率提升5-14倍。
链接：https://arxiv.org/pdf/2506.05781.pdf
代码：https://github.com/facebookresearch/RPG_KDD2025
亮点：首次实现LLM与亿级商品ID的高效对齐，适合工业级推荐系统部署。
2. LLM2Rec: Large Language Models Are Powerful Embedding Models for Sequential Recommendation
作者：He Yingzhi等
核心摘要：证明LLM可作为序列推荐的强大嵌入模型，提出轻量级适配策略，无需全量微调即可提取高质量用户/物品表征，在多个公开数据集上显著优于传统序列推荐方法。
链接：https://arxiv.org/pdf/2506.05824.pdf
代码：https://github.com/HappyPointer/LLM2Rec
亮点：为LLM在序列推荐中的低成本应用提供新范式。
3. LaViC: Adapting Large Vision-Language Models to Visually-Aware Conversational Recommendation
作者：UCSD团队（J. McAuley组）
核心摘要：提出视觉-语言对话推荐框架，将紧凑图像表示融入对话系统，构建Reddit-Amazon多模态对话数据集，解决视觉导向领域（时尚、美妆）的推荐准确性问题。
链接：https://cseweb.ucsd.edu/~jmcauley/reviews/kdd25b.pdf
亮点：打通视觉信息与对话推荐的壁垒，支持细粒度用户偏好理解。
4. Bursting Filter Bubble: Enhancing Serendipity Recommendations with Aligned Large Language Models
作者：Xi Yunjia等
核心摘要：利用对齐LLM打破推荐系统的“过滤气泡”，通过LLM的常识推理能力挖掘用户潜在兴趣，在保证准确性的同时提升推荐的意外性与多样性，在电商数据集上验证显著效果。
链接：https://dl.acm.org/doi/10.1145/3711896.3737199
亮点：将LLM的知识推理能力用于解决推荐多样性与意外性难题。
5. Selection and Exploitation of High-Quality Knowledge from Large Language Models for Recommendation
作者：快手团队（Wang Guanchen等）
核心摘要：提出高质量知识选择与利用框架，解决LLM生成知识的噪声与冗余问题，通过知识质量评分机制筛选有效信息，提升推荐系统的可解释性与准确性。
链接：https://arxiv.org/pdf/2508.07223v1.pdf
亮点：为LLM知识增强推荐提供质量控制方案，适合工业级应用。
二、搜索与广告×大模型+智能体
6. Real-time Ad retrieval via LLM-generative Commercial Intention for Sponsored Search Advertising
作者：腾讯广告团队（Liu Tongtong等）
核心摘要：提出LLM生成式商业意图理解方法，实时捕捉用户搜索中的广告意图，将自然语言查询转化为精准广告检索信号，在腾讯搜索广告平台上提升CTR与转化率。
链接：https://arxiv.org/pdf/2504.01304.pdf
亮点：实现搜索广告中意图理解的实时化与精准化，适配动态商品库。
7. Efficient Single-Step Item ID Generation for Large-Scale LLM-based Recommendation
作者：Google Research团队
核心摘要：解决LLM在大规模推荐中面临的Item ID生成效率问题，提出单步生成策略，将商品目录与用户行为融入LLM，在Amazon数据集上实现推荐质量与推理效率的双重提升。
链接：https://research.google/pubs/efficient-single-step-item-id-generation-for-large-scalellm-based-recommendation/
亮点：为LLM在超大规模商品推荐中的落地提供工程化解决方案。
8. OMS: On-the-fly, Multi-Objective, Self-Reflective Ad Keyword Generation via LLM Agent
作者：Chen Bowen等
核心摘要：提出LLM智能体驱动的广告关键词生成框架，支持多目标（相关性、点击率、转化率）实时优化，通过自我反思机制迭代提升关键词质量，在电商广告场景中显著优于传统方法。
链接：https://arxiv.org/pdf/2507.02353v1.pdf
DOI：https://doi.org/10.18653/v1/2025.emnlp-main.938
亮点：将智能体的自主决策能力用于广告关键词生成，适配动态营销目标。
三、智能体×搜广推（科研精选）
9. FlowXpert: Expertizing Troubleshooting Workflow Orchestration with Knowledge Base and Multi-Agent Coevolution
作者：南开大学团队
核心摘要：提出多智能体协同的推荐系统故障排除框架，通过知识库与智能体共同进化，实现推荐系统异常的快速诊断与修复，提升系统稳定性与用户体验。
链接：软件学院师生论文被数据挖掘领域顶会SIGKDD 2025录用
亮点：将智能体技术用于推荐系统运维，解决工业级系统的可靠性问题。
10. LLM-Enhanced Reranking for Complementary Product Recommendation
作者：Xu Zekun等（GenAIRecP@KDD’25）
核心摘要：提出模型无关的LLM增强重排方法，解决互补商品推荐中的准确性-多样性权衡问题，通过LLM的语义理解能力提升长尾商品的推荐效果。
链接：https://genai-personalization.github.io/assets/papers/GenAIRecP2025/5_Xu.pdf
亮点：轻量级适配现有推荐系统，无需重构即可提升互补推荐性能。
11. Optimizing Retrieval-Augmented Generation with Multi-Agent Hybrid Retrieval
作者：Baban等（GenAIRecP@KDD’25）
核心摘要：提出智能体混合检索框架，协调关键词检索与嵌入检索的优势，通过LangGraph实现并行智能体协同，动态适配查询复杂度，提升推荐系统的检索效率与准确性。
链接：https://genai-personalization.github.io/assets/papers/GenAIRecP2025/11_Baban.pdf
亮点：将Agentic RAG技术用于推荐检索，解决复杂查询的理解难题。
12. End-to-End Personalization: Unifying Recommender Systems with Large Language Models
作者：Ebrat等（GenAIRecP@KDD’25）
核心摘要：提出端到端个性化框架，将推荐系统与LLM深度融合，通过LLM驱动的推理与图关系学习结合，实现可扩展、可解释的推荐系统，在多个数据集上验证新基准。
链接：https://arxiv.org/pdf/2508.01514.pdf
https://genai-personalization.github.io/assets/papers/GenAIRecP2025/12_Ebrat.pdf
亮点：为推荐系统与LLM的统一提供完整技术路径。
补充说明
覆盖范围：以上论文来自KDD 2025研究轨道（Research Track）与两个核心工作坊（GenAIRecP、AdKDD），均聚焦搜广推×大模型×智能体的技术融合与应用创新。
获取方式：DOI链接可通过ACM Digital Library访问，arXiv链接可免费获取预印本，部分论文提供开源代码。
技术趋势：核心方向包括LLM高效适配大规模商品目录、多模态信息融合、智能体自主决策与协同、知识增强与可解释性，代表了工业界与学术界的前沿探索。
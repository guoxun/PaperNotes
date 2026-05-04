# 小红书生成式推荐系统 — 论文深度总结 | SAGE: Sequence-level Gradient Evolution for Generative Recommendation

> **原文链接**: [https://zhuanlan.zhihu.com/p/2020816071146386879](https://zhuanlan.zhihu.com/p/2020816071146386879)  
> **点赞数**: 16  
> **平台**: 知乎专栏

---

SAGE: Sequence-level Adaptive Gradient Evolution for Generative Recommendation — 论文深度总结
论文信息

标题: SAGE: Sequence-level Adaptive Gradient Evolution for Generative Recommendation
作者: Yu Xie, Xing Kai Ren, Ying Qi, Hu Yao（小红书团队）
来源: arXiv:2601.21452
领域: 生成式推荐系统 / 大语言模型对齐 / 强化学习


一、研究背景与动机

1.1 从传统推荐到生成式推荐的范式跃迁

传统推荐系统（DLRM）基于 ID 匹配范式：将用户和物品映射为高维稀疏 Embedding，通过向量内积预测点击率。这种范式存在根本性局限：

冷启动困境：新物品缺乏交互数据，Embedding 质量差，陷入”无曝光→无数据→无法学习”的死循环
语义割裂：ID Embedding 无法捕获物品的语义内容，难以进行跨领域/跨模态推理
信息茧房：马太效应导致热门物品持续垄断曝光，长尾物品被永久压制

LLM 的出现带来了范式转移：生成式推荐系统（Generative Recommender Systems） 抛弃打分排序逻辑，让大模型以自回归生成方式直接输出推荐物品序列。

1.2 Semantic ID 路线的工程瓶颈

业界先驱（Google TIGER、快手OneRec）采用 Semantic ID 路线：通过量化技术（RQ-VAE）将物品压缩为离散代码序列。但在工业规模下（每天新增上亿条内容）遭遇灾难性问题：

问题	具体表现
碰撞冲突	多个语义不同的物品被编码为相同 ID，模型无法区分
词表灾难	物品量级暴增时，ID 词表的维护和更新成本不可控
语义断裂	量化过程中丢失原始语义信息，无法激发 LLM 的语义理解能力


1.3 推荐领域 RLHF 的核心痛点

将 NLP 领域的 PPO/GRPO 直接迁移到推荐系统会遭遇严重的”水土不服”：

痛点一：对称保守性（Symmetric Conservatism）

现有优化器（如 GBPO）采用对称的静态梯度边界 [1-ε, 1+ε]。在推荐系统中，这种对称性从根本上违背了数据分布特征：

正反馈极度稀疏：用户对冷门物品的正反馈极其珍贵，但对称 clipping 将其更新幅度限制在与热门物品相同的上界，导致冷启动物品永远无法突破曝光阈值
负反馈高度同质化：大量负反馈来自同质化的推荐结果，但对称惩罚无法区分”失败的探索”和”敷衍的信息茧房”，导致多样性坍塌（Diversity Collapse）

痛点二：奖励坍塌（Reward Collapse）

推荐系统涉及多个优化目标（点击率、完播率、评论率等），直接加权求和后进行 Group Normalization 会导致不同行为模式映射到相同的优势值，梯度信号退化。

二、核心研究问题

论文试图回答一个关键问题：

如何设计一个优化框架，使其能够在生成式推荐的 RLHF 阶段，同时解决冷启动压制、多样性坍塌和多目标奖励坍塌三大工业级难题？

具体而言：

如何让优化器”认知到”冷启动物品的成功推荐比热门物品更有价值，给予超线性的梯度激励？
如何让优化器”感知到”低多样性的失败推荐比探索性失败更有害，施加更强的梯度惩罚？
如何在多目标场景下保持各目标优势信号的独立性，避免信息混淆？
核心理论假设
在生成式推荐的偏好优化中，标准的对称截断（Symmetric Clipping）从根本上违背了推荐系统的”长尾探索”与”去同质化”需求。基于行为多样性的非对称奖惩是同时解决冷启动和多样性崩塌的数学基石。

三、方法论（SAGE 框架）

3.1 整体架构：SFT + RLHF 两阶段流水线

整个系统的工作流分为三大阶段：

阶段零：数据构造

将用户画像、历史行为序列、候选物品描述等转化为自然语言提示（Prompt）
直接使用物品的原生文本描述（标题、标签等）作为生成目标，废弃 Semantic ID
这使得 LLM 可以直接利用预训练获得的语义知识

阶段一：监督微调（SFT）

使用用户历史交互数据构造 <prompt, target_list> 对
对开源 LLM 进行标准的 Next-Token 预测训练
让模型学会推荐任务的基本输入输出格式

阶段二：SAGE 强化学习优化

在 SFT 模型基础上，使用 SAGE 进行偏好对齐
模型生成候选推荐列表（Slate），根据多维用户反馈计算奖励
通过 SAGE 的非对称自适应梯度更新优化策略

3.2 核心技术模块
模块一：序列级概率比值（Sequence-level Ratio）

问题：传统 PPO 在 Token 级别计算重要性采样比值 r_t = π_θ(a_t|s_t) / π_old(a_t|s_t)。但在推荐系统中，奖励信号是针对整个推荐列表（Slate） 而非单个 Token 的。Token 级比值会引入巨大的方差。

解决方案：采用几何平均（Geometric Mean）将 Token 级比值聚合为序列级比值：

r_slate = (∏_{t=1}^{T} r_t)^{1/T}

其中 T 是推荐列表对应的 Token 序列长度。几何平均相比算术平均具有以下优势：

对异常值鲁棒，避免单个 Token 比值极端时主导整体更新
保持乘法结构与概率链式法则的自然对齐
归一化效果消除序列长度差异带来的偏差
模块二：多目标信号解耦（Multi-Objective Signal Decoupling）

问题：推荐系统有多个优化目标（点击 R_click、时长 R_duration、评论 R_comment 等）。直接加权求和 R = Σ w_m · R_m 后做 Group Normalization 会导致奖励坍塌——不同行为模式被映射到相同的标准化优势值。

解决方案：Decouple-then-Aggregate（先解耦后聚合）策略：

A_SAGE(S) = Norm_batch( Σ_{m=1}^{M} w_m · (R_m(S) - μ_m^{group}) / (σ_m^{group} + ε) )

关键步骤：

独立标准化：对每个目标 m，在采样组内独立计算均值 μ_m^{group} 和标准差 σ_m^{group}，然后标准化
加权聚合：用业务权重 w_m 对标准化后的各目标优势加权求和
批次归一化：对聚合后的优势值进行批次级 Normalization

这样，每个目标在标准化阶段保留了自身的分布特征，避免了信息混淆。

模块三：非对称自适应动态边界（Asymmetric Adaptive Dynamics） — SAGE 的核心创新

这是 SAGE 最关键的突破。传统 GBPO 使用对称 clipping：

L_GBPO = min(r · A, clip(r, 1-ε, 1+ε) · A)

SAGE 将 clipping 边界改为非对称且自适应的，分为两种情况：

Case A：正向冷启动助推（Positive Boost）

当推荐列表获得正反馈（A_SAGE > 0）时：

SAGE 引入 Boost Factorε_boost
有效梯度系数的上界从 1+ε 提升至 1+ε+ε_boost
如果模型成功推荐了高潜力的冷启动物品（导致较高的 r_slate），SAGE 锁定分母使得有效梯度系数维持在 1+ε_boost

效果：允许冷启动物品的推荐概率超线性增长，提供突破初始曝光阈值的必要动量。传统 GBPO 的对称上界 1+ε 则会将这种增长截断。

Case B：熵感知多样性惩罚（Entropy-Aware Penalty）

当推荐列表获得负反馈（A_SAGE < 0）时：

SAGE 使用 List EntropyH(S) 度量推荐列表的语义多样性
当 H(S) 很低（列表中物品高度同质化）时，说明模型在”信息茧房”中摆烂
此时 SAGE 动态扩大负向 clipping 边界，施加更强的梯度惩罚
当 H(S) 较高（列表多样性好）时，说明是”诚实的探索失败”，惩罚保持温和

效果：让优化器能够区分两种本质不同的失败模式——探索性失败（应被宽容）vs 同质化摆烂（应被严惩），从而打破信息茧房。

SAGE 目标函数的统一形式：

L_SAGE = E_S [ min(r_slate · A_SAGE, clip_asym(r_slate, A_SAGE, H(S)) · A_SAGE) ]

其中 clip_asym 根据 A_SAGE 的正负和 H(S) 的大小动态确定非对称的 clipping 边界。

3.3 SAGE 与现有方法的定位对比
维度	PPO/GBPO	SAGE
比值粒度	Token 级	序列级（几何平均）
Clipping 边界	对称静态 [1-ε, 1+ε]	非对称自适应
正反馈处理	统一上界截断	Boost Factor 超线性激励
负反馈处理	统一下界截断	熵感知动态惩罚
多目标处理	加权求和→统一标准化	先解耦标准化→后聚合
针对场景	通用 NLP	推荐系统定制

四、实验设置

4.1 数据集
数据集	类型	规模	说明
Amazon Product Reviews (Beauty)	学术基准	数百万交互	电商用户评论，1996-2014
Amazon Product Reviews (Sports)	学术基准	数百万交互	同上
Amazon Product Reviews (Toys)	学术基准	数百万交互	同上
RecIF-Bench	工业基准	1.2 亿次真实交互	包含短视频、广告、商品推荐等多场景

4.2 基线方法
SASRec: 基于自注意力的序列推荐模型（传统 DLRM）
TIGER: Google 提出的基于 Semantic ID 的生成式推荐
LC-Rec: 基于 Semantic ID 的改进方法
ReaRec: 基于推理增强的推荐方法
OneRec-V2: 阿里的 Semantic ID + GBPO 优化器方案
OneRec-SAGE: 将 SAGE 替换 OneRec 的 GBPO 优化器
TextRec (RecLLM): 使用原生文本 + SAGE 优化器的完整方案

4.3 评估指标
准确率: Recall@5, Recall@10, NDCG@5, NDCG@10
多样性: Entropy@10（推荐列表的信息熵）
冷启动: Cold-Recall@10（冷启动物品的召回率）

五、实验结果与分析

5.1 整体准确率（Top-K Accuracy）

Amazon 数据集结果：

方法	Beauty R@5	Beauty R@10	Beauty N@5	Beauty N@10	Sports R@5	Sports R@10	Toys R@5	Toys R@10
SASRec	0.0393	0.0639	0.0209	0.0289	0.0240	0.0389	0.0420	0.0658
TIGER	0.0413	0.0628	0.0277	0.0346	0.0216	0.0331	0.0367	0.0527
LC-Rec	0.0495	0.0764	0.0338	0.0424	0.0269	0.0418	0.0350	0.0549
ReaRec	0.0488	0.0702	0.0341	0.0409	0.0231	0.0348	0.0517	0.0706
TextRec (SAGE)	0.0574	-	0.0392	-	0.0273	-	-	-

核心发现：TextRec + SAGE 在三个 Amazon 子集上全面超越所有基线，验证了原生文本表示 + 非对称优化器的组合优势。

5.2 多样性与冷启动指标
方法	Beauty Entropy@10	Beauty Cold-Recall	Sports Entropy@10	Sports Cold-Recall	Toys Entropy@10	Toys Cold-Recall
OneRec-V2	2.285	0.0326	2.274	0.0282	2.315	0.0365
OneRec-SAGE	2.551	0.0619	2.528	0.0713	2.574	0.0695
RecLLM (TextRec)	2.420	0.0487	2.510	0.0460	2.485	0.0522
提升幅度	+5.9%	+49%	+10.36%	+63%	+7.36%	+43%

关键结论：

冷启动召回率暴涨：SAGE 的 Boost Factor 在三个数据集上分别带来 49%、63%、43% 的冷启动改善，验证了正向超线性激励机制的有效性
多样性显著提升：熵感知惩罚在各数据集上带来 5.9%~10.36% 的 Entropy 改善，证明了对同质化推荐的有效惩戒
OneRec-SAGE 在多样性/冷启动指标上达到最高绝对值，说明 SAGE 优化器本身的贡献独立于动作空间的选择
5.3 工业级 RecIF-Bench 结果

短视频场景（Short Video）：

方法	Entropy@10	Cold-Recall@10
OneRec-GBPO	4.284	0.521
OneRec-SAGE	4.455	0.637
TextRec	4.317	0.594

在包含 1.2 亿次真实工业交互的 RecIF-Bench 上，SAGE 保持了稳定的统治力。特别是在”指令遵循（Instruction-conditioned）”子任务中，TextRec 的优势被进一步放大，证明原生文本表示比 Semantic ID 更能激发 LLM 的语义涌现能力。

5.4 消融实验（Ablation Study）

在 Amazon-Beauty 数据集上进行的组件剥离测试：

消融配置	影响
移除 Positive Boost (ε_boost=0)	Cold-Start Recall 降至完整模型的0.50（暴跌 50%），证实正向助推对物品探索至关重要
移除 Entropy Penalty	Entropy@10 降至完整模型的0.78（下降 22%），表明多样性向同质化坍塌
移除信号解耦	各指标均有下降，验证独立标准化对保持梯度信号保真度的必要性
完整 SAGE	所有指标达到最优，证明三个模块构成不可或缺的精巧闭环

结论：SAGE 的三个核心模块（Positive Boost、Entropy-Aware Penalty、Signal Decoupling）缺一不可，它们共同构成了一个协同增强的优化体系。

六、核心创新点总结

6.1 理论创新
首次提出非对称动态梯度边界：打破了 PPO/GBPO 家族一直以来的对称 clipping 假设，将推荐系统中正负反馈的信息价值不对称性显式编码到优化器中
熵感知的行为多样性度量：将信息论中的熵引入策略优化的惩罚机制，使优化器能区分”探索性失败”和”同质化摆烂”
序列级信号对齐：通过几何平均将 Token 级比值提升到序列级，消除了推荐场景下 Token 级优化的方差问题

6.2 工程创新
废弃 Semantic ID，直接使用原生文本：避免了量化编码带来的碰撞冲突和词表维护成本，同时激发 LLM 预训练语义知识
即插即用的优化器设计：SAGE 可以同时应用于 Semantic ID（OneRec-SAGE）和原生文本（TextRec）两种动作空间，具有强通用性
工业级验证：在包含 1.2 亿次真实交互的 RecIF-Bench 上验证了稳定性和有效性

七、局限性与未来研究方向

7.1 当前局限
论文主要在离线评估上验证，尚未公开在线 A/B 测试的完整结果
Boost Factor 和 Entropy Penalty 的超参数需要针对不同场景调优
原生文本生成的推理效率可能低于 Semantic ID 方案

7.2 未来方向
在线部署与实时优化：将 SAGE 部署到实际在线推荐系统，研究在线学习与实时更新的工程方案
更丰富的反馈信号：扩展到隐式反馈（停留时长、滑动速度等）和多模态信号
跨域迁移：研究 SAGE 在不同推荐场景（电商→短视频→新闻）间的迁移效果
与检索增强生成（RAG）的结合：在生成前引入候选物品召回阶段，提高工业场景的可行性
理论分析深化：进一步分析非对称 clipping 的收敛性保证和最优边界的理论表征

八、通俗理解

将大模型比作一个博览群书但不懂商业推销的天才图书管理员：

传统方案：强迫他用一套”摩斯密码”（Semantic ID）死记硬背书名，管理制度奖罚完全对称——推荐成功冷门好书只加 1 分，推荐同质化烂书只扣 1 分
SAGE 方案：让他直接用”人话”（原生文本）推荐；成功推荐冷门好书给予”超级加倍”奖励（Positive Boost），偷懒推同质化书籍时被监测到多样性极低（熵感知），给予严厉惩罚（Entropy-Aware Penalty）

通过这套”基于行为多样性的非对称胡萝卜加大棒”机制，SAGE 让推荐大模型告别了死记硬背和信息茧房，代表着生成式推荐系统的一次深刻工业级进化。

九、关键参考文献
OneRec: Zhou et al., 2025 — 阿里 Semantic ID 生成式推荐
TIGER: Rajput et al., 2023 — Google Semantic ID 推荐先驱
GBPO: 梯度受限策略优化（SAGE 的主要改进对象）
GDPO: 多目标解耦策略优化（SAGE 信号解耦模块的灵感来源）
PPO: Schulman et al. — 近端策略优化（SAGE 所属的算法族）
RecIF-Bench: 工业级推荐基准数据集（1.2 亿交互）

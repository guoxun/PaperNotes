# 一文读懂点击率预估模型：IJCAI 2021 | 华为与上海交大联合出品CTR模型综述《Deep Learning for Click-Through Rate Estimation》

> **原文链接**: [https://zhuanlan.zhihu.com/p/545545493](https://zhuanlan.zhihu.com/p/545545493)  
> **点赞数**: 30  
> **平台**: 知乎专栏

---

本文是IJCAI 2021收录的一篇华为出品的CTR预估模型的综述文章解读，该文由上海交通大学的Weinan Zhang老师与华为的Ruiming Tang老师等人合作发表在IJCAI-21(Survey Track)上。该综述高度抽象了ctr场景近年来模型的发展与迭代，以及架构演进。在本研究中，作者对运用于CTR预估任务的深度学习模型进行了全面回顾，对后续的点击率预估的模型创新、数据创新、架构创新提供了有效总结。


一.文章目录
摘要
1.背景
2.从浅到深的CTR模型
3.CTR的特征交互模块
3.1 特征交互
3.1.1 乘积Product Operators
3.1.2 卷积 Convolutional Operators
3.1.3 注意力Attention Operators
3.2 DNN在CTR模型中的作用
4.用户行为模型
4.1 基于注意力
4.2 基于记忆网络
4.3 基于检索模型
5. Automated Architecture Search
6.总结

二.摘要
这篇综述主要从以下方面对CTR进行总结：
1、回顾从浅到深的CTR模型，并解释该趋势出现的原因
2、重点研究CTR模型的特征交互模块
3、讨论基于用户行为的模型
4、模型自动搜索架构
5、总结

三.全文概要

注：思维导图链接


四.全文解读
1.背景
CTR模块即将点击作为用户偏好的特征行为，基于行为数据进行学习的点击率预估是这些个性化服务的核心功能模块。


2.从浅到深的CTR模型


2.1 logistic回归(LR)
[Richardson et al.， 2007] 是最基本的CTR模型：通过二分类完成预估。具有效率高、易于快速部署、快速挖掘有效特征的优点。

2.2 POLY2
[Chang et al.， 2010] 该模型为每个二阶组合特征分配一个权值，需要O(m2)参数空间。但是当数据稀疏时，POLY2的性能可能会比较差，如果存在许多特征从未或很少同时出现的情况，则无法正确地估计特征交互相关的参数。

2.3 因子分解机(FM)
[Rendle, 2010] FM是一个经典算法，为每个特征i分配一个k维可学习的嵌入向量vi，使模型能够以灵活的方式探索特征组合的有效性：
自2015年始，CTR开始通过深度学习来修改经典模型或开发新模型来提高性能。深度神经网络模型使捕获高阶特征交互模式并在CTR估计中获得更好的性能成为可能，利用每个稀疏(或分类)特征的向量表示，连接这些向量来构建实例密集向量，并将这些向量模拟地馈入具有s形输出的多层感知器(MLP)。


2.4 Wide & Deep network
[Cheng et al.， 2016]是最早发表的关于CTR估计的深度模型之一，该模型将LR(宽部)和DNN(深部)的logit值相加，然后输入最终的sigmoid函数。

2.5 DeepCross
[Shan et al.， 2016]对残差网络[He et al.， 2016]进行了扩展，以隐式方式进行自动特征交互学习。作者在后续章节讨论了深度构架框架下的特征设计、深度用户行为模型、自动架构搜索等方法。

3.CTR的特征交互模块
本文对现有的一些显式特征交互学习算子进行了详细的描述，然后讨论了DNN在模型结构中的作用。


3.1 特征交互
特征交互学习算法主要可分为三类，即乘积、卷积和注意力操作。其基本表达式如下：
3.1.1 乘积 Product Operators
Product-based Neural Network (PNN)引入一个product层来建模不同领域之间的特征交互（如图）。结果表明，增加乘积运算具有更好的收敛性，提高了网络的预测能力。
可参考：Product- Network In Network (PIN)、Cross Network V2 [Wang et al.， 2020]、Kernel Product Neural Network (KPNN)

3.1.2 卷积 Convolutional Operators
Convolutional Click Prediction Model, CCPM) [Liu et al.， 2015]反复进行卷积、池化和非线性激活，生成任意阶特征交互，如图(b)所示。
FGCNN验证了CNN生成的特征可以增强原始特征空间，降低现有深层结构的优化难度。特征交互图神经网络(FiGNN) 认为，使用简单非结构化特征场组合的现有深度模型在建模复杂特征交互方面能力有限。

3.1.3 注意力Attention Operators
CTR中，已有研究尝试利用注意机制进行特征交互建模。
注意因子分解机器(AFM)通过利用额外的注意力网络改进FM：将两个特征的成对交互向量输入注意力网络，计算该交互向量在每一步的分数，如图©所示。然后应用softmax函数对这些注意力分数进行归一化。最后，将这些注意力分数与相互作用的向量相乘，得出最终的预测结果。
Feature Importance and Bilinear Feature Interaction NETwork (FiBiNET)扩展了squeeze-excite NETwork (SENET)，然后使用一个双线性函数来学习特征的相互作用。
AutoInt [Song et al.， 2019]受self-attention启发，利用带有残差连接的多头自注意神经网络来建模不同顺序的特征交互，通过attention weights提供可解释的预测。
具有层次注意的可解释CTR预测模型(InterHAt) [Li et al.， 2020]将具有多个注意聚合层的变压器网络结合在一起进行特征交互学习，具有较高的训练效率和相当的性能，可以解释不同特征交互的重要性。

3.2 DNN在CTR模型中的作用
如图所示构建单塔网络或双塔网络。单塔模型将特征交互和深度网络依次置于模型中，如图(a)所示，可以有效地捕获高阶特征相互作用，但是低阶特征相互作用的信号可能在随后DNN网络中消失。
为了更好地捕捉低阶特征交互，提出了双塔网络：将特征交互层与DNN平行放置。特征交互层负责显式捕获低阶交互，而高阶交互则由DNN隐式捕获。两个模块的输出生成最终的预测。
NFM [He and Chua, 2017]和PIN [Qu et al.， 2018]等单塔模型具有更强的建模能力，网络结构更加复杂。Wide & Deep [Cheng et al.， 2016]， DeepFM [Guo et al.， 2017]， DCN [Wang et al.， 2017]， DCN V2 [Wang et al.， 2020]， xDeepFM [Lian et al.， 2018]和Autoint+ [Song et al.， 2019]均为双塔模型。将DNN部分作为学习特征交互层残差信号的补充，逼近标签，训练稳定，且性能有所提高。


4.用户行为模型

基本表达式如下：


4.1 基于注意力
Deep Interest Network (DIN) [Zhou et al.， 2018]是第一个在CTR估计任务的用户行为建模中引入注意机制的模型。通过注意机制，与优化目标的相关度，将不同的历史行为赋予不同的权重。
Deep Interest Evolution Network (DIEN) [Zhou et al.， 2019]是在DIN基础上将CTR估计任务的用户行为抽象为兴趣演化来引入注意机制的模型。它利用注意机制，抽象出行为序列层、兴趣抽取层、兴趣进化层，根据兴趣进化层与兴趣抽取层的注意力机制来抽象表达不同的历史行为。
Behavior Sequence Transformer (BST) [Chen et al.， 2019a]直接将多头注意层作为序列特征提取器，捕捉行为之间的依赖关系。
Deep Session Interest Network (DSIN) [Feng等人，2019]将用户行为分为多个会话看待。其利用带有偏差编码的自注意机制获取每个会话内部的准确行为表示，并借助Bi-LSTM来捕捉历史会话之间的顺序关系。以上模型说明了注意机制在用户行为建模中取得很好的收益。

4.2 基于记忆网络
由于大型电商平台积累了大量的用户行为数据，处理非常长的行为序列和挖掘较远的用户历史中的模式就显得非常重要。像DIN或DIEN这样的模型受时间复杂度的限制，它们在建模非常长的序列时是不可行的。因此，有了基于内存网络的模型Multi-channel user Interest Memory Network (MIMN)。

4.3 基于检索模型
User Behavior Retrieval (UBR4CTR) [Qin et al., 2020] 基于搜索引擎机制的模型。

5 Automated Architecture Search
5.1 Embedding维度搜索
Embedding表征是推荐场景的一个重要的方法论，如果能高效自动探索地优化embedding超参，就能找到提升模型性能的关键。可参考：Neural Input Search(NIS) 2020、Differentiable Neural Input Search(DNIS) 2020、Automated embedding size search(AutoEmb) 2020、AutoDim 2020、PEP 2021。


5.2 特征交互搜索
特征交叉的自动搜索是一个很有大潜力和挑战的方向。可考虑在大规模特征基础上，尝试这个方向。如AutoFIS，该模型可自动识别分解出模型中重要的特征交叉，而计算量仅相当于训练目标模型以实现收敛。在搜索阶段，没有在整个离散特征集中搜索，而是通过结构参数（连续值）来放松选择。通过对体系结构参数实施正则化优化器，该模型可以在模型训练过程中自动识别并删除多余的特征交叉。并且在第二次训练阶段，将该结构参数作为注意力单元，实现性能的进一步提高。
可参考：Automatic Feature Interaction Selection (AutoFIS)2020、Effificient Neural Interaction Function Search (SIF)2020、Searching for Feature Interactions (AutoFeature)2020、Automatic Feature Grouping (AutoGroup)2020、Bayesian Personalized Feature Interaction Selection (BP-FIS)2020。

5.3 整个CTR模型结构搜索
整个模型架构的搜索是一个探索较少，但比较有价值的方向。例如AutoCTR框架，通过将简单有效的表示交互模块化为组件，并将这些组件放入一个有向无环图的空间中，AutoCTR通过自动探索学习到最有效的网络交互结构。
可参考：AutoCTR 2020、Automatic Behavior Modeling and Interaction Exploration (AMER) 2020。

6.总结
尽管深度学习在CTR估计方面取得了快速的发展和巨大的成功，但仍有一些重大挑战需要解决：
• 深度学习理论。关于CTR模型的设计已有大量的工作，但对模型的深度学习理论，包括样本复杂度分析、特征交互层的学习行为、梯度分析等方面的研究很少。
• 特征学习。与文本、图等其他离散数据一样，多领域分类数据的表示学习(或称预训练)可以极大地提高CTR预测性能。然而，据我们所知，到目前为止，关于这一观点的现有工作很少。
• 通过多模式数据进行学习。在现代信息系统中，有各种各样的多媒体元素的条目或浏览环境。因此，设计CTR估计模型来处理多模态数据上的特征交互具有很大的潜力。
• 策略性数据处理。用户历史行为获取策略(如用户行为检索和排序)的最新进展表明，数据处理与深度模型设计相结合的方法具有巨大的潜力。使这些数据处理变得可学习，将具有很高的研究价值。

参考文献
[1] Deep Learning for Click-Through Rate Estimation. IJCAI, 2021.
[2] https://zhuanlan.zhihu.com/p/367942611
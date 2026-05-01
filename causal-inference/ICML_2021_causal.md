# ICML 2021 | 因果推断论文集锦，从推荐系统角度出发

> **原文链接**: [https://zhuanlan.zhihu.com/p/433260334](https://zhuanlan.zhihu.com/p/433260334)  
> **点赞数**: 165  
> **平台**: 知乎专栏

---

ICML-2021放榜近半年，笔者就因果推断方向，总结了今年ICML相关的一些论文，含中文题目。因果推断以及因果发现等是未来推荐系统进化以及增长的一个强大的数据挖掘武器，如果能够有效利用因果推断能力，能够为推荐系统的生态良性和实质增长贡献可靠能力。以下是本人整理选取的十几篇今年ICML因果相关专题的论文，涉及的因果细分方向有：因果发现、因果结构学习、贝叶斯学习、因果强化学习、因果推断、因果深度学习、因果对抗学习等。相比于今年NIPS，ICML中因果相关的论文，涉及贝叶斯优化比较多。我个人认为比较有价值的文章，会标注星号，欢迎大家浏览评论。

参考ICML今年接受论文的List:

[ICML 2021](https://link.zhihu.com/?target=https%3A//icml.cc/Conferences/2021/Schedule%3Ftype%3DPoster)

## 1.因果发现

因果发现是通过对相关数据进行算法发掘，从而提取因果关系。这在推荐系统的数据分析中十分重要，尤其是特征分析、效果分析。是增长模型的利器，未来需要重点关注。今年ICML因果发现相关的文章较少，但每篇都值得深入学习。

***Causal Curiosity: RL Agents Discovering Self-supervised Experiments for Causal Representation Learning**

Sumedh Sontakke · Arash Mehrjou · Laurent Itti · Bernhard Schölkopf

因果好奇心:发现因果表征学习自我监督实验的RL代理

***Necessary and sufficient conditions for causal feature selection in time series with latent common causes**

Atalanti Mastakouri · Bernhard Schölkopf · Dominik Janzing

具有潜在共同原因的时间序列中因果特征选择的充分必要条件

## 2.因果推断

这个方向是因果推断方向，相对基础的方向，比较侧重于数据本身与因果的关系。今年有一些涉及实验方法、策略评估以及可解释性相关的文章。

**Proximal Causal Learning with Kernels: Two-Stage Estimation and Moment Restriction**

Afsaneh Mastouri · Yuchen Zhu · Limor Gultchin · Anna Korba · Ricardo Silva · Matt J. Kusner · Arthur Gretton · Krikamol Muandet

核的近端因果学习:两阶段估计和矩约束

**Model-Free and Model-Based Policy Evaluation when Causality is Uncertain**

David Bruns-Smith

因果关系不确定时的无模型和基于模型的策略评估

***How and Why to Use Experimental Data to Evaluate Methods for Observational Causal Inference**

Amanda Gentzel · Purva Pruthi · David Jensen

如何以及为什么使用实验数据来评价观察性因果推理方法

**Quantifying Ignorance in Individual-Level Causal-Effect Estimates under Hidden Confounding**

Andrew Jesson · Sören Mindermann · Yarin Gal · Uri Shalit

隐藏混淆下个体水平因果效应估计中的无知量化

***Generative Causal Explanations for Graph Neural Networks**

Wanyu Lin · Hao Lan · Baochun Li

图神经网络的生成因果解释

**Domain Generalization using Causal Matching**

Divyat Mahajan · Shruti Tople · Amit Sharma

使用因果匹配的领域泛化

**Regularizing towards Causal Invariance: Linear Models with Proxies**

Michael Oberst · Nikolaj Thams · Jonas Peters · David Sontag

面向因果不变性的正则化:具有代理的线性模型

**Estimating Identifiable Causal Effects on Markov Equivalence Class through Double Machine Learning**

Yonghan Jung · Jin Tian · Elias Bareinboim

利用双机器学习估计马尔可夫等价类的可识别因果效应

***Causality-aware counterfactual confounding adjustment as an alternative to linear residualization in anticausal prediction tasks based on linear learners**

Elias Chaibub Neto

因果意识反事实混淆调整替代线性残差在线性学习者反因果预测任务中的应用

***Valid Causal Inference with (Some) Invalid Instruments**

Jason Hartford · Victor Veitch · Dhanya Sridhar · Kevin Leyton-Brown

有效的因果推理与(一些)无效工具

**Multiscale Invertible Generative Networks for High-Dimensional Bayesian Inference**

Shumao Zhang · Pengchuan Zhang · Thomas Hou

用于高维贝叶斯推理的多尺度可逆生成网络

**Differentially Private Bayesian Inference for Generalized Linear Models**

Tejas Kulkarni · Joonas Jälkö · Antti Koskela · Samuel Kaski · Antti Honkela

广义线性模型的差分私有贝叶斯推理

## 3.因果结构学习

因果结构学习本质上是通过拓扑结构来描述因果关系，从而更好地从不同尺度来反映因果关系的强度。落地有推荐场景的根因分析，特征有效性根因分析等，因果结构学习是一个重要的方向。今年有涉及整数规划方法、子结构深度学习等。

***Integer Programming for Causal Structure Learning in the Presence of Latent Variables**

Rui Chen · Sanjeeb Dash · Tian Gao

潜在变量存在时因果结构学习的整数规划

**Global inducing point variational posteriors for Bayesian neural networks and deep Gaussian processes**

Sebastian Ober · Laurence Aitchison

贝叶斯神经网络和深度高斯过程的全局诱导点变分后验

***Bayesian Deep Learning via Subnetwork Inference**

Erik Daxberger · Eric Nalisnick · James Allingham · Javier Antorán · Jose Miguel Hernandez-Lobato

基于子网络推理的贝叶斯深度学习

**What Are Bayesian Neural Network Posteriors Really Like?**

Pavel Izmailov · Sharad Vikram · Matthew Hoffman · Andrew Wilson

贝叶斯神经网络后验到底在模仿什么?

***Active Learning of Continuous-time Bayesian Networks through Interventions**

Dominik Linzner · Heinz Koeppl

通过干预的连续时间贝叶斯网络主动学习

***Training Adversarially Robust Sparse Networks via Bayesian Connectivity Sampling**

Ozan Özdenizci · Robert Legenstein

基于贝叶斯连通性采样的对抗鲁棒稀疏网络训练

***Bayesian Structural Adaptation for Continual Learning**

Abhishek Kumar · Sunabha Chatterjee · Piyush Rai

持续学习的贝叶斯结构适应

***On Recovering from Modeling Errors Using Testing Bayesian Networks**

Haiying Huang · Adnan Darwiche

利用贝叶斯网络测试从建模错误中恢复

## 4.贝叶斯优化

贝叶斯是因果方向的一种基础工具，我们可以为我们的方法找到理论依据和优化工具。今年ICML有很多文章都涉及贝叶斯优化，可以看到ICML对这个方向的重视程度超过NIPS。

***Bayesian Optimization over Hybrid Spaces**

Aryan Deshwal · Syrine Belakaria · Jana Doppa

混合空间上的贝叶斯优化

***Bias-Robust Bayesian Optimization via Dueling Bandits**

Johannes Kirschner · Andreas Krause

基于对抗博弈的偏鲁棒贝叶斯优化

**BORE: Bayesian Optimization by Density-Ratio Estimation**

Louis Chi-Chun Tiao · Aaron Klein · Matthias W Seeger · Edwin V Bonilla · Cedric Archambeau · Fabio Ramos

BORE:基于密度比估计的贝叶斯优化

***Policy Gradient Bayesian Robust Optimization for Imitation Learning**

Zaynah Javed · Daniel Brown · Satvik Sharma · Jerry Zhu · Ashwin Balakrishna · Marek Petrik · Anca Dragan · Ken Goldber

模仿学习的策略梯度贝叶斯鲁棒优化

***Think Global and Act Local: Bayesian Optimisation over High-Dimensional Categorical and Mixed Search Spaces**

Xingchen Wan · Vu Nguyen · Huong Ha · Binxin Ru · Cong Lu · Michael A Osborne

全局思维和局部行动:高维分类和混合搜索空间上的贝叶斯优化

**A Bit More Bayesian: Domain-Invariant Learning with Uncertainty**

Zehao Xiao · Jiayi Shen · Xiantong Zhen · Ling Shao · Cees Snoek

更多的贝叶斯:不确定性领域不变性学习

**Bayesian Optimistic Optimisation with Exponentially Decaying Regret**

Hung Tran-The · Sunil Gupta · Santu Rana · Svetha Venkatesh

带指数衰减遗憾的贝叶斯乐观优化

**Collaborative Bayesian Optimization with Fair Regret**

Rachael Hwee Ling Sim · Yehong Zhang · Bryan Kian Hsiang Low · Patrick Jaillet

带公平遗憾的协作贝叶斯优化

**Rate-Distortion Analysis of Minimum Excess Risk in Bayesian Learning**

Hassan Hafez-Kolahi · Behrad Moniri · Shohreh Kasaei · Mahdieh Soleymani Baghshah

贝叶斯学习中最小超额风险的失真率分析

**Multi-Receiver Online Bayesian Persuasion**

Matteo Castiglioni · Alberto Marchesi · Andrea Celli · Nicola Gatti

多接收者在线贝叶斯说服

**Bayesian Quadrature on Riemannian Data Manifolds**

Christian Fröhlich · Alexandra Gessner · Philipp Hennig · Bernhard Schölkopf · Georgios Arvanitidis

黎曼数据流形的贝叶斯正交

***Deep Adaptive Design: Amortizing Sequential Bayesian Experimental Design**

Adam Foster · Desi Ivanova · ILYAS MALIK · Tom Rainforth

深度自适应设计:摊销式序列贝叶斯实验设计

***Bayesian Algorithm Execution: Estimating Computable Properties of Black-box Functions Using Mutual Information**

Willie Neiswanger · Ke Alexander Wang · Stefano Ermon

贝叶斯算法的执行:利用互信息估计黑盒函数的可计算性

**Objective Bound Conditional Gaussian Process for Bayesian Optimization**

Taewon Jeong · Heeyoung Kim

基于贝叶斯优化的目标有界条件的高斯过程

**Overcoming Catastrophic Forgetting by Bayesian Generative Regularization**

PEI-HUNG Chen · Wei Wei · Cho-Jui Hsieh · Bo Dai

通过贝叶斯生成正则化克服灾难性遗忘

## 5.贝叶斯深度学习

贝叶斯结合深度学习的方向。通过深度学习方法来探究因果相关问题，也是近年比较多的做法。

***Bayesian Attention Belief Networks**

Shujian Zhang · Xinjie Fan · Bo Chen · Mingyuan Zhou

基于注意力机制的贝叶斯信念网络

**Deep Adaptive Design: Amortizing Sequential Bayesian Experimental Design**

Adam Foster · Desi Ivanova · ILYAS MALIK · Tom Rainforth

深度自适应设计:摊销式序列贝叶斯实验设计

**Streaming Bayesian Deep Tensor Factorization**

Shikai Fang · Zheng Wang · Zhimeng Pan · Ji Liu · Shandian Zhe

流贝叶斯深度张量分解

***Bayesian Deep Learning via Subnetwork Inference**

Erik Daxberger · Eric Nalisnick · James Allingham · Javier Antorán · Jose Miguel Hernandez-Lobato

基于子网络推理的贝叶斯深度学习

## 参考资料：

[ICML 2021](https://link.zhihu.com/?target=https%3A//icml.cc/Conferences/2021/Schedule%3Ftype%3DPoster)

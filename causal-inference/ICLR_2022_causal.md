# ICLR 2022 | 因果推断论文精选[持续更新]

> **原文链接**: [https://zhuanlan.zhihu.com/p/469540097](https://zhuanlan.zhihu.com/p/469540097)  
> **点赞数**: 77  
> **平台**: 知乎专栏

---

ICLR-2022刚刚放榜，笔者总结了今年ICLR因果推断方向的一些论文，含中文参考。就今年因果方向的文章来说，整体价值较高，对因果推断落地较困难的问题，有一些有价值的探讨。关键点比如：可有环(without Acyclicity)因果推断、因果图抽样、因果对抗学习、重叠因果效应。其中，可有环推断、连续值图抽样、重叠因果效应三个问题都是传统贝叶斯因果网络无法解决的问题，含金量十足。

以下是笔者整理选取的24篇(2篇Oral、5篇SpotLight)今年ICLR因果相关专题的论文，涉及的因果细分方向有：因果发现、因果结构学习、因果强化学习、因果对抗学习、因果推断、因果深度学习、因果表示学习等。因果推断以及因果发现等是未来机器学习系统进化的一个强大数据挖掘武器，如果能够有效利用因果推断能力，能够为机器学习系统的生态良性和实质增长贡献价值，如推荐系统场景、视觉场景、AI制药场景，具体到疫情预测、药物结构、增长归因等等场景。相比于今年AAAI，ICLR的文章更多是融合因果推断与机器学习方法来进行创新，价值更高。我个人认为比较有价值的文章，会标注*号，欢迎大家浏览评论。


一.因果发现

因果发现是通过对相关数据进行算法发掘，从而提取因果关系。在推荐系统的数据分析中比较重要，尤其是特征分析、效果分析、可解释性分析等。是增长模型的利器，未来需要重点关注。

*1.Optimal Transport for Causal Discovery

Ruibo Tu, Kun Zhang, Hedvig Kjellstrom, Cheng Zhang

因果发现的最佳转化 (Spot light)


*2.Learning Causal Relationships from Conditional Moment Restrictions by Importance Weighting

Masahiro Kato, Masaaki Imaizumi, Kenichiro McAlinn, Shota Yasui, Haruo Kakehi

通过重要性加权从条件矩约束学习因果关系(Spot light)


3.Distributional Decision Transformer for Hindsight Information Matching

Hiroki Furuta, Yutaka Matsuo, Shixiang Shane Gu

用于后知信息匹配的分布式决策变压器(Spot light)


**4.Meta Discovery: Learning to Discover Novel Classes given Very Limited Data

Haoang Chi, Feng Liu, Wenjing Yang, Long Lan, Tongliang Liu, Bo Han, Gang Niu, Mingyuan Zhou, Masashi Sugiyama

元发现:学习在非常有限的数据下发现新颖的类(Spot light)


*5.Efficient Neural Causal Discovery without Acyclicity Constraints

Phillip Lippe, Taco Cohen, Efstratios Gavves

没有无环约束的高效神经网络因果发现

注：Acyclicity Constraints一直是传统因果发现的一个难以逾越的障碍，这篇文章值得深入阅读。


6.Discovering Invariant Rationales for Graph Neural Networks

Yingxin Wu, Xiang Wang, An Zhang, Xiangnan He, Tat-Seng Chua

发现图神经网络的恒定关系


7.GeneDisco: A Benchmark for Experimental Design in Drug Discovery

Arash Mehrjou, Ashkan Soleymani, Andrew Jesson, Pascal Notin, Yarin Gal, Stefan Bauer, Patrick

GeneDisco:药物发现实验设计的基准


二.因果结构学习

因果结构学习本质上是通过拓扑结构来描述因果关系，从而更好地从不同尺度来反映因果关系的强度。落地有推荐场景的根因分析，特征有效性根因分析等，因果结构学习是一个重要的方向。今年主要为多重数据挖掘场景的应用。

8.Granger causal inference on DAGs identifies genomic loci regulating transcription

Alexander P Wu, Rohit Singh, Bonnie Berger

通过DAGs的Granger因果推断识别调控转录的基因组位点


**9.Differentiable DAG Sampling

Bertrand Charpentier, Simon Kibler, Stephan Günnemann

可微的有向无环图抽样

注：DAG的连续抽样也是以前贝叶斯因果网络无法实现的能力，这篇文章从数据生成角度来说很有参考意义。


三.因果对抗学习

对抗样本广泛的存在于机器学习场景当中，因果推断也不例外。

*10.Adversarial Robustness Through the Lens of Causality

Yonggang Zhang, Mingming Gong, Tongliang Liu, Gang Niu, Xinmei Tian, Bo Han, Bernhard Schölkopf, Kun Zhang

从因果关系的角度看对抗鲁棒性


四.因果推断

这个方向是因果推断方向，比较侧重于数据本身与因果的关系。今年有一些涉及时间序列、重叠因果效应、轨迹预测、推荐系统优化等场景的文章。

11.Learning Temporally Latent Causal Processes from General Temporal Data

Weiran Yao, Yuewen Sun, Alex Ho, Changyin Sun, Kun Zhang

从一般时间数据中学习时间潜在的因果过程


12.CoST: Contrastive Learning of Disentangled Seasonal-Trend Representations for Time Series Forecasting

Gerald Woo, Chenghao Liu, Doyen Sahoo, Akshat Kumar, Steven Hoi

CoST:时间序列预测中解开的季节趋势表示的对比学习


**13.$\beta$-Intact-VAE: Identifying and Estimating Causal Effects under Limited Overlap

Pengzhou Abel Wu, Kenji Fukumizu

$\beta$-Intact-VAE: 识别和估计有限重叠下的因果效应

注：重叠因果效应往往是伴随着有环因果图存在的问题，也是以前难以克服的问题，这篇文章值得深入学习。


14.You Mostly Walk Alone: Analyzing Feature Attribution in Trajectory Prediction

Osama Makansi, Julius Von Kügelgen, Francesco Locatello, Peter Vincent Gehler, Dominik Janzing, Thomas Brox, Bernhard Schölkopf

独自行进:在轨迹预测中分析特征属性


15.From Intervention to Domain Transportation: A Novel Perspective to Optimize Recommendation

Da Xu, Yuting Ye, Chuanwei Ruan, Evren Korpeoglu, Sushant Kumar, Kannan Achan

从干预到领域转移:优化推荐的新视角


16.Autoregressive Diffusion Models

Emiel Hoogeboom, Alexey A. Gritsenko, Jasmijn Bastings, Ben Poole, Rianne van den Berg, Tim Salimans

自回归扩散模型传态:优化推荐的新视角


17.Huber Additive Models for Non-stationary Time Series Analysis

Yingjie Wang, Xianrui Zhong, Fengxiang He, Hong Chen, Dacheng Tao

非平稳时间序列分析的Huber可加模型


18.Graph-Augmented Normalizing Flows for Anomaly Detection of Multiple Time Series

Enyan Dai, Jie Chen

基于图形增强归一化流的多时间序列异常检测


*19.Asymmetry Learning for Counterfactually-invariant Classification in OOD Tasks

S Chandra Mouli, Bruno Ribeiro

OOD任务中反事实不变分类的非对称学习(Oral)

*20.Filtered-CoPhy: Unsupervised Learning of Counterfactual Physics in Pixel Space

Steeven JANNY, Fabien Baradel, Natalia Neverova, Madiha Nadri, Greg Mori, Christian Wol

过滤复制:像素空间中反事实物理的无监督学习(Oral)


五.因果深度学习

通过深度学习方法来解决因果相关问题，也是近年因果问题的主流做法。涉及的方法主要有GNN以及因果ImageNet。

**21.Causal ImageNet: How to discover spurious features in Deep Learning?

Sahil Singla, Soheil Feizi

因果ImageNet:如何发现深度学习中的伪特征?


21.Discovering Invariant Rationales for Graph Neural Networks

Yingxin Wu, Xiang Wang, An Zhang, Xiangnan He, Tat-Seng Chua

发现图神经网络的恒定关系


六.因果强化学习

强化学习和因果关系的结合是一个较热的方向，也是强化学习当中反对大规模数据暴力强化学习的有力理论支撑。因果推断相关方法反对暴力强化学习，既只依赖数据规模、数据多样性就能依靠现有深度学习方法解决强化学习场景的问题。

22.Causal Contextual Bandits with Targeted Interventions

Chandrasekar Subramanian, Balaraman Ravindran

有针对性干预的因果上下文Bandits


23.On Covariate Shift of Latent Confounders in Imitation and Reinforcement Learning

Guy Tennenholtz, Assaf Hallak, Gal Dalal, Shie Mannor, Gal Chechik, Uri Shalit

模仿与强化学习中潜在混杂变量的协变量转移


七.因果表示学习

今年有一篇涉及因果图表示学习的文章，来自于Schölkopf团队。

24.Invariant Causal Representation Learning for Out-of-Distribution Generalization

Chaochao Lu, Yuhuai Wu, José Miguel Hernández-Lobato, Bernhard Schölkopf

非分布泛化的不变因果表示学习


参考：
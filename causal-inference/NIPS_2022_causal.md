# NIPS 2022 | 因果推断论文精选[持续更新]

> **原文链接**: [https://zhuanlan.zhihu.com/p/588978133](https://zhuanlan.zhihu.com/p/588978133)  
> **点赞数**: 55  
> **平台**: 知乎专栏

---

NIPS-2022刚刚放榜，笔者总结了今年NIPS因果推断方向的一些论文，含中文参考。就今年因果方向的文章来说，通过因果推断解决实际问题的文章不少。更是有文章通过因果推断来解构一些宏大的问题。

以下是笔者整理选取的今年49篇因果相关专题的论文，涉及的因果细分方向有：因果发现、因果结构学习、因果强化学习、因果对抗学习、因果推断、因果深度学习、因果表示学习、因果可解释性等。因果推断以及因果发现等是未来机器学习系统进化的一个强大数据挖掘武器，如果能够有效利用因果推断能力，能够为机器学习系统的生态良性和实质增长贡献价值，如推荐系统场景、视觉场景、AI制药场景，具体到疫情预测、药物结构、增长归因等等场景。我个人认为比较有价值的文章，会标注*号，欢迎大家浏览评论。

一.因果发现

因果发现是通过对相关数据进行算法发掘，从而提取因果关系。在推荐系统的数据分析中比较重要，尤其是特征分析、效果分析、可解释性分析、根因分析等。是增长模型的利器，未来需要重点关注。

Root Cause Analysis of Failures in Microservices through Causal Discovery

Azam Ikram · Sarthak Chakraborty · Subrata Mitra · Shiv Saini · Saurabh Bagchi · Murat Kocaoglu

Unsupervised Causal Generative Understanding of Images

Titas Anciukevicius · Patrick Fox-Roberts · Edward Rosten · Paul Henderson

Large-Scale Differentiable Causal Discovery of Factor Graphs

Romain Lopez · Jan-Christian Huetter · Jonathan Pritchard · Aviv Regev

Sound and Complete Causal Identification with Latent Variables Given Local Background Knowledge

Tian-Zuo Wang · Tian Qin · Zhi-Hua Zhou

A Causal Analysis of Harm

Sander Beckers · Hana Chockler · Joseph Halpern

Conditional Independence Testing with Heteroskedastic Data and Applications to Causal Discovery

Wiebke Günther · Urmi Ninad · Jonas Wahl · Jakob Runge

Causal Discovery in Heterogeneous Environments Under the Sparse Mechanism Shift Hypothesis

Ronan Perry · Julius von Kügelgen · Bernhard Schölkopf

Causal Discovery in Linear Latent Variable Models Subject to Measurement Error

Yuqin Yang · AmirEmad Ghassami · Mohamed Nafea · Negar Kiyavash · Kun Zhang · Ilya Shpitser

Bivariate Causal Discovery for Categorical Data via Classification with Optimal Label Permutation

Yang N

Independence Testing-Based Approach to Causal Discovery under Measurement Error and Linear Non-Gaussian Models

Haoyue Dai · Peter Spirtes · Kun Zhang

二.因果结构学习

因果结构学习本质上是通过拓扑结构来描述因果关系，从而更好地从不同尺度来反映因果关系的强度。落地有推荐场景的根因分析，特征有效性根因分析等，因果结构学习是一个重要的方向。今年主要为多重约束场景的应用。

Debiasing Graph Neural Networks via Learning Disentangled Causal Substructure

Shaohua Fan · Xiao Wang · Yanhu Mo · Chuan Shi · Jian Tang

Verification and search algorithms for causal DAGs

Davin Choo · Kirankumar Shiragur · Arnab Bhattacharyya

Counterfactual Fairness with Partially Known Causal Graph

Aoqi Zuo · Susan Wei · Tongliang Liu · Bo Han · Kun Zhang · Mingming Gong

*Deep Multi-Modal Structural Equations For Causal Effect Estimation With Unstructured Proxies

Shachi Deshpande · Kaiwen Wang · Dhruv Sreenivas · Zheng Li · Volodymyr Kuleshov

Amortized Inference for Causal Structure Learning

Lars Lorch · Scott Sussex · Jonas Rothfuss · Andreas Krause · Bernhard Schölkopf

*Latent Hierarchical Causal Structure Discovery with Rank Constraints

Biwei Huang · Charles Jia Han Low · Feng Xie · Clark Glymour · Kun Zhang

三.因果对抗学习

对抗样本广泛的存在于机器学习场景当中，因果推断也不例外。今年是一篇涉及因果鲁棒性的文章。

In the Eye of the Beholder: Robust Prediction with Causal User Modeling

Amir Feder · Guy Horowitz · Yoav Wald · Roi Reichart · Nir Rosenfeld

四.因果推断

这个方向是因果推断方向，比较侧重于数据本身与因果的关系。今年有一些涉及因果效应估计、Non-IID等场景的文章。

Disentangling Causal Effects from Sets of Interventions in the Presence of Unobserved Confounders

Olivier Jeunen · Ciarán Gilligan-Lee · Rishabh Mehrotra · Mounia Lalmas


Generalization Bounds for Estimating Causal Effects of Continuous Treatments

Xin Wang · Shengfei Lyu · Xingyu Wu · Tianhao Wu · Huanhuan Chen


Debiased Causal Tree: Heterogeneous Treatment Effects Estimation with Unmeasured Confounding

Caizhi Tang · Huiyuan Wang · Xinyu Li · Qing Cui · Ya-Lin Zhang · Feng Zhu · Longfei Li · Jun Zhou · Linbo Jiang


Empirical Gateaux Derivatives for Causal Inference

Michael Jordan · Yixin Wang · Angela Zhou

*Counterfactual Neural Temporal Point Process for Estimating Causal Influence of Misinformation on Social Media

Yizhou Zhang · Defu Cao · Yan Liu

Towards Out-of-Distribution Sequential Event Prediction: A Causal Treatment

Chenxiao Yang · Qitian Wu · Qingsong Wen · Zhiqiang Zhou · Liang Sun · Junchi Yan

Causally motivated multi-shortcut identification and removal

Jiayun Zheng · Maggie Makar

Active Bayesian Causal Inference

Christian Toth · Lars Lorch · Christian Knoll · Andreas Krause · Franz Pernkopf · Robert Peharz · Julius von Kügelgen

*Causal Inference with Non-IID Data using Linear Graphical Models

Chi Zhang · Karthika Mohan · Judea Pearl

Interpolation and Regularization for Causal Learning

Leena Chennuru Vankadara · Luca Rendsburg · Ulrike Luxburg · Debarghya Ghoshdastidar

Invariant and Transportable Representations for Anti-Causal Domain Shifts

Yibo Jiang · Victor Veitch

*An Adaptive Kernel Approach to Federated Learning of Heterogeneous Causal Effects

Thanh Vinh Vo · Arnab Bhattacharyya · Young Lee · Tze-Yun Leong

Interventions, Where and How? Experimental Design for Causal Models at Scale

Panagiotis Tigas · Yashas Annadani · Andrew Jesson · Bernhard Schölkopf · Yarin Gal · Stefan Bauer

Scalable Sensitivity and Uncertainty Analyses for Causal-Effect Estimates of Continuous-Valued Interventions

Andrew Jesson · Alyson Douglas · Peter Manshausen · Nicolai Meinshausen · Philip Stier · Yarin Gal · Uri Shalit

Causal Identification under Markov equivalence: Calculus, Algorithm, and Completeness

Amin Jaber · Adele Ribeiro · Jiji Zhang · Elias Bareinboim

Falsification before Extrapolation in Causal Effect Estimation

Zeshan M Hussain · Michael Oberst · Ming-Chieh Shih · David Sontag

*CEBaB: Estimating the Causal Effects of Real-World Concepts on NLP Model Behavior

Eldar D Abraham · Karel D&#x27;Oosterlinck · Amir Feder · Yair Gat · Atticus Geiger · Christopher Potts · Roi Reichart · Zhengxuan Wu

Staggered Rollout Designs Enable Causal Inference Under Interference Without Network Knowledge

Mayleen Cortez · Matthew Eichhorn · Christina Yu

五.因果深度学习

通过深度学习方法来解决因果相关问题，也是近年因果问题的主流做法。涉及的方法主要有GAN、生成模型以及去偏。

ConfounderGAN: Protecting Image Data Privacy with Causal Confounder

Qi Tian · Kun Kuang · Kelu Jiang · Furui Liu · Zhihua Wang · Fei Wu

[Re] Replication Study of DECAF: Generating Fair Synthetic Data Using Causally-Aware Generative Networks

Velizar Shulev · Paul Verhagen · Shuai Wang · Jennifer Zhuge

Causality Preserving Chaotic Transformation and Classification using Neurochaos Learning

Harikrishnan N B · Aditi Kathpalia · Nithin Nagaraj

DeepMed: Semiparametric Causal Mediation Analysis with Debiased Deep Learning

Siqi Xu · Lin Liu · Zhonghua Liu

MissDAG: Causal Discovery in the Presence of Missing Data with Continuous Additive Noise Models

Erdun Gao · Ignavier Ng · Mingming Gong · Li Shen · Wei Huang · Tongliang Liu · Kun Zhang · Howard Bondell

Using Embeddings for Causal Estimation of Peer Influence in Social Networks

Irina Cristali · Victor Veitch

六.因果强化学习

强化学习和因果关系的结合是一个较热的方向，也是强化学习当中反对大规模数据暴力强化学习的有力理论支撑。因果推断相关方法反对暴力强化学习，既只依赖数据规模、数据多样性就能依靠现有深度学习方法解决强化学习场景的问题。今年涉及到的文章有因果驱动强化学习、因果归因生成等。

Adaptively Exploiting d-Separators with Causal Bandits

Blair Bilodeau · Linbo Wang · Dan Roy

*Causality-driven Hierarchical Structure Discovery for Reinforcement Learning

shaohui peng · Xing Hu · Rui Zhang · Ke Tang · Jiaming Guo · Qi Yi · Ruizhi Chen · xishan zhang · Zidong Du · Ling Li · Qi Guo · Yunji Chen

Generalizing Goal-Conditioned Reinforcement Learning with Variational Causal Reasoning

Wenhao Ding · Haohong Lin · Bo Li · DING ZHAO

七.因果表示学习

今年有3篇涉及因果图表示学习的文章，涉及图相关。

Learning Causally Invariant Representations for Out-of-Distribution Generalization on Graphs

Yongqiang Chen · Yonggang Zhang · Yatao Bian · Han Yang · MA Kaili · Binghui Xie · Tongliang Liu · Bo Han · James Cheng

Multi-Instance Causal Representation Learning for Instance Label Prediction and Out-of-Distribution Generalization

Weijia Zhang · Xuanhui Zhang · hanwen deng · Min-Ling Zhang

Weakly supervised causal representation learning

Johann Brehmer · Pim de Haan · Phillip Lippe · Taco Cohen

八.因果可解释性

今年的因果可解释性文章比较意思，想从物理上解释人为什么能利用因果武器。

Explainability Via Causal Self-Talk

Nicholas Roy · Junkyung Kim · Neil Rabinowitz

*CLEVRER-Humans: Describing Physical and Causal Events the Human Way

Jiayuan Mao · Xuelin Yang · Xikun Zhang · Noah Goodman · Jiajun Wu
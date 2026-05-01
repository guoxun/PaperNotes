# Recsys2021 | 推荐系统论文整理与导读

> **原文链接**: [https://zhuanlan.zhihu.com/p/424991459](https://zhuanlan.zhihu.com/p/424991459)  
> **点赞数**: 108  
> **平台**: 知乎专栏

---

参考机器学习与推荐算法公众号作者蘑菇先生的内容，整理了Recsys2021的各个方向的文章。

1.1 信息茧房和回音室

信息茧房(echo chamber、filter bubble)。即为使用社交媒体以及带有推荐算法功能的资讯类APP，可能会导致用户只看得到自己感兴趣的、认同的内容，进而让大家都活在自己的小世界里，彼此之间难以认同和沟通。关于这部分的概念可参见知乎文章：https://zhuanlan.zhihu.com/p/71844281。

The Dual Echo Chamber: Modeling Social Media Polarization for Interventional RecommendingTim Donkers and Jürgen Ziegler
I want to break free! Recommending friends from outside the echo chamberAntonela Tommasel, Juan Manuel Rodriguez, and Daniela Godoy
Follow the guides: disentangling human and algorithmic curation in online music consumptionQuentin Villermet, Jérémie Poiroux, Manuel Moussallam, Thomas Louail, and Camille Roth
An Audit of Misinformation Filter Bubbles on YouTube: Bubble Bursting and Recent Behavior ChangesMatus Tomlein, Branislav Pecher, Jakub Simko, Ivan Srba, Robert Moro, Elena Stefancova, Michal Kompan, Andrea Hrckova, Juraj Podrouzek, and Maria Bielikova
1.2 探索与利用

此次大会继续在往年的基础上，在探索与利用上有一些新的发展，例如多臂老虎机。

Burst-induced Multi-Armed Bandit for Learning RecommendationRodrigo Alves, Antoine Ledent, and Marius Kloft
Values of User Exploration in Recommender SystemsGoogle, Minmin Chen, Yuyan Wang, Can Xu, Ya Le, mohit sharma, Lee Richardson, and Ed Chi
Designing Online Advertisements via Bandit and Reinforcement LearningYusuke Narita, Shota Yasui, and Kohei Yata
The role of preference consistency, defaults and musical expertise in users’ exploration behavior in a genre exploration recommenderYu Liang and Martijn C. Willemsen
Top-K Contextual Bandits with Equity of ExposureOlivier Jeunen and Bart Goethals
1.3 偏差与纠偏

涉及排序学习的纠偏(debias)、用户的偏差探索等。

Debiased Explainable Pairwise Ranking from Implicit Feedback

Khalil Damak, Sami Khenissi, and Olfa Nasraoui

Mitigating Confounding Bias in Recommendation via Information Bottleneck

Dugang Liu, Pengxiang Cheng, Hong Zhu, Zhenhua Dong, Xiuqiang He, Weike Pan, and Zhong Ming

User Bias in Beyond-Accuracy Measurement of Recommendation Algorithms

Ningxia Wang, and Li Chen

1.4 冷启动

通过图学习、表征学习来完成冷启动。

Cold Start Similar Artists Ranking with Gravity-Inspired Graph Autoencoders

Guillaume Salha-Galvan, Romain Hennequin, Benjamin Chapus, Viet-Anh Tran, and Michalis Vazirgiannis

Shared Neural Item Representations for Completely Cold Start Problem

Ramin Raziperchikolaei, Guannan Liang, and Young-joo Chung

1.5 推进系统评估体系

主要是离线或在线评估方法，准确性和多样性等统一指标的设计等。

Evaluating Off-Policy Evaluation: Sensitivity and Robustness

Yuta Saito, Takuma Udagawa, Haruka Kiyohara, Kazuki Mogi, Yusuke Narita, and Kei Tateno

Fast Multi-Step Critiquing for VAE-based Recommender Systems

Diego Antognini and Boi Faltings

Online Evaluation Methods for the Causal Effect of Recommendations

Masahiro Sato

Towards Unified Metrics for Accuracy and Diversity for Recommender Systems

Javier Parapar and Filip Radlinski

1.6 会话/序列推荐

涉及session维度的短序列推荐；使用NLP中常用的Transformers做序列推荐的鸿沟探讨和解决，这一块交叉了NLP的算法，是当前的热点。

Next-item Recommendations in Short SessionsWenzhuo Song, Shoujin Wang, Yan Wang, and SHENGSHENG WANG
Transformers4Rec: Bridging the Gap between NLP and Sequential / Session-Based RecommendationGabriel de Souza Pereira Moreira, Sara Rabhi, Jeong Min Lee, Ronay Ak, and Even Oldridge
Denoising User-aware Memory Network for RecommendationZhi Bian, Shaojun Zhou, Hao Fu, Qihong Yang, Zhenqi Sun, Junjie Tang, Guiquan Liu, kaikui liu, and Xiaolong Li
Large-Scale Modeling of Mobile User Click Behaviors Using Deep LearningXin Zhou and Yang Li
1.7 隐私保护

通过联邦学习来实现隐私保护的机制。

Privacy Preserving Collaborative Filtering by Distributed MediationAlon Ben Horin, and Tamir Tassa
Stronger Privacy for Federated Collaborative Filtering With Implicit FeedbackLorenzo Minto, Moritz Haller, Ben Livshits, and Hamed Haddadi
1.8 对抗与攻击

对抗样本在推荐场景的应用。

Black-Box Attacks on Sequential Recommenders via Data-Free Model Extraction

Zhenrui Yue, Zhankui He, Huimin Zeng, and Julian McAuley

1.9 对话推荐系统

对话交互式推荐系统

Large-scale Interactive Conversational Recommendation System

Ali Montazeralghaem, James Allan, and Philip S. Thomas

1.10 可解释性推荐

推荐系统的可解释性探索

EX3: Explainable Attribute-aware Item-set Recommendations

Yikun Xian, Tong Zhao, Jin Li, Jim Chan, Andrey Kan, Jun Ma, Xin Luna Dong, Christos Faloutsos, George Karypis, S. Muthukrishnan, and Yongfeng Zhang

1.11 跨域推荐

Towards Source-Aligned Variational Models for Cross-Domain Recommendation

Aghiles Salah, Thanh Binh Tran, and Hady Lauw

1.12 基于视觉的推荐

通过视觉信息做推荐。也就是内容理解方向，是广大CV人士切入推荐场景的一个很好的方向。

Semi-Supervised Visual Representation Learning for Fashion Compatibility

Ambareesh Revanur, Vijay Kumar, and Deepthi Sharma

Tops, Bottoms, and Shoes: Building Capsule Wardrobes via Cross-Attention Tensor Network

Huiyuan Chen, Yusan Lin, Fei Wang, and Hao Yang

1.13 组推荐/用户物品分层推荐
Local Factor Models for Large-Scale Inductive RecommendationLongqi Yang, Tobias Schnabel, Paul N. Bennett, and Susan Dumais
Learning to Represent Human Motives for Goal-directed Web BrowsingJyun-Yu Jiang, Chia-Jung Lee, Longqi Yang, Bahareh Sarrafzadeh, Brent Hecht, Jaime Teevan
1.14 推荐系统交互设计

研究了美食场景下，多用户意图的推荐系统的交互设计。

“Serving Each User”: Supporting Different Eating Goals Through a Multi-List Recommender Interface

Alain Starke, Edis Asotic, and Christoph Trattner

2. 按照推荐技术分类

涉及传统协同过滤、度量学习的迭代；新兴的图学习技术、联邦学习技术、强化学习技术等的探索。

2.1 协同过滤

传统的协同过滤工作，其中第一篇工作把CF和LDA关联起来。

Matrix Factorization for Collaborative Filtering Is Just Solving an Adjoint Latent Dirichlet Allocation Model After All

Florian Wilhelm

Negative Interactions for Improved Collaborative-Filtering: Don’t go Deeper, go Higher

Harald Steck and Dawen Liang

ProtoCF: Prototypical Collaborative Filtering for Few-shot Item Recommendation

Aravind Sankar, Junting Wang, Adit Krishnan, and Hari Sundaram

2.2 图学习

知识图谱的应用以及图嵌入技术和上下文感知的表征技术的融合。

Sparse Feature Factorization for Recommender Systems with Knowledge Graphs

Antonio Ferrara, Vito Walter Anelli, Tommaso Di Noia, and Alberto Carlo Maria Mancino

Together is Better: Hybrid Recommendations Combining Graph Embeddings and Contextualized Word Representations

Marco Polignano, Cataldo Musto, Marco de Gemmis, Pasquale Lops, and Giovanni Semeraro

2.3 强化学习

强化学习在推荐系统中的应用，结合对话系统，设计奖励函数。

Partially Observable Reinforcement Learning for Dialog-based Interactive RecommendationYaxiong Wu, Craig Macdonald, and Iadh Ounis
Pessimistic Reward Models for Off-Policy Learning in Recommendation

Olivier Jeunen and Bart Goethals

2.4 度量学习

协同过滤和度量学习的结合，又叫CML。

Hierarchical Latent Relation Modeling for Collaborative Metric LearningViet-Anh Tran, Guillaume Salha-Galvan, Romain Hennequin, and Manuel Moussallam
2.5 联邦学习

联邦学习的优化以及在隐私保护中的应用。

A Payload Optimization Method for Federated Recommender SystemsFarwa K. Khan, Adrian Flanagan, Kuan Eeik Tan, Zareen Alamgir, and Muhammad Ammad-ud-din
Stronger Privacy for Federated Collaborative Filtering With Implicit Feedback

Lorenzo Minto, Moritz Haller, Ben Livshits, and Hamed Haddadi

2.6 架构/训练/优化

推荐系统架构方向的优化：涉及训练、优化、检索、实时流等。

cDLRM: Look Ahead Caching for Scalable Training of Recommendation ModelsKeshav Balasubramanian, Abdulla Alshabanah, Joshua D Choe, and Murali Annavaram
Reverse Maximum Inner Product Search: How to efficiently find users who would like to buy my item?Daichi Amagata and Takahiro Hara
Page-level Optimization of e-Commerce Item RecommendationsChieh Lo, Hongliang Yu, Xin Yin, Krutika Shetty, Changchen He, Kathy Hu, Justin M Platz, Adam Ilardi, and Sriganesh Madhvanath
Accordion: A Trainable Simulator for Long-Term Interactive SystemsJames McInerney, Ehtsham Elahi, Justin Basilico, Yves Raimond, and Tony Jebara
Information Interactions in Outcome Prediction: Quantification and Interpretation using Stochastic Block ModelsGaël Poux-Médard, Julien Velcin, and Sabine Loudcher
Learning An Adaptive Meta Model-Generator for Incrementally Updating Recommender SystemsDanni Peng, Sinno Jialin Pan, Jie Zhang, and Anxiang Zeng
Recommendation on Live-Streaming Platforms: Dynamic Availability and Repeat Consumption

Jeremie Rappaz, Julian McAuley, and Karl Aberer

3. 实验性质的文章

Reproducibility papers可复现实验性质的文章，共3篇。分别探索了：序列推荐中的采样评估策略；对话推荐系统中生成式和检索式的方法对比；神经网络推荐系统和矩阵分解推荐系统的对比。

A Case Study on Sampling Strategies for Evaluating Neural Sequential Item Recommendation Modelsby Alexander Dallmann, Daniel Zoller, Andreas Hotho (Data Science Chair, University of Würzburg, Würzburg, Germany)
Generation-based vs. Retrieval-based Conversational Recommendation: A User-Centric Comparisonby Ahtsham Manzoor and Dietmar Jannach (University of Klagenfurt, Klagenfurt, Austria)
Reenvisioning the comparison between Neural Collaborative Filtering and Matrix Factorizationby Vito Walter Anelli (Polytechnic University of Bari, Bari, Italy), Alejandro Bellogin (Information Retrieval Group, Universidad Autonoma de Madrid, Madrid, Spain), Tommaso Di Noia Polytechnic (University of Bari, Bari, Italy), and Claudio Pomo (Polytechnic University of Bari, Bari, Italy)

参考链接：

RecSys 2021

Recsys2021 | 推荐系统论文整理与导读
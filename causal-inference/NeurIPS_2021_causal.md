# NeurIPS 2021 | 因果推断论文集锦，推荐系统视角下。

> **原文链接**: [https://zhuanlan.zhihu.com/p/430479546](https://zhuanlan.zhihu.com/p/430479546)  
> **点赞数**: 176  
> **平台**: 知乎专栏

---

NeurIPS-2021刚刚放榜没多久，笔者为了进一步优化推荐系统，就因果推断方向，总结了今年NIPS相关的一些论文。因果推断以及因果发现等是未来推荐系统进化以及增长的一个强大的数据挖掘武器，如果能够有效利用因果推断能力，能够为推荐系统的生态良性和实质增长贡献可靠能力。以下是本人整理选取的十几篇今年NIPS因果相关专题的论文，涉及的因果细分方向有：因果发现、因果结构学习、贝叶斯学习、因果强化学习、因果推断、因果深度学习、因果多任务学习、因果对抗学习。我个人认为比较有价值的文章，会标注相应的中文题目，欢迎大家浏览评论。

今年NIPS接受论文的List:

[NeurIPS | 2021](https://link.zhihu.com/?target=https%3A//neurips.cc/Conferences/2021/AcceptedPapersInitial)

## 1.因果发现

因果发现是通过对相关数据进行算法发掘，从而提取因果关系。这在推荐系统的数据分析中十分重要，尤其是特征分析、效果分析。是增长模型的利器，未来需要重点关注。

**Iterative Causal Discovery in the Possible Presence of Latent Confounders and Selection Bias**

 _Raanan Yehezkel Rohekar (Intel Labs) · Shami Nisimov (Intel Labs) · Yaniv Gurwicz (Intel Labs) · Gal Novik (Intel Labs)_

潜在混杂因素和选择偏差可能存在的迭代因果发现

**Reliable Causal Discovery with Improved Exact Search and Weaker Assumptions**

 _Ignavier Ng (Carnegie Mellon University) · Yujia Zheng (Carnegie Mellon University) · Jiji Zhang (Lingnan University) · Kun Zhang (CMU)_

改进精确搜索和较弱的假设下的可靠因果发现

**Collaborative Causal Discovery with Atomic Interventions**

 _Raghavendra Addanki (College of Information and Computer Science, University of Massachusetts, Amherst) · Shiva Kasiviswanathan (Amazon)_

元干预条件下的协同因果发现

**BCD Nets: Scalable Variational Approaches for Bayesian Causal Discovery**

 _Chris Cundy (Stanford University) · Aditya Grover (University of California, Los Angeles) · Stefano Ermon (Stanford)_

BCD网:贝叶斯因果发现的可扩展变分方法

  


## 2.因果结构学习 

因果结构学习本质上是通过拓扑结构来描述因果关系，从而更好地从不同尺度来反映因果关系的强度。落地有推荐场景的根因分析，特征有效性根因分析等，因果结构学习是一个重要的方向。

**Interventional Sum-Product Networks: Causal Inference with Tractable Probabilistic Models**

 _Matej Zečević (TU Darmstadt) · Devendra Dhami (CS Department, TU Darmstadt, TU Darmstadt) · Athresh Karanam (University of Texas, Dallas) · Sriraam Natarajan (Indiana University) · Kristian Kersting (TU Darmstadt)_

介入和积网络:可处理的概率模型的因果推理

**Matching a Desired Causal State via Shift Interventions**

 _Vicky Zhang (Massachusetts Institute of Technology) · Chandler Squires (Massachusetts Institute of Technology) · Caroline Uhler (Massachusetts Institute of Technology)_

通过Shift干预匹配期望的因果状态

**Necessary and sufficient graphical conditions for optimal adjustment sets in causal graphical models with hidden variables**

 _Jakob Runge (German Aerospace Center)_

具有隐藏变量的因果图模型中最优平差集的充分必要图条件

**Instance-dependent Label-noise Learning under a Structural Causal Model**

 _Yu Yao (University of Sydney) · Tongliang Liu (The University of Sydney) · Mingming Gong (University of Melbourne) · Bo Han (HKBU / RIKEN) · Gang Niu (RIKEN) · Kun Zhang (CMU)_

结构因果模型下的实例依赖标记噪声学习

**Causal Effect Inference for Structured Treatments**

 _Jean Kaddour (University College London) · Yuchen Zhu (University College London) · Qi Liu (University of Oxford) · Matt Kusner (University College London) · Ricardo Silva ([ http://ucl.ac.uk](https://link.zhihu.com/?target=http%3A//ucl.ac.uk))_

结构恢复的因果关系推理

**Learning Causal Semantic Representation for Out-of-Distribution Prediction**

 _Chang Liu (Microsoft Research Asia) · Xinwei Sun (Peking University) · Jindong Wang (Microsoft Research Asia) · Haoyue Tang (Tsinghua University, Tsinghua University) · Tao Li (Peking University) · Tao Qin (Microsoft Research) · Wei Chen (Microsoft Research) · Tie-Yan Liu (Microsoft Research)_

非分布预测的因果语义表示学习

**Recursive Causal Structure Learning in the Presence of Latent Variables and Selection Bias**

 _Sina Akbari (EPFL (École Polytechnique Fédérale de Lausanne)) · Ehsan Mokhtarian (Swiss Federal Institute of Technology Lausanne) · AmirEmad Ghassami (Johns Hopkins University) · Negar Kiyavash (École Polytechnique Fédérale de Lausanne)_

存在潜在变量和选择偏差的递归因果结构学习

**Learning latent causal graphs via mixture oracles**

 _Bohdan Kivva (University of Chicago) · Goutham Rajendran (University of Chicago) · Pradeep Ravikumar (Carnegie Mellon University) · Bryon Aragam (University of Chicago)_

**A Causal Lens for Controllable Text Generation**

 _Zhiting Hu (Carnegie Mellon University) · Li Erran Li (AWS AI, Amazon)_

**Statistical Undecidability in Linear, Non-Gaussian Causal Models in the Presence of Latent Confounders**

 _Konstantin Genin (University of Tübingen)_

**Identification of Partially Observed Linear Causal Models: Graphical Conditions for the Non-Gaussian and Heterogeneous Cases**

 _Jeffrey Adams (University of Copenhagen) · Niels Hansen (University of Copenhagen) · Kun Zhang (CMU)_

**Answering Complex Causal Queries With the Maximum Causal Set Effect**

 _Zachary Markovich (MIT)_

  


## 3.贝叶斯相关

贝叶斯是因果方向的一种基础工具。借此，我们可以为我们的方法找到理论依据和优化工具。

**Dynamic Causal Bayesian Optimization**

 _Virginia Aglietti (University of Warwick) · Neil Dhir (Alan Turing Institute) · Javier González (Microsoft Research Cambridge) · Theodoros Damoulas (University of Warwick)_

动态因果贝叶斯优化

**BayesIMP: Uncertainty Quantification for Causal Data Fusion**

 _Siu Lun Chau (University of Oxford) · Jean-Francois Ton (University of Oxford) · Javier González (Microsoft Research Cambridge) · Yee Teh (DeepMind) · Dino Sejdinovic (University of Oxford)_

因果数据融合的不确定性量化

## 4.因果强化学习

强化学习和因果关系的结合是一个较热的方向，也是强化学习当中反对大规模数据暴力强化学习的有力理论支撑。我本人同样反对暴力强化学习，既只依赖数据规模、数据多样性就能依靠现有深度学习方法解决强化学习场景的问题。

**Actively Identifying Causal Effects with Latent Variables Given Only Response**

**Causal Bandits with Unknown Graph Structure**

 _Yangyi Lu (University of Michigan) · Amirhossein Meisami (University of Michigan) · Ambuj Tewari (University of Michigan)_

通过具有未知图结构的因果器来积极识别潜在变量的因果效应

**Provably Efficient Causal Reinforcement Learning with Confounded Observational Data**

 _Lingxiao Wang (Northwestern University) · Zhuoran Yang (Princeton) · Zhaoran Wang (Princeton University)_

**Asymptotically Best Causal Effect Identification with Multi-Armed Bandits**

 _Alan Malek (DeepMind) · Silvia Chiappa (DeepMind)_

**Deep Proxy Causal Learning and its Application to Confounded Bandit Policy Evaluation**

 _Liyuan Xu (Gatsby Computational Neuroscience Unit) · Heishiro Kanagawa (Gatsby Unit, University College London) · Arthur Gretton (Gatsby Unit, UCL)_

  


## 5.因果推断

这个方向是因果推断方向，相对基础的方向，比较侧重于数据本身与因果的关系。

**Causal Identification with Matrix Equations**

 _Sanghack Lee (Penn State University) · Elias Bareinboim (Columbia University)_

**Recovering Latent Causal Factor for Generalization to Distributional Shifts**

 _Xinwei Sun (Peking University) · Botong Wu (Peking University) · Xiangyu Zheng (Peking University) · Chang Liu (Microsoft Research Asia) · Wei Chen (Microsoft Research) · Tao Qin (Microsoft Research) · Tie-Yan Liu (Microsoft Research)_

**Actively Identifying Causal Effects with Latent Variables Given Only Response Variable Observable**

 _Tian-Zuo Wang (Nanjing University) · Zhi-Hua Zhou (Nanjing University)_

**Matching a Desired Causal State via Shift Interventions**

 _Vicky Zhang (Massachusetts Institute of Technology) · Chandler Squires (Massachusetts Institute of Technology) · Caroline Uhler (Massachusetts Institute of Technology)_

**A Critical Look at the Consistency of Causal Estimation with Deep Latent Variable Models**

 _Severi Rissanen (Aalto University) · Pekka Marttinen (Aalto University)_

**DECAF: Generating Fair Synthetic Data Using Causally-Aware Generative Networks** _Boris van Breugel (University of Cambridge) · Trent Kyono (UCLA) · Jeroen Berrevoets (University of Cambridge) · Mihaela van der Schaar (University of Cambridge)_

**MIRACLE: Causally-Aware Imputation via Learning Missing Data Mechanisms** _Trent Kyono (UCLA) · Yao Zhang (University of Cambridge) · Alexis Bellot (Columbia University) · Mihaela van der Schaar (University of Cambridge)_

**Sequential Causal Imitation Learning with Unobserved Confounders**

 _Daniel Kumor (Purdue University) · Junzhe Zhang (Columbia University) · Elias Bareinboim (Columbia University)_

**Invariant Causal Imitation Learning for Generalizable Policies**

 _Ioana Bica (University of Oxford) · Daniel Jarrett (University of Cambridge) · Mihaela van der Schaar (University of Cambridge)_

**Learning Generalized Gumbel-max Causal Mechanisms**

 _Guy Lorberbom (Technion) · Daniel Johnson (Google Research, Brain Team) · Chris Maddison (Oxford) · Daniel Tarlow (Microsoft Research Cambridge) · Tamir Hazan (Technion)_

**Object-Aware Regularization for Addressing Causal Confusion in Imitation Learning**

 _Jongjin Park (KAIST) · Younggyo Seo (KAIST) · Chang Liu (Microsoft Research Asia) · Li Zhao (Microsoft Research) · Tao Qin (Microsoft Research) · Jinwoo Shin (KAIST) · Tie-Yan Liu (Microsoft Research)_

  


## 6.因果深度学习

通过深度学习方法来解决因果相关问题，也是近年因果问题的主流做法。

**Comprehensive Knowledge Distillation with Causal Intervention**

 _Xiang Deng (State University of New York at Binghamton) · Zhongfei Zhang (Binghamton University)_

知识蒸馏与因果干预综合

**Causal Abstractions of Neural Networks**

 _Atticus Geiger (Stanford University) · Hanson H Lu (Stanford University) · Thomas F Icard (Stanford University) · Christopher Potts (Stanford University)_

**How Well do Feature Visualizations Support Causal Understanding of CNN Activations?**

_Roland S. Zimmermann (University of Tübingen, International Max Planck Research School for Intelligent Systems) · Judy Borowski (University of Tuebingen) · Robert Geirhos (University of Tübingen) · Matthias Bethge (University of Tübingen) · Thomas Wallis (TU Darmstadt) · Wieland Brendel (AG Bethge, University of Tübingen)_

**Causal Navigation by Continuous-time Neural Networks**

 _Charles J Vorbach (Massachusetts Institute of Technology) · Ramin Hasani (MIT) · Alexander Amini (MIT) · Mathias Lechner (IST Austria) · Daniela Rus (Massachusetts Institute of Technology)_

**Causal Inference for Event Pairs in Multivariate Point Processes**

 _Tian Gao (IBM Research AI) · Dharmashankar Subramanian (IBM Research) · Debarun Bhattacharjya (IBM Research) · Xiao Shou (Rensselaer Polytechnic Institute) · Nicholas Mattei (Tulane University) · Kristin P Bennett (Rensselaer Poly. Inst.)_

**A Topological Perspective on Causal Inference**

 _Duligur Ibeling (Stanford University) · Thomas F Icard (Stanford University)_

**Causal Influence Detection for Improving Efficiency in Reinforcement Learning**

 _Maximilian Seitzer (Max Planck Institute for Intelligent Systems, Max-Planck Institute) · Bernhard Schölkopf (MPI for Biological Cybernetics) · Georg Martius (IST Austria)_

**The Causal-Neural Connection: Expressiveness, Learnability, and Inference**

 _Kevin M Xia (Columbia University) · Kai-Zhan Lee (Columbia University) · Yoshua Bengio (University of Montreal) · Elias Bareinboim (Columbia University)_

  


## 7.因果对抗学习

机器学习的对抗场景无处不在，因果推断场景也不例外。因果学习对对抗数据的敏感度更高，很容易出现因果翻转的现象，这是我们利用因果工具的时候，尤其要注意的。

**Beware of the Simulated DAG! Causal Discovery Benchmarks May Be Easy to Game**

 _Alexander Reisach (University of Amsterdam) · Christof Seiler (Maastricht University) · Sebastian Weichwald (University of Copenhagen)_

当心模拟DAG!因果发现基准可能很容易被利用

  


## 8.因果多任务学习

多任务学习是推荐系统场景中经常要面对的问题，借助因果工具来进行多任务学习是一个不错的尝试。

**Multi-task Learning of Order-Consistent Causal Graphs**

 _Xinshi Chen (Georgia Institution of Technology) · Haoran Sun (Georgia Institute of Technology) · Caleb Ellington (School of Computer Science, Carnegie Mellon University) · Eric Xing (Petuum Inc. / Carnegie Mellon University) · Le Song (Georgia Institute of Technology)_

序一致因果图的多任务学习

 _参考资料：_

[NeurIPS | 2021](https://link.zhihu.com/?target=https%3A//neurips.cc/Conferences/2021/AcceptedPapersInitial)

# AAAI 2022 | 因果推断论文集锦[持续更新]

> **原文链接**: [https://zhuanlan.zhihu.com/p/455091033](https://zhuanlan.zhihu.com/p/455091033)  
> **点赞数**: 190  
> **平台**: 知乎专栏

---

AAAI-2022刚刚放榜，笔者就因果推断方向，总结了今年AAAI相关的一些论文，含中文参考。因果推断以及因果发现等是未来机器学习系统进化的一个强大的数据挖掘武器，如果能够有效利用因果推断能力，能够为机器学习系统的生态良性和实质增长贡献可靠能力，如推荐系统场景、CV场景、AI制药场景，具体到疫情预测、药物结构、增长归因等等场景。以下是本人整理选取的二十五篇今年AAAI因果相关专题的论文，涉及的因果细分方向有：因果发现、因果结构学习、因果强化学习、因果推断、因果深度学习等。相比于NIPS，ICML等顶会，AAAI涉及因果推断落地的场景比较多。我个人认为比较有价值的文章，会标注星号，欢迎大家浏览评论。

  


**一.因果发现**

因果发现是通过对相关数据进行算法发掘，从而提取因果关系。在推荐系统的数据分析中比较重要，尤其是特征分析、效果分析、可解释性分析等。是增长模型的利器，未来需要重点关注。今年AAAI因果发现相关的文章较少，但每篇都值得深入学习。

1\. Unsupervised Causal Binary Concepts Discovery with VAE for Black-box Model Explanation

Thien QTran, Kazuto Fukuchi, Youhei Akimoto, Jun Sakuma

应用于黑箱模型解释的基于VAE的无监督因果二元概念发现算法 

  


2.Causal Discovery in Hawkes Processes by Minimum Description Length

Amirkarsa Jalaldoust, Katerina Schindlerova, Claudia Plant

基于最小描述长度的霍克斯过程的因果发现 

  


  


**二.因果结构学习**

因果结构学习本质上是通过拓扑结构来描述因果关系，从而更好地从不同尺度来反映因果关系的强度。落地有推荐场景的根因分析，特征有效性根因分析等，因果结构学习是一个重要的方向。今年主要为多重数据挖掘场景的应用。

*3.Efficient Causal Structure Learning from Multiple Interventional Datasets with Unknown Targets

Yunxia Wang, Fuyuan Cao, Kui Yu, Jiye Liang

基于目标未知的多介入数据集的有效因果结构学习 

  


*4. A Hybrid Causal Structure Learning Algorithm for Mixed-type Data

Yan Li, Rui Xia, Chunchen Liu, Liang Sun

一种混合类型数据的混合因果结构学习算法 

  


  


**三.因果推断**

这个方向是因果推断方向，相对基础的方向，比较侧重于数据本身与因果的关系。今年有一些涉及目标检测、识别、可视化等视觉场景的文章。

*5.Deconfounding Physical Dynamics with Global Causal Relation and Confounder Transmission for Counterfactual Prediction

Zong zhao Li, Xiangyu Zhu, Zhen Lei, Zhaoxiang Zhang

反事实预测的全局因果关系解耦物理动力学和混杂传播 

  


6.A Causal Inference Look At Unsupervised Video Anomaly Detection

Xiangru Lin, Yuyang Chen, Guanbin Li, Yizhou Yu

无监督视频异常检测的因果推理 

  


7.A Causal Debiasing Framework for Unsupervised Salient Object Detection

Xiangru Lin, Ziyi Wu, Guanqi Chen, Guanbin Li, Yizhou Yu

一种用于无监督显著性目标检测的因果去偏框架 

  


8.Causal Intervention for Subject-deconfounded Facial Action Unit Recognition

Yingjie Chen, Diqi Chen, Tao Wang, Yizhou Wang, Yun Liang

因果干预落地被试解基础面部动作单元识别 

  


9.DeepVisuallnsight: Time-Travelling Visualization for Spatio-Temporal Causality of Deep Classification Training

Xianglin Yang, Yun Lin, Ruofan Liu, Zhenfeng He, Chao Wang, Jin Song Dong, Hong Mei

DeepVisuallnsight:深度分类训练时空因果关系的时间旅行可视化 

  


10.Reasoning About Causal Models With Infinitely Many Variables

Joseph Y Halpern, Spencer J Peters

无限多变量因果模型的推理 

  


11.Information-theoretic Bias Reduction via Causal View of Spurious Correlation

Seonguk Seo/ Joon-Young Lee, Bohyung Han

基于伪相关因果观的信息理论偏差减少 

  


12.On Testing for Discrimination Using Causal Models

Hana Chockier, Joseph Y Halpern

因果模型有偏检验 

  


13.Debiasing NLU models via Causal Intervention and Counterfactual Reasoning 

Bing Tian, yixin cao, Yong Zhang, Chunxiao Xin

通过因果干预和反事实推理去偏NLU模型

  


14.On Causally Disentangled Representations

Abbavaram Gowtham Reddy, Benin Godfrey, Vineeth N Balasubramanian

论因果解纠缠表象

  


15\. Unit Selection with Causal Diagram

Ang Li, Judea Pearl

因果图下的单元选择

  


*16.Bounds on Causal Effects and Application to High Dimensional Data

Ang Li, Judea Pearl

因果效应的边界及其在高维数据中的应用 

  


17.Learning Human Driving Behaviors with Sequential Causal Imitation Learning

Kangrui Ruan, Xuan Di

用序列因果模仿学习人类驾驶行为 

  


18.C2L: Causally Contrastive Learning for Robust Text Classification

SeungtaekChoi, Myeongho Jeong, Hojae Han, Seung-won Hwang

C2L:基于因果对比学习的健壮文本分类 

  


*19.On the Fairness of Causal Algorithmic Recourse

Julius von KUgelgen, Amir H Karimi, Umang Bhatt, Isabel Valera, Adrian Weller, Bernhard Scholkopf

论因果算法追索权的公平性

  


20.VACA: Designing Variational Graph Autoencoders for Causal Queries

Pablo Sanchez-Martin, Miriam Rateike, Isabel Valera

VACA:设计变分图自动编码器用于因果查询

  


**四.因果深度学习**

通过深度学习方法来解决因果相关问题，也是近年因果问题的主流做法。涉及的方法主要有GNN以及Embedding。

21.CausalGNN: Causal-based Graph Neural Networks for Spatio-Temporal Epidemic Forecasting

Lijing Wang, Aniruddha Adiga, Jiangzhuo Chen, Adam Sadilek, Srinivasan Venkatramanan, Madhav Marathe

基于因果图神经网络的时空流行病预测 

  


22.Word Embeddings via Causal Inference: Gender Bias Reducing and Semantic Information Preserving Lei Ding, Dengdeng Yu, Jinhan Xie, Wenxing Guo, Shenggang Hu, Meichen Liu, Linglong Kong, Hongsheng Dai, Yanchun Bao, Bei Jiang

基于因果推理的词嵌入:性别偏见减少与语义信息保存 

  


23.Personalized Public Policy Analysis In Social Sciences Using Causal-Graphical Normalizing Flows

Sourabh V BalgL Jose Pena, Adel Daoud

社会科学中使用因果图形化流的个性化公共政策分析   


  


**五.因果强化学习**

强化学习和因果关系的结合是一个较热的方向，也是强化学习当中反对大规模数据暴力强化学习的有力理论支撑。因果推断相关方法反对暴力强化学习，既只依赖数据规模、数据多样性就能依靠现有深度学习方法解决强化学习场景的问题。

  
24.Achieving Counterfactual Fairness for Causal Bandit

Wen Huang, Lu Zhang, Xintao Wu

实现反事实公平的因果Bandit

  


25.Reinforcement learning of causal variables using mediation analysis

Tue Herlau, Rasmus Larsen

利用中介分析强化学习的因果变量 

_参考资料：_

[AAAI 2022 完整List](https://link.zhihu.com/?target=https%3A//aaai.org/Conferences/AAAI-22/wp-content/uploads/2021/12/AAAI-22_Accepted_Paper_List_Main_Technical_Track.pdf)

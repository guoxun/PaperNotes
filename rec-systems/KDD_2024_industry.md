# KDD 2024  | 工业界搜广推场景工作

> **原文链接**: [https://zhuanlan.zhihu.com/p/720208542](https://zhuanlan.zhihu.com/p/720208542)  
> **点赞数**: 160  
> **平台**: 知乎专栏

---

本文参考蘑菇先生分享的KDD 2024相关内容。主要对2024年KDD上搜广推场景的相关工作整理，主要集中于百度、阿里、腾讯、字节、华为、微软、谷歌等大厂的搜广推场景产出。此外，今年有不少工作是基于LLM技术产出的，有不小的参考价值。

参考：[KDD 2024 工业界搜广推工作整理](https://link.zhihu.com/?target=https%3A//mp.weixin.qq.com/s/jSRiHyg0yRGaRzFDpIl81Q)

## **百度**

**冷启动CTR预估 | Warming Up Cold-Start CTR Prediction by Learning Item-Specific Feature Interactions**

Yaqing Wang (Baidu Research, Baidu Inc.); Hongming Piao (Department of Computer Science, City University of Hong Kong); Daxiang Dong (Baidu AI Cloud, Baidu Inc.); Quanming Yao (Department of Electronic Engineering, Tsinghua University); Jingbo Zhou (Baidu Research, Baidu Inc.)

**图与大模型 | HiGPT: Heterogeneous Graph Language Model**

Jiabin Tang (University of Hong Kong); Yuhao Yang (University of Hong Kong); Wei Wei (University of Hong Kong); Lei Shi (Baidu); Long Xia (Baidu Inc.); Dawei Yin (Baidu); Chao Huang (University of Hong Kong)

## **字节**

**广告出价 | Spending Programmed Bidding: Privacy-friendly Bid Optimization with ROI Constraint in Online Advertising**

Yumin Su (ByteDance Inc.); Min Xiang (ByteDance Inc.); Yifei Chen (ByteDance Inc.); Yanbiao Li (ByteDance Inc.); Tian Qin (ByteDance Inc.); Hongyi Zhang (ByteDance Inc.); Yasong Li (ByteDance Inc.); Xiaobing Liu (ByteDance Inc.)

**兴趣建模 | Trinity: Syncretizing Multi-/Long-Tail/Long-Term Interests All in One**

Jing Yan (ByteDance Inc.); Liu Jiang (ByteDance Inc.); Jianfei Cui (ByteDance Inc.); Zhichen Zhao (ByteDance Inc.); Xingyan Bin (ByteDance Inc.); Feng Zhang (ByteDance Inc.); Zuotao Liu (ByteDance Inc.)

## **阿里**

阿里巴巴工作涵盖面广泛：推荐上，跨域推荐、粗排、GNN等；广告上，生成式出价、合约广告多目标、拍卖广告探索机制等。搜索上，电商相关性架构、LLM需求理解、淘搜文本匹配索引系统等。

**基于生成的出价建模 |** **Generative Auto-bidding via Conditional Diffusion Modeling**

利用条件扩散模型进行自动出价，提高在线广告的效率。

Jiayan Guo (Peking University, Alibaba Group); Yusen Huo (Alibaba Group); Zhilin Zhang (Alibaba Group); Tianyu Wang (Alibaba Group); Chuan Yu (Alibaba Group); Jian Xu (Alibaba Group); Bo Zheng (Alibaba Group); Yan Zhang (Peking University)

**电商语义相关性模型架构 |** **Deep Bag-of-Words Model: An Efficient and Interpretable Relevance Architecture for Chinese E-Commerce**

为中文电商设计高效且可解释的相关性架构模型。

Zhe Lin (Alibaba Group); Jiwei Tan (Alibaba Group); Ou Dan (Alibaba Group); Chen Xi (Alibaba Group); Shaowei Yao (Alibaba Group); Bo Zheng (Alibaba Group)

**LLM需求理解 | Know Your Needs Better: Towards Structured Understanding of Marketer Demands with Analogical Reasoning Augmented LLMs**

通过类比推理增强的大型语言模型来更好地理解市场营销人员的需求。

Junjie Wang (Zhejiang University, Ant Group); Dan Yang (Ant Group); Binbin Hu (Ant Group); Yue Shen (Ant Group); Wen Zhang (Zhejiang University); Jinjie Gu (Ant Group)

**GCN图协同过滤 | Multi-Behavior Collaborative Filtering with Partial Order Graph Convolutional Networks**

利用部分顺序图卷积网络进行多行为协同过滤，改善推荐系统。

Yijie Zhang (Jinan University); Yuanchen Bei (Zhejiang University); Hao Chen (The Hong Kong Polytechnic University); Qijie Shen (Alibaba Group); Zheng Yuan (The Hong Kong Polytechnic University); Huan Gong (National University of Defense Technology); Senzhang Wang (Central South University); Feiran Huang (Jinan University); Xiao Huang (The Hong Kong Polytechnic University)

**基于蒸馏的跨域推荐 | DDCDR: A Disentangle-based Distillation Framework for Cross-Domain Recommendation**

基于解耦和蒸馏的框架用于跨域推荐。

Zhicheng An (Ant Group); Zhexu Gu (Ant Group); Li Yu (Ant Group); Ke Tu (Ant Group); Zhengwei Wu (Ant Group); Binbin Hu (Ant Group); Zhiqiang Zhang (Ant Group); Lihong Gu (Ant Group); Jinjie Gu (Ant Group)

**淘宝搜索文本匹配索引 | Text Matching Indexers in Taobao Search**

研究淘宝搜索中的文本匹配索引。

Sen Li (Alibaba Group); Fuyu Lv (Alibaba Group); Ruqing Zhang (CAS Key Lab of Network Data Science and Technology, ICT, CAS); Ou Dan (Alibaba Group); Zhixuan Zhang (Alibaba Group); Maarten Rijke (University of Amsterdam)

**因果推断 | CURLS: Causal Rule Learning for Subgroups with Significant Treatment Effect**

针对具有显著处理效应的子群体的因果规则学习。

Jiehui Zhou (State Key Lab of CAD&CG, Zhejiang University, DAMO Academy, Alibaba Group); Linxiao Yang (DAMO Academy, Alibaba Group); Xingyu Liu (State Key Lab of CAD&CG, Zhejiang University); Xinyue Gu (DAMO Academy, Alibaba Group); Liang Sun (DAMO Academy, Alibaba Group); Wei Chen (State Key Lab of CAD&CG, Zhejiang University)

**合约广告 | Bi-Objective Contract Allocation for Guaranteed Delivery Advertising**

合约广告的双目标合同分配问题。

an Li (Key Laboratory of System Software (Chinese Academy of Sciences) and State Key Laboratory of Computer Science, Institute of Software, Chinese Academy of Sciences, School of Computer Science and Technology, University of Chinese Academy of Sciences); Yundu Huang (Alibaba Group); Wuyang Mao (Alibaba Group); Furong Ye (Key Laboratory of System Software (Chinese Academy of Sciences) and State Key Laboratory of Computer Science, Institute of Software, Chinese Academy of Sciences); Xiang He (Key Laboratory of System Software (Chinese Academy of Sciences) and State Key Laboratory of Computer Science, Institute of Software, Chinese Academy of Sciences, School of Computer Science and Technology, University of Chinese Academy of Sciences); Zhonglin Zu (Alibaba Group); Shaowei Cai (Key Laboratory of System Software (Chinese Academy of Sciences) and State Key Laboratory of Computer Science, Institute of Software, Chinese Academy of Sciences, School of Computer Science and Technology, University of Chinese Academy of Sciences)

**拍卖广告 | Truthful Bandit Mechanisms for Repeated Two-stage Ad Auctions**

为重复两阶段广告拍卖设计真实性多臂老虎机机制。

Haoming Li (Shanghai Jiaotong University); Yumou Liu (The Chinese University of Hong Kong, Shenzhen); Zhenzhe Zheng (Shanghai Jiao Tong University); Zhilin Zhang (Alibaba Group); Jian Xu (Alibaba Group); Fan Wu (Shanghai Jiao Tong University)

**标签推荐 |** **When Box Meets Graph Neural Network in Tag-aware Recommendation**

在标签感知推荐系统中结合盒子模型和图神经网络。

Fake Lin (University of Science and Technology of China); Ziwei Zhao (University of Science and Technology of China); Xi Zhu (University of Science and Technology of China); Da Zhang (University of Science and Technology of China); Shitian Shen (Alibaba Group); Xueying Li (Alibaba Group); Tong Xu (University of Science and Technology of China); Suojuan Zhang (Army Engineering University of PLA); Enhong Chen (University of Science and Technology of China)

**跨域推荐 | Mitigating Negative Transfer in Cross-Domain Recommendation via Knowledge Transferability Enhancement**

研究跨域推荐系统中知识迁移能力的提升，以减少负面迁移的影响。

Zijian Song (School of CS, Peking University, National Engineering Laboratory for Big Data Analysis and Applications, Peking University); WenHan Zhang (School of CS, Peking University, National Engineering Laboratory for Big Data Analysis and Applications, Peking University); Lifang Deng (Lazada Group); Jiandong Zhang (Lazada Group); Wu Zhihua (Lazada Group); Kaigui Bian (School of CS, Peking University, National Engineering Laboratory for Big Data Analysis and Applications, Peking University); Bin Cui (School of CS, Peking University, National Engineering Laboratory for Big Data Analysis and Applications, Peking University)

**粗排 | Enhancing Pre-Ranking Performance: Tackling Intermediary Challenges in Multi-Stage Cascading Recommendation Systems**

多阶段级联推荐系统中粗排性能的增强，解决中间阶段的挑战。

Jianping Wei (Ant Group); Yujie Zhou (Ant Group); Zhengwei Wu (Ant Group); Ziqi Liu (Ant Group)

## **Tencent**

腾讯的工作也比较丰富，涵盖多模态推荐、排序目标引入推荐系统(2篇)、序列建模、兴趣建模、LTV、uplift等。

**多模态推荐 | Improving Multi-modal Recommender Systems by Denoising and Aligning Multi-modal Content and User Feedback**

Guipeng Xv (School of Informatics, Xiamen University); Xinyu Li (School of Informatics, Xiamen University); Ruobing Xie (Tencent); Chen Lin (School of Informatics, Xiamen University); Chong Liu (Tencent); Feng Xia (Tencent); Zhanhui Kang (Tencent); Leyu Lin (Tencent)

**排序与校准联合建模 | Beyond Binary Preference: Leveraging Bayesian Approaches for Joint Optimization of Ranking and Calibration**

Chang Liu (Shanghai Jiaotong University); Qiwei Wang (Tencent); Wenqing Lin (Tencent); Yue Ding (Shanghai Jiao Tong University); Hongtao Lu (Shanghai Jiao Tong University)

**排序目标损失函数理解 | Understanding the Ranking Loss for Recommendation with Sparse User Feedback**

Zhutian Lin (Shenzhen International Graduate School, Tsinghua University); Junwei Pan (Tencent Inc.); Shangyu Zhang (Tencent Inc.); Ximei Wang (Tencent Inc.); Xi Xiao (Shenzhen International Graduate School, Tsinghua University); Huang Shudong (Tencent Inc.); Lei Xiao (Tencent Inc.); Jie Jiang (Tencent Inc.)

**全生命周期跨场景序列建模** | **Cross-Domain LifeLong Sequential Modeling for Online Click-Through Rate Prediction**

Ruijie Hou (Wechat, Tencent); Zhaoyang Yang (Wechat, Tencent); Yu Ming (Wechat, Tencent); Hongyu Lu (Wechat, Tencent); Zhuobin Zheng (Wechat, Tencent); Yu Chen (Wechat, Tencent); Qinsong Zeng (Wechat, Tencent); Ming Chen (Wechat, Tencent)

**动态兴趣建模** | **Know in** **Linear-Complexity Forecasting of Ad Campaign Performance with Evolving User Interest**

Xiaoyu Wang (University of Science and Technology of China, National Institute of Informatics); Yonghui Guo (Tencent Advertising); Hui Sheng (Tencent Advertising); Peili Lv (Tencent Advertising); Chi Zhou (Tencent Advertising); Wei Huang (Tencent Advertising); Shiqin Ta (Tencent Advertising); Dongbo Huang (Tencent Advertising); Xiujin Yang (Tencent Advertising); Lan Xu (Tencent Advertising); Hao Zhou (LINKE Lab, School of Computer Science and Technology, University of Science and Technology of China, CAS Key Laboratory of Wireless-Optical Communications, University of Science and Technology of China); Yusheng Ji (Information Systems Architecture Science Research Division, National Institute of Informatics)

**LTV建模 |** **ADSNet: Cross-Domain LTV Prediction with an Adaptive Siamese Network in Advertising**

Ruize Wang (Tencent Inc.); Hui Xu (Tencent Inc.); Ying Cheng (School of Computer Science, Fudan University); Qi He (Tencent Inc.); Xing Zhou (Tencent Inc.); Rui Feng (School of Computer Science, Fudan University); Wei Xu (Tencent Inc.); Lei Huang (Tencent Inc.); Jie Jiang (Tencent Inc.)

**游戏皮肤推荐 | Controllable Multi-Behavior Recommendation for In-Game Skins with Large Sequential Model**

Yanjie Gou (Common Data Platform, Tencent); Yuanzhou Yao (Institute of Computing Technology, Chinese Academy of Sciences, University of Chinese Academy of Sciences); Zhao Zhang (Institute of Computing Technology, Chinese Academy of Sciences); Yiqing Wu (Institute of Computing Technology, Chinese Academy of Sciences); Yi Hu (Common Data Platform, Tencent); Fuzhen Zhuang (Institute of Artificial Intelligence, Beihang University, Zhongguancun Laboratory); Jiangming Liu (School of Information Science and Engineering, Yunnan University); Yongjun Xu (Institute of Computing Technology, Chinese Academy of Sciences)

**排序增强的uplift | Rankability-enhanced Revenue Uplift Modeling Framework for Online Marketing**

Bowei He (City University of Hong Kong); Yunpeng Weng (FiT, Tencent); Xing Tang (FiT, Tencent); Ziqiang Cui (City University of Hong Kong); Zexu Sun (Renmin University of China); Liang Chen (FiT, Tencent); Xiuqiang He (FiT, Tencent); Chen Ma (City University of Hong Kong)

**网页搜索 |** **Enhancing Asymmetric Web Search through Question-Answer Generation and Ranking**

Dezhi Ye (Tencent PCG); Jie Liu (Tencent PCG); Jiabin Fan (Tencent PCG); Bowen Tian (Tencent PCG); Tianhua Zhou (Tencent PCG); Xiang Chen (Tencent PCG); Jin Ma (Tencent PCG)

## **Kuaishou**

快手的研究涉及较多融合、重排、校准方面的工作，以及更高阶的用户留存建模等，相比于传统的研究会更吸引注意力。

**融合模型 | Unsupervised Ranking Ensemble Model for Recommendation**

Wenhui Yu (Kuaishou Technology); Bingqi Liu (Kuaishou Technology); Bin Xia (Kuaishou Technology); Xiaoxiao Xu (Kuaishou Technology); Ying Chen (Kuaishou Technology); Yongchang Li (Kuaishou Technology); Lantao Hu (Kuaishou Technology)

**直播礼物推荐 | MMBee: Live Streaming Gift-Sending Recommendations via Multi-Modal Fusion and Behaviour Expansion**

Jiaxin Deng (Institute of Automation, School of Artificial Intelligence, University of Chinese Academy of Sciences); Shiyao Wang (KuaiShou Inc.); Yuchen Wang (KuaiShou Inc.); Jiansong Qi (KuaiShou Inc.); Liqin Zhao (KuaiShou Inc.); Guorui Zhou (KuaiShou Inc.); Gaofeng Meng (Institute of Automation)

**上下文蒸馏-多样性推荐 | Contextual Distillation Model for Diversified Recommendation**

Fan Li (University of Science and Technology of China); Xu Si (Tsinghua University); Shisong Tang (Kuaishou Inc., Tsinghua University); Dingmin Wang (University of Oxford); Kunyan Han (Kuaishou Inc.); Bing Han (Kuaishou Inc.); Guorui Zhou (Kuaishou Inc.); Yang Song (Kuaishou Inc.); Hechang Chen (Jilin University)

**用户留存建模 | Modeling User Retention through Generative Flow Networks**

Ziru Liu (City University of Hong Kong); Shuchang Liu (Kuaishou Technology); Bin Yang (Kuaishou Technology); Zhenghai Xue (Nanyang Technological University); Qingpeng Cai (Kuaishou Technology); Xiangyu Zhao (City University of Hong Kong); Zijian Zhang (City University of Hong Kong); Lantao Hu (Kuaishou Technology); Han Li (Kuaishou Technology); Peng Jiang (Kuaishou Technology)

**非自回归生成的重排模型 | Non-autoregressive Generative Models for Reranking Recommendation**

Yuxin Ren (Kuaishou Technology); Qiya Yang (Peking University); Yichun Wu (Tsinghua University); Wei Xu (Kuaishou Technology); Yalong Wang (Kuaishou Technology); Zhiqiang Zhang (Kuaishou Technology)

**校准排序 | A Self-boosted Framework for Calibrated Ranking**

Shunyu Zhang (Kuaishou Technology); Hu Liu (Kuaishou Technology); Wentian Bao (Columbia University); Yun Yu (Northeasten University); Yang Song (Kuaishou Technology)

## **Meituan**

**搜推联合 | Unified Dual-Intent Translation for Joint Modeling of Search and Recommendation**

Yuting Zhang (Institute of Computing Technology, Chinese Academy of Sciences, University of Chinese Academy of Sciences); Yiqing Wu (Institute of Computing Technology, Chinese Academy of Sciences, University of Chinese Academy of Sciences); Ruidong Han (Meituan); Ying Sun (Thrust of Artificial Intelligence, The Hong Kong University of Science and Technology (Guangzhou)); Yongchun Zhu (Institute of Computing Technology, Chinese Academy of Sciences); Xiang Li (Meituan); Wei Lin (Meituan); Fuzhen Zhuang (Institute of Artificial Intelligence, Beihang University, Zhongguancun Laboratory); Zhulin An (Institute of Computing Technology, Chinese Academy of Sciences); Yongjun Xu (Institute of Computing Technology, Chinese Academy of Sciences)

**拍卖 | Joint Auction in the Online Advertising Market**

Zhen Zhang (Gaoling School of Artificial Intelligence, Renmin University of China); Weian Li (School of Software, Shandong University); Yahui Lei (Meituan Inc.); Bingzhe Wang (Gaoling School of Artificial Intelligence, Renmin University of China); Zhicheng Zhang (Gaoling School of Artificial Intelligence, Renmin University of China); Qi Qi (Gaoling School of Artificial Intelligence, Renmin University of China); Qiang Liu (Meituan Inc.); Xingxing Wang (Meituan Inc.)

**因果推断 | Decision Focused Causal Learning for Direct Counterfactual Marketing Optimization**

Hao Zhou (State Key Laboratory for Novel Software Technology, Nanjing University, Meituan); Rongxiao Huang (State Key Laboratory for Novel Software Technology, Nanjing University); Shaoming Li (Meituan); Guibin Jiang (Meituan); Jiaqi Zheng (State Key Laboratory for Novel Software Technology, Nanjing University); Bing Cheng (Meituan); Wei Lin (Meituan)

## 京东

**电商异构图 | Paths2Pair: Meta-path Based Link Prediction in Billion-Scale Commercial Heterogeneous Graphs**

Jinquan Hang (JD Logistics, Rutgers University, New Brunswick); Zhiqing Hong (Rutgers University, New Brunswick); Xinyue Feng (Rutgers University, New Brunswick); Guang Wang (Florida State University); Guang Yang (Rutgers University, New Brunswick); Feng Li (JD Logistics); Xining Song (JD Logistics); Desheng Zhang (Rutgers University, New Brunswick

**多任务 |** **Multi-task Conditional Attention Network for Conversion Prediction in Logistics Advertising**

Baoshen Guo (Southeast University, JD Logistics); Xining Song (JD Logistics); Shuai Wang (Southeast University); Wei Gong (University of Science and Technology of China); Tian He (JD Logistics); Xue Liu (McGill University)

## **Huawei**

华为整体的工作也比较丰富，包括：序列推荐、生成式推荐、生成式内容、时长纠偏、结构化和语义表征、蒸馏、特征选择等。也值得学习下。

**序列推荐 | Dataset Regeneration for Sequential Recommendation（最佳学生论文）**

Mingjia Yin (University of Science and Technology of China & State Key Laboratory of Cognitive Intelligence); Hao Wang (University of Science and Technology of China & State Key Laboratory of Cognitive Intelligence); Wei Guo (Huawei Singapore Research Center); Yong Liu (Huawei Singapore Research Center); Suojuan Zhang (University of Science and Technology of China & State Key Laboratory of Cognitive Intelligence); Sirui Zhao (University of Science and Technology of China & State Key Laboratory of Cognitive Intelligence); Defu Lian (University of Science and Technology of China & State Key Laboratory of Cognitive Intelligence); Enhong Chen (University of Science and Technology of China & State Key Laboratory of Cognitive Intelligence)

**生成式推荐 | EAGER: Two-Stream Generative Recommender with Behavior-Semantic Collaboration**

Ye Wang (Zhejiang University); Jiahao Xun (Zhejiang University); Minjie Hong (Zhejiang University); Jieming Zhu (Huawei Noah’s Ark Lab); Tao Jin (Zhejiang University); Lin Wang (Zhejiang University); Haoyuan Li (Zhejiang University); Linjun Li (Zhejiang University); Yan Xia (Zhejiang University); Zhou Zhao (Zhejiang University); Zhenhua Dong (Huawei Noah’s Ark Lab)

**LLM内容生成** | **Neural Retrievers are Biased Towards LLM-Generated Content**

Sunhao Dai (Gaoling School of Artificial Intelligence, Renmin University of China); Yuqi Zhou (Gaoling School of Artificial Intelligence, Renmin University of China); Liang Pang (CAS Key Laboratory of AI Safety Institute of Computing Technology Chinese Academy of Sciences); Weihao Liu (Gaoling School of Artificial Intelligence, Renmin University of China); Xiaolin Hu (Gaoling School of Artificial Intelligence, Renmin University of China); Yong Liu (Gaoling School of Artificial Intelligence, Renmin University of China); Xiao Zhang (Gaoling School of Artificial Intelligence, Renmin University of China); Gang Wang (Noah’s Ark Lab, Huawei); Jun Xu (Gaoling School of Artificial Intelligence, Renmin University of China)

**时长纠偏 | Counteracting Duration Bias in Video Recommendation via Counterfactual Watch Time**

Haiyuan Zhao (School of Information, Renmin University of China); Guohao Cai (Noah’s Ark Lab, Huawei); Jieming Zhu (Noah’s Ark Lab, Huawei); Zhenhua Dong (Noah’s Ark Lab, Huawei); Jun Xu (Gaoling School of Artificial Intelligence, Renmin University of China); Ji-Rong Wen (Gaoling School of Artificial Intelligence, Renmin University of China)

**结构化和语义解耦和协同 | DisCo: Towards Harmonious Disentanglement and Collaboration between Tabular and Semantic Space for Recommendation**

Kounianhua Du (Shanghai Jiao Tong University); Jizheng Chen (Shanghai Jiaotong University); Jianghao Lin (Shanghai Jiaotong University); Yunjia Xi (Shanghai Jiaotong University); Hangyu Wang (Shanghai Jiao Tong University); Xinyi Dai (Huawei Noah’s Ark Lab); Bo Chen (Huawei Noah’s Ark Lab); Ruiming Tang (Huawei Noah’s Ark Lab); Weinan Zhang (Shanghai Jiao Tong University)

**面向RL推荐的优势知识状态蒸馏 | Privileged Knowledge State Distillation for Reinforcement Learning-based Educational Path Recommendation**

Qingyao Li (Shanghai Jiao Tong University); Wei Xia (Huawei Noah’s Ark Lab); Li’ang Yin (Shanghai Jiao Tong University); Jiarui Jin (Shanghai Jiao Tong University); Yong Yu (Shanghai Jiao Tong University)

**深度模型特征选择** | **ERASE: Benchmarking Feature Selection Methods for Deep Recommender Systems**

Pengyue Jia (City University of Hong Kong); Yejing Wang (City University of Hong Kong); Zhaocheng Du (Huawei Noah’s Ark Lab); Xiangyu Zhao (City University of Hong Kong); Yichao Wang (Huawei Noah’s Ark Lab); Bo Chen (Huawei Noah’s Ark Lab); Wanyu Wang (City University of Hong Kong); Huifeng Guo (Huawei Noah’s Ark Lab); Ruiming Tang (Huawei Noah’s Ark Lab)

## **Google**

**多任务 | Scalable Multitask Learning Using Gradient-based Estimation of Task Affinity**

Dongyue Li (Northeastern University); Aneesh Sharma (Google); Hongyang R. Zhang (Northeastern University)

**多任务探索 | Multi-Task Neural Linear Bandit for Exploration in Recommender Systems**

Yi Su (Google Deepmind); Haokai Lu (Google Deepmind); Yuening Li (Google); Liang Liu (Google); Shuchao Bi (Google); Ed H. Chi (Google Deepmind); Minmin Chen (Google Deepmind)

**LLM用于拍卖 | Auctions with LLM Summaries**

Avinava Dubey (Google Research); Zhe Feng (Google Research); Rahul Kidambi (Google Research); Aranyak Mehta (Google Research); Di Wang (Google Research)

**基于生成式AI的评估 | Reliable Confidence Intervals for Information Retrieval Evaluation using Generative A.I.**

Harrie Oosterhuis (Google Research, Radboud University); Rolf Jagerman (Google Research); Zhen Qin (Google Research); Xuanhui Wang (Google Research); Michael Bendersky (Google Research)

**用户价值 | User Welfare Optimization in Recommender Systems with Competing Content Creators**

Fan Yao (University of Virginia); Yiming Liao (Meta Platforms, Inc.); Mingzhe Wu (University of Southern California); Chuanhao Li (Yale University); Yan Zhu (Google); James Yang (Meta Platforms, Inc.); Jingzhou Liu (Meta Platforms, Inc.); Qifan Wang (Meta Platforms, Inc.); Haifeng Xu (University of Chicago); Hongning Wang (University of Virginia)

**序列推荐 | Probabilistic Attention for Sequential Recommendation**

Yuli Liu (Qinghai University, Qinghai Provincial Key Laboratory of Media Integration Technology and Communication); Christian Walder (Google Research, Brain Team); Lexing Xie (Australian National University, Data61 CSIRO); Yiqun Liu (Department of Computer Science and Technology, Tsinghua University, Zhongguancun Laboratory)

## **Airbnb**

airbnb一如既往，标题简短、实战经验满满，也值得关注下。

**基于模型蒸馏的多目标学习 | Multi-objective Learning to Rank by Model Distillation**

Jie Tang (Airbnb); Huiji Gao (Airbnb); Liwei He (Airbnb); Sanjeev Katariya (Airbnb)

**地图场景下的LTR | Learning to Rank for Maps at Airbnb**

Malay Haldar (Airbnb, Inc.); Hongwei Zhang (Airbnb, Inc.); Kedar Bellare (Airbnb, Inc.); Sherry Chen (Airbnb, Inc.); Soumyadip Banerjee (Airbnb, Inc.); Xiaotang Wang (Airbnb, Inc.); Mustafa Abdool (Airbnb, Inc.); Huiji Gao (Airbnb, Inc.); Pavan Tapadia (Airbnb, Inc.); Liwei He (Airbnb, Inc.); Sanjeev Katariya (Airbnb, Inc.)

## **Microsoft**

**使用LLM和强化学习的topK推荐 |** **Optimizing Novelty of Top-k Recommendations using Large Language Models and Reinforcement Learning**

Amit Sharma (Microsoft Research); Hua Li (Microsoft Bing Ads); Xue Li (Microsoft Bing Ads); Jian Jiao (Microsoft Bing Ads)

**使用LLM用于可解释推荐 | RecExplainer: Aligning Large Language Models for Explaining Recommendation Models**

Yuxuan Lei (University of Science and Technology of China); Jianxun Lian (Microsoft Research Asia); Jing Yao (Microsoft Research Asia); Xu Huang (University of Science and Technology of China); Defu Lian (University of Science and Technology of China); Xing Xie (Microsoft Research Asia)

**检索 | Extreme Meta-classification for Large-Scale Zero-Shot Retrieval**

Sachin Yadav (Microsoft Research); Deepak Saini (Microsoft); Anirudh Buvanesh (Microsoft Research); Bhawna Paliwal (Microsoft Research); Kunal Dahiya (Indian Institute of Technology Delhi); Siddarth Asokan (Microsoft Research); Yashoteja Prabhu (Microsoft Research); Jian Jiao (Microsoft); Manik Varma (Microsoft Research)

## **Shopee**

**广告校准 | Deep Ensemble Shape Calibration: Multi-Field Post-hoc Calibration in Online Advertising**

Shuai Yang (Shopee Discovery Ads); Hao Yang (Shopee Discovery Ads); Zhuang Zou (Shopee Discovery Ads); Linhe Xu (Shopee Discovery Ads); Shuo Yuan (Shopee Discovery Ads); Yifan Zeng (Shopee Discovery Ads)

**多目标残差学习 | Residual Multi-Task Learner for Applied Ranking**

Cong Fu (Shopee Pte. Ltd.); Kun Wang (Shopee Pte. Ltd.); Jiahua Wu (Shopee Pte. Ltd.); Yizhou Chen (Shopee Pte. Ltd.); Guangda Huzhang (Shopee Pte. Ltd.); Yabo Ni (Nanyang Technological University); Anxiang Zeng (SCSE, National Technological University); Zhiming Zhou (ECONCS, Shanghai University of Finance and Economics)‍

## **Meta**

**离线强化学习出价 | Offline Reinforcement Learning for Optimizing Production Bidding Policies**

Dmytro Korenkevych (AI at Meta); Frank Cheng (AI at Meta); Artsiom Balakir (AI at Meta); Alex Nikulkov (AI at Meta); Lingnan Gao (Meta Platform Inc.); Zhihao Cen (AI at Meta); Zuobing Xu (Meta Platform Inc.); Zheqing Zhu (AI at Meta)

**多阶段个性化推荐 |** **Achieving a Better Tradeoff in Multi-stage Recommender Systems through Personalization**

Ariel Evnine (Meta); Stratis Ioannidis (Northeastern University); Dimitris Kalimeris (Meta); Shankar Kalyanaraman (Meta); Weiwei Li (Meta); Israel Nir (Meta); Wei Sun (Meta); Udi Weinsberg (Meta)

**冷启动 |** **Inductive Modeling for Realtime Cold Start Recommendations**

Chandler Zuo (Meta); Jonathan Castaldo (Meta); Hanqing Zhu (Meta); Haoyu Zhang (Meta); Ji Liu (Meta); Yangpeng Ou (Meta); Xiao Kong (Meta)

**用户福利优化 | User Welfare Optimization in Recommender Systems with Competing Content Creators**

Fan Yao (University of Virginia); Yiming Liao (Meta Platforms, Inc.); Mingzhe Wu (University of Southern California); Chuanhao Li (Yale University); Yan Zhu (Google); James Yang (Meta Platforms, Inc.); Jingzhou Liu (Meta Platforms, Inc.); Qifan Wang (Meta Platforms, Inc.); Haifeng Xu (University of Chicago); Hongning Wang (University of Virginia)

## **Walmart**

**大模型生成个性化广告** | **Chaining Text-to-Image and Large Language Model: A Novel Approach for Generating Personalized e-commerce Banners**

Shanu Vashishtha (Walmart Global Tech); Abhinav Prakash (Walmart Global Tech); Lalitesh Morishetti (Walmart Global Tech); Kaushiki Nag (Walmart Global Tech); Yokila Arora (Walmart Global Tech); Sushant Kumar (Walmart Global Tech); Kannan

## **Amazon**

**多模态视觉搜索 | Bringing Multimodality to Amazon Visual Search System**

Xinliang Zhu (Amazon); Sheng-Wei Huang (Amazon); Han Ding (Amazon); Jinyu Yang (Amazon); Kelvin Chen (Amazon); Tao Zhou (Amazon); Tal Neiman (Amazon); Ouye Xie (Amazon); Son Tran (Amazon); Benjamin Yao (Amazon); Douglas Gray (Amazon); Anuj Bindal (Amazon); Arnab Dhua (Amazon)

**统一图学习 | GraphStorm: All-in-one Graph Machine Learning Framework for Industry Applications**

Da Zheng (Amazon AWS AI); Xiang Song (Amazon AWS AI); Qi Zhu (Amazon AWS AI); Jian Zhang (Amazon AWS AI); Theodore Vasiloudis (Amazon AWS AI); Runjie Ma (Amazon AWS AI); Houyu Zhang (Amazon Search AI); Zichen Wang (Amazon AWS AI); Soji Adeshina (Amazon AWS AI); Israt Nisa (Amazon AWS AI); Alejandro Mottini (Amazon Search AI); Qingjun Cui (Amazon Search AI); Huzefa Rangwala (Amazon AWS AI); Belinda Zeng (Amazon SP); Christos Faloutsos (Amazon AWS AI); George Karypis (Amazon AWS AI)

**购物轨迹表示学习 | Shopping Trajectory Representation Learning with Pre-training for E-commerce Customer Understanding and Recommendation**

Yankai Chen (Department of Computer Science and Engineering, The Chinese University of Hong Kong); Quoc-Tuan Truong (Amazon); Xin Shen (Amazon); Jin Li (Amazon); Irwin King (Department of Computer Science and Engineering, The Chinese University of Hong Kong)

## **LinkedIn**

**GNN | LiGNN: Graph Neural Networks at LinkedIn**

Fedor Borisyuk (LinkedIn); Shihai He (LinkedIn); Yunbo Ouyang (LinkedIn); Morteza Ramezani (LinkedIn); Peng Du (LinkedIn); Xiaochen Hou (LinkedIn); Chengming Jiang (LinkedIn); Nitin Pasumarthy (LinkedIn); Priya Bannur (LinkedIn); Birjodh Tiwana (LinkedIn); Ping Liu (LinkedIn); Siddharth Dangi (LinkedIn); Daqi Sun (LinkedIn); Zhoutao Pei (LinkedIn); Xiao Shi (LinkedIn); Sirou Zhu (LinkedIn); Qianqi Shen (LinkedIn); Kuang-Hsuan Lee (LinkedIn); David Stein (LinkedIn); Baolei Li (LinkedIn); Haichao Wei (LinkedIn); Amol Ghoting (LinkedIn); Souvik Ghosh (LinkedIn)

**元学习 | LiMAML: Personalization of Deep Recommender Models via Meta Learning**

Ruofan Wang (LinkedIn Corporation); Prakruthi Prabhakar (LinkedIn Corporation); Gaurav Srivastava (LinkedIn Corporation); Tianqi Wang (LinkedIn Corporation); Zeinab S. Jalali (LinkedIn Corporation); Varun Bharill (LinkedIn Corporation); Yunbo Ouyang (LinkedIn Corporation); Aastha Nigam (LinkedIn Corporation); Divya Venugopalan (LinkedIn Corporation); Aman Gupta (LinkedIn Corporation); Fedor Borisyuk (LinkedIn Corporation); Sathiya Keerthi (LinkedIn Corporation); Ajith Muralidharan (Aliveo AI Corp)

## **Instacart**

**电商搜索纠偏 | Mitigating Pooling Bias in E-commerce Search via False Negative Estimation**

Xiaochen Wang (Pennsylvania State University); Xiao Xiao (Instacart); Ruhan Zhang (Instacart); Xuan Zhang (Instacart); Taesik Na (Instacart); Tejaswi Tenneti (Instacart); Haixun Wang (Instacart); Fenglong Ma (Pennsylvania State University)

## **Adobe**

**LLM用于长尾推荐 | CoRAL: Collaborative Retrieval-Augmented Large Language Models Improve Long-tail Recommendation**

Junda Wu (University of California San Diego); Cheng-Chun Chang (Columbia University); Tong Yu (Adobe Research); Zhankui He (University of California San Diego); Jianing Wang (University of California San Diego); Yupeng Hou (University of California San Diego); Julian McAuley (University of California San Diego)

## **总结**

KDD2024，整体来说，工业界搜广推相关的工作很丰富，不仅仅涵盖了经典推荐系统研究领域：如序列建模、排序目标、图推荐、多任务、跨域、纠偏、因果推断、蒸馏、CTR预估、等，也包括了前沿的基于LLM或类LLM的生成式推荐、搜索、广告方面的工作，如下面几篇：

  * Alibaba 生成式出价建模 | Generative Auto-bidding via Conditional Diffusion Modeling
  * Alibaba 基于LLM的需求理解 | Know Your Needs Better: Towards Structured Understanding of Marketer Demands with Analogical Reasoning Augmented LLMs
  * Kuaishou 生成式重排 | Non-autoregressive Generative Models for Reranking Recommendation
  * Huawei 生成式推荐 | EAGER: Two-Stream Generative Recommender with Behavior-Semantic Collaboration
  * Huawei 生成式内容检索有偏性研究 | Neural Retrievers are Biased Towards LLM-Generated Content
  * Google 基于生成式AI的搜索质量评估 | Reliable Confidence Intervals for Information Retrieval Evaluation using Generative A.I.
  * Microsoft 基于LLM的推荐新颖性 | Optimizing Novelty of Top-k Recommendations using Large Language Models and Reinforcement Learning
  * Microsoft 使用LLM用于可解释推荐 | RecExplainer: Aligning Large Language Models for Explaining Recommendation Models
  * Walmart 生成式广告 | Chaining Text-to-Image and Large Language Model: A Novel Approach for Generating Personalized e-commerce Banners
  * Adobe 基于LLM的长尾内容推荐 | CoRAL: Collaborative Retrieval-Augmented Large Language Models Improve Long-tail Recommendation



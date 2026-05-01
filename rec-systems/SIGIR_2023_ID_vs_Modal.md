# SIGIR2023 | ID vs 模态: 推荐系统ID范式有望被颠覆？

> **原文链接**: [https://zhuanlan.zhihu.com/p/645910074](https://zhuanlan.zhihu.com/p/645910074)  
> **点赞数**: 13  
> **平台**: 知乎专栏

---

简要概括：本文探索了一个非常有潜在价值的方向，即多模态推荐系统MoRec范式 是否有望终结 IDRec范式 在推荐系统领域长达十多年的主导地位。对于这个问题，这篇论文进行了深入的探究。


链接: https://arxiv.org/abs/2303.13835

代码: https://github.com/westlake-repl/IDvs.MoRec

参考了机器学习与推荐算法公众号作者ML_RSer的内容：SIGIR2023 | ID vs 模态: 推荐系统ID范式有望被颠覆？

研究背景 [纯 ID 推荐 vs 纯模态推荐系统]

自矩阵分解问世以来，使用 ID embedding 来建模物品的协同过滤算法已经成为推荐系统最主流的范式，主导了整个推荐系统社区长达 15 年。经典的双塔架构、CTR 模型、会话和序列推荐、Graph 网络无不采用 ID embedding 来对物品进行建模，整个推荐系统现有的 SOTA 体系也几乎都是采用基于 ID 特征的建模手段。

然而，近年来 NLP、CV 和多模态预训练大模型技术蓬勃发展，取得了一系列革命性成果，预训练大模型（又称为基础模型）对多模态（文本和图像）建模能力越来越强，知名的基础模型包括 BERT，GPT, Vision Transformer，CLIP 等。随着基础模型对物品的模态特征的建模和理解能力的增强，一个自然的问题出现了：使用最先进的模态编码器表征物品是否能取代经典的 itemID embedding 范式？论文称此类模型为 MoRec，MoRec 是否能和经典的纯 ID 范式（IDRec）硬刚，超过或者取代 IDRec？

实际上这一问题在 10 年前就被广泛调查过，然而，当时受制于 NLP 和 CV 技术不足，IDRec 在效率和效果上都可以轻松碾压 MoRec。但是该结论在十年后的今天是否仍然成立？论文认为需要重新思考这一问题。其中一个重要原因是，论文认为基于 ID 的经典范式是与当近大模型技术严重背离的。因为 ID 在不同的推荐业务无法共享，这一特性导致推荐系统模型难以在不同的业务进行有效迁移，更无法实现 NLP 和 CV 领域的 one model for all（one4all）范式。

值得注意的是，虽然近几年有不少文献尝试将 NLP、CV 预训练模型引入推荐系统的领域，但这些文献往往关注于冷启动和新物品场景，而这种场景下 IDRec 的效果自然是不理想的，这也是普遍接受的。但是对于常规场景，也就是非冷启动，甚至是热 item 场景，IDRec 仍是非常强的基线，在这种场景下 MoRec 与 IDRec 哪个更好仍然是未知的。论文特别指出，现有的很多 MoRec 文献虽然声称取得了 SOTA 结果，但是并没有显式地比较 IDRec 与 MoRec。这里作者认为要做到公平比较是指：IDRec 与 MoRec 至少应该采用相同的骨架推荐模型和实验设置（例如，采样和损失函数保持一致）。也就是除了 item 的表示方式，其他部分都应该保持一致或者公平。

论文认为 MoRec 与 IDRec 的公平比较是非常重要的，如果在热场景下 MoRec 也能打败 IDRec，那么推荐系统将有望迎来经典范式的变革。这一观点来自于 MoRec 完全基于物品的模态信息，此类内容信息天生具有迁移能力，这证明了 MoRec 有潜力实现通用大模型。因此，只要 MoRec 在各种场景下都能打败 IDRec，或者只需要做到跟 IDRec 具有相当的推荐效果，那么 IDRec 就有望被推翻。换言之，one4all 推荐模型一旦实现，未来的推荐系统只需要在一个或者几个通用大模型上进行微调，甚至做零样本迁移即可。如果实现这一理想，那么推荐系统领域无疑会发生近 10 年最大的变革，无数的推荐系统工程师重复性的劳动都有望被释放。

除此以外，文章还验证了 2 个重要的问题：（1）对于 MoRec，现有的 NLP 和 CV 领域取得的进展，也就是更强大的（多）模态编码器能否能够直接带来推荐系统效果的直接提升；如果这个问题得到肯定答案，那么 MoRec 范式无疑是更加有潜力的，随着更强的 NLP 和 CV 表征模型的产生，MoRec 也将越强；（2）NLP 和 CV 预训练大模型，如 BERT 和 Vision Transformer，产生的物品表征应该如何使用？工业界最常用的手段是直接将这些表征当做离线特征来加入推荐或 CTR 模型，这种方法是不是最优的；换言之，这种大模型产生的物品表征是否具有一定的通用性，是否必须要在推荐系统数据集上进行重新适应？最后论文提供 MoRec 发展的四个挑战，这些问题大多在现有的文献没有被明确提出。

论文也指出，想要彻底调查清楚这一问题，甚至是颠覆 IDRec，仅靠一篇文章是远远不够的，将需要整个推荐系统社区一同努力。

实验设置

网络架构


该文章为了验证设想，对推荐系统社区两种最具有代表性的推荐架构进行了评估，分别是最经典的双塔 DSSM 模型（代表 CTR 范式）和 SASRec 模型（代表时序或者会话推荐）。SASRec 采用最为流行的 Transformer 架构。

为了保证公平比较，MoRec 和 IDRec 唯一的不同之处是使用预训练的模态编码器来替代 IDRec 中的 ID embedding 向量。考虑到相同推荐网络架构下的 MoRec 需要比 IDRec 多出一个参数量巨大的预训练模态编码器网络，在调参过程中很难极限地对 MoRec 进行超参数搜索。为此，本文只对 IDRec 进行较大范围的网格参数搜索，定位 IDRec 的最优参数后直接应用到 MoRec，然后在对应的较小调参空间做简单搜索。这样的调参方式可以保证 IDRec 达到最优，但 MoRec 可能没有达到性能上限。考虑到搜参的困难，作者认为仅仅 MoRec 的调参就可以作为一个非常重要的研究方向，下文 MoRec 面临的几个挑战也再次印证了超参数对于 MoRec 非常重要。

数据集


论文使用了 3 个数据集，用户规模在 40-60 万，商品规模在 8-12 万，分别是文本信息主导的新闻推荐数据集 MIND，商品图片信息主导的 HM 和视频推荐数据集 Bili。这些数据集均含有商品的原始模态信息。MIND 和 HM 都是公开数据集，作者已将实验所用数据集公布在 Github（链接见上），Bili 数据集来自于未发表的论文，可通过邮件获取，详情可见 Github。


可以看出，Bili 和 HM 数据集中的图片和 CV 领域用于预训练的数据集（ImageNet）存在一定差异，在 ImageNet 上预训练得到的图片编码器在推荐系统是否具有足够的泛化能力仍然是一个未知的问题。对于该问题，论文在后面进行了实验探究。

实验探究

问题 1：MoRec 和 IDRec 性能对比，尤其是在常规场景和热 item 场景。


论文在常规推荐、冷启动推荐、热门物品推荐三个场景下，对 MoRec 和 IDRec 的效果做了周全的对比，结果如下：


首先在常规推荐下，无论是 IDRec 还是 MoRec，DSSM 的性能总是大大低于 SASRec。这与之前的很多研究是一致的：使用用户的交互的 item 序列来代表用户，往往比把它们作为单独的用户 ID 来处理更有效 [1, 2]。同时，MoRec 与 IDRec 的对比在 DSSM 和 SASRec 之间也存在巨大的性能差异，论文发现在 DSSM 架构下，MoRec 在所有三个数据集中的表现都比 IDRec 差很多。这种差距会让人对 MoRec 完全丧失信心，例如在 HM 和 Bili 数据集上，IDRec 比 MoRec 高出一倍以上。

相比之下，在 SASRec 架构下，MoRec 在文本推荐数据集 MIND 上使用三个文本编码器中的任何一个都能取得比 IDRec 更好的结果，在图像数据集 Bili 和 HM 上也基本做到了可比较的效果，例如，当使用 Swin Transformer (Base) 版本，MoRec 甚至能比 IDRec 略好一些，当使用 ResNet 时候，MoRec 仍然略逊于 IDRec。这种比较结果意味着 MoRec 需要一个强大的推荐骨干（SASRec 优于 DSSM）和训练方法（seq2seq 优于 <u,i> pair）才能激发基于模态的项目编码器的优势，而 DSSM 范式似乎很难很好的激发模态编码器的潜力。鉴于 MoRec 在 DSSM 的结果太不理想，论文后续主要关注 SASRec 的架构。


MoRec 很自然地适用于冷物品推荐，因为它们的模态编码器是专门为物品的原始模式特征建模而开发的，无论它们的流行度如何都可以进行物品表征。MoRec 在所有三个数据集上对文本和视觉推荐的冷启动场景都有大幅度超过 IDRec，该现象符合社区的广泛认知，因此论文把相应的结果只放在附录。


在热门商品推荐方面，打败 IDRec 无疑是非常困难的，论文展示了相应的结果。通过选择不同热度的 item 进行验证可以发现在热门程度一般的 warm-20 数据集中，MoRec 还可以比 IDRec 略好，而在热门程度剧烈的 warm-200 中（数据集所有物品均出现 200 次以上），MoRec 在文本和视觉推荐上效果都略差于 IDRec。这是因为 IDRec 在对流行项目进行建模方面非常有优势 [3, 4, 5]。但即使在这些热启动设置中，MoRec 仍然可以与 IDRec 效果相当。

结论 1：对于时序推荐架构 SASRec，在常规场景（既有热 item 也有一部分冷 item），MoRec 在文本上明显优于 IDRec，而在图片上则和 IDRec 效果相当。在冷启动场景，MoRec 大幅优于 IDRec，在热门商品推荐场景，MoRec 和 IDRec 效果相当。这些积极的特性很吸引人，因为这些特性表明，推荐系统很有可能采用 MoRec 替代 IDRec, 另外，考虑到 MoRec 在迁移学习或跨域推荐中具有天然的优势，一旦推荐系统由 IDRec 转向 MoRec，那么大型 MoRec 模型很有可能成为一个像 BERT 和 ChatGPT 一样的基础推荐模型 [6, 7]，从而实现 "一个模型适用于所有推荐场景" 的宏伟目标 [6, 8]。

问题 2：NLP、CV 领域的技术进展能否同步推动 MoRec 的发展？

论文进行了大量实验，分别从更大参数量和更优的编码器两方面调查了 NLP、CV 中预训练模型的进展是否能同步提高 MoRec 推荐的准确性。


如图所示，一个较大的视觉项目编码器一般总是能实现更好的视觉推荐准确率。在文本方面基本结论也基本一致，唯一区别是基于 BERTbase 的 MoRec 并不优于基于 BERT small 的 MoRec，尽管后者参数量小很多。论文的结论是，一般来说来自 NLP 和 CV 的更大和更强大的模态编码器往往会提高推荐的准确性，但这可能并不严格适用于所有的情况。

同时，论文探究了更优的编码器网络。例如，人们认识到 RoBERTa 优于 BERT，而 BERT 在大多数 NLP 理解（但不是生成）任务，在相似的模型规模下，可能优于 GPT。Swin Transformer 在许多 CV 任务中常常优于 ResNet。此外，这些现代预训练文本大模型很容易超过大约十年前开发的著名的轻量级模型 TexTCNN 和 GloVe，如图所示，在更优的模型架构上，MoRec 的性能改变与 NLP 和 CV 的研究结果基本保持一致。


第三，论文研究了有预训练参数的模态编码器是否比在推荐场景下从头训练（即随机初始化）的模态编码器有更高的推荐精度。在较大规模的数据集，和较小规模的图片数据集上，经过预训练的 MoRec 获得了明显更好的最终结果，这也与 NLP 和 CV 领域的发现一致。

结论 2：MoRec 为推荐系统和 NLP、CV 等多模态社区建立了联系，而且一般来说，可以很好的继承 NLP 和 CV 领域的最新进展。这意味着一旦未来在相应的研究领域有新的突破，MoRec 有更多的机会和更大的改进空间。

问题 3：对于推荐场景，NLP、CV 的预训练模型产生的表征有足够的通用能力吗？我们应该怎样使用预训练模型生成的表征？

NLP 和 CV 预训练大模型其中一个目标是实现通用的文本或者视觉表征，可以直接在 zero-shot 设置下用于下游任务。然而，这些预训练编码器只在一些传统 NLP 和 CV 任务中被评估，如图像和文本分类。论文认为，在推荐系统场景下预测主观的用户偏好比 NLP、CV 本身的下游任务更具挑战性。

论文探究了两种训练 MoRec 的方式：1. Two-stage：预先用模态编码器提取离线模态特征，然后将其加入到推荐模型中。由于实际业务中推荐系统通常有数百万乃至千万的商品，Two-stage 在工业界特别受欢迎。2. 采用 End2end 的方式同时优化用户和物品编码器（上述所有实验均汇报的是 End2end 的结果），这种方式会将预训练物品编码器在推荐数据集上进行重新适应。


如表所示，与 IDRec 和基于 End2end 的 MoRec 相比，基于 Two-stage 的 MoRec 显示出糟糕的结果，其效果比前两者差很多，特别是对于视觉推荐能达到 50% 以上的差距。结果表明，由 NLP 和 CV 的预训练任务学习的模态表征对于推荐问题来说仍然不够通用，与在新数据上 End2end 重新训练相比推荐结果差距较大。

结论 3：工业界流行的 Two-stage 离线特征提取推荐方式会导致 MoRec 性能显著下降（特别是对于视觉推荐），这在实践中不应该被忽视。同时，尽管多模态领域的预训练模型在近年来取得了革命性的成功，但其表征还没有做到通用性和泛化性，至少对于推荐系统是这样。

主要挑战

推荐系统社区基于 End2end 的 MoRec 研究比较少，特别是对于视觉推荐。论文提出了几个关键的挑战和一些社区可能不知道的发现。

训练成本


具有较大模态编码器的 MoRec 往往表现更好，然而，训练的计算量、时间和 GPU 内存消耗也会增加，特别是对于具有很长交互序列的基于 seq2seq 的架构。MoRec（用 SASRec 作为用户编码器，Swin-Base 作为商品编码器）比 IDRec 需要 100 倍以上的计算和训练时间。这可能是之前没有论文将 seq2seq 用户编码器和 End2end 训练的模态编码器结合起来用于 MoRec 的原因，特别是用于视觉推荐。

额外的预训练


论文探究了使用下游数据集对模态编码器进行第二轮预训练的效果，这种技术经常被应用于 NLP 和 CV 领域。二次预训练将采用和预训练相同的训练策略，如 MLM。论文发现对于文本数据集来说，二次预训练对 Two-stage 和 End2end 两种 MoRec 都有提升。但在视觉数据集上，则只提升了 HM 数据集中的 Two-stage，对于 HM 的 End2end 和 Bili 的 MoRec 都没有提升。论文给出的结论是二次预训练的有效性取决于个别数据集。

结合 ID 和模态特征


鉴于 IDRec 和基于 E2E 的 MoRec 都运作良好，一个自然的想法是在一个模型中结合这两个特征（即 ID 和模态）。论文采用 2 种融合方法：add 和 concate 对此进行了评估。

令人惊讶的是，论文发现通过添加 ID 特征，基于 End2end 的 MoRec 表现甚至比纯 IDRec 和纯 MoRec 更差。这里的结果与一些已发表的论文有些不一致。原因之一可能是在常规设置中，基于 End2end 的 MoRec 和 IDRec 都是从用户 - 项目交互数据中学习用户偏好，所以它们不能相互补充；而对于基于 Two-stage 的 MoRec，由于 ID 嵌入比冻结的模态特征好太多，它们的组合也不能改善结果。第二个原因可能是在结合 ID 和模态特征时需要更先进的技术。

事实上，从另一个角度看，带有 ID 特征的 MoRec 将失去 MoRec 的许多优势。例如，使用 ID 特征的 MoRec 不适合建立基础推荐模型，因为由于隐私和不同平台间用户、商品难以重叠的问题，ID 不容易迁移。

模型崩溃


论文发现在没有适当的超参数（主要是学习率）的情况下训练 MoRec，很容易导致模型崩溃，有时需要为模态编码器和其他模块设置不同的学习率。可能原因是已经预训练好的编码器的学习步调需要与其他随机初始化开始训练的网络保持不同。

总结

论文调查了一个富有潜力但未被充分探索的问题，即 MoRec 是否有机会结束 IDRec 在推荐系统领域的主导地位。显然，这个问题不可能在一篇论文中得到完全的回答，它需要 Recsys 甚至 NLP 和 CV 社区的更多研究和努力。然而，这里的一个主要发现是，在 End2end 训练的 SOTA 模态编码器的加持下，现代 MoRec 已经可以在典型的推荐架构（即 Transformer 骨干）下表现得与 IDRec 相当或更好，即便是在非冷启动和热 item 推荐的设置中。此外，MoRec 在很大程度上可以从 NLP 和 CV 领域的技术进步中获益，这意味着它在未来有更大的性能提升空间。

论文期待激发社区中更多关于 MoRec 的研究，例如，开发更强大的推荐架构，更有表现力和通用的模态编码器，更好的物品表征和用户表征的融合策略，以及更有效的优化策略以减少计算和时间成本。论文抛出一个设想：从长远来看，当商品的模态信息可用时，推荐系统的主流范式可能有机会从 IDRec 转向 MoRec，从而与 NLP、CV 紧密结合，互相促进发展。

论文还提到了自身的局限性：（1）只考虑了文本和视觉的推荐场景，而 MoRec 在语音和视频下的效果仍然是未知的；(2) 只考虑了单模态场景，多模态场景的效果是未知的；(3) 论文所用的数据集属于中等规模，扩展到 100 倍或 1000 倍的训练数据后（如在真实的工业系统中）论文关键的发现是否成立，仍是未知的。

更多技术细节请阅读原始论文。

引用

[1] Balázs Hidasi, Alexandros Karatzoglou, Linas Baltrunas, and Domonkos Tikk. 2015. Session-based recommendations with recurrent neural networks. arXiv preprint arXiv:1511.06939 (2015).[2] Wang-Cheng Kang and Julian McAuley. 2018. Self-attentive sequential recom- mendation. In 2018 IEEE international conference on data mining (ICDM). IEEE, 197–206.[3] JiaweiChen,HandeDong,YangQiu,XiangnanHe,XinXin,LiangChen,Guli Lin, and Keping Yang. 2021. Autodebias: Learning to debias for recommendation. In Proceedings of the 44th International ACM SIGIR Conference on Research and Development in Information Retrieval. 21–30.[4] XinyangYi,JiYang,LichanHong,DerekZhiyuanCheng,LukaszHeldt,Aditee Kumthekar, Zhe Zhao, Li Wei, and Ed Chi. 2019. Sampling-bias-corrected neural modeling for large corpus item recommendations. In Proceedings of the 13th ACM Conference on Recommender Systems. 269–277.[5] Fajie Yuan, Guibing Guo, Joemon M Jose, Long Chen, Haitao Yu, and Weinan Zhang. 2016. Lambdafm: learning optimal ranking with factorization machines using lambda surrogates. In Proceedings of the 25th ACM international on confer- ence on information and knowledge management. 227–236.[6] Kyuyong Shin, Hanock Kwak, Kyung-Min Kim, Minkyu Kim, Young-Jin Park, Jisu Jeong, and Seungjae Jung. 2021. One4all user representation for recommender systems in e-commerce. arXiv preprint arXiv:2106.00573 (2021).[7] KyuyongShin,HanockKwak,Kyung-MinKim,SuYoungKim,andMaxNihlen Ramstrom. 2021. Scaling law for recommendation models: Towards general- purpose user representations. arXiv preprint arXiv:2111.11294 (2021).[8] JieWang,FajieYuan,MingyueCheng,JoemonMJose,ChenyunYu,BeibeiKong, Zhijin Wang, Bo Hu, and Zang Li. 2022. TransRec: Learning Transferable Recom- mendation from Mixture-of-Modality Feedback. arXiv preprint arXiv:2206.06190 (2022).
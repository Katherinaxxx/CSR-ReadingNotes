# CSR-ReadingNotes
[TOC]

### TextCNN - [Convolutional Neural Networks for Sentence Classification](https://arxiv.org/abs/1408.5882)

### GRU4Rec - [Session-based Recommendations with Recurrent Neural Networks](https://arxiv.org/abs/1511.06939)

* motivation

推荐系统中常用的矩阵分解的方法，用于基于会话的推荐，是不准确的。本文也认为对整个会话建模，推荐会更精准。因此，本文提出了用RNN的会话推荐，并且为了实际可用，对RNN做了一些修改。

*  method

input：state output： items scores
model： GRUs + FC


### SASRec - [Self-Attentive Sequential Recommendation](https://arxiv.org/abs/1808.09781)

* motivation

基于MC的方法在极其稀疏的数据集中执行最佳，其中模型定义是至关重要的，而RNNS在更高的模型复杂性的密集数据集中执行更好。本文提出的SASRec（Self-Attentive Sequential Recommendation）在稀疏和稠密数据上均有良好表现。

* method

![sasrec](/fig/SASRec.png)

---
### R-GCN - [Modeling Relational Data with Graph Convolutional Networks](https://arxiv.org/abs/1703.06103)

### REDIAL - [Towards Deep Conversational Recommendations](https://arxiv.org/abs/1812.07617)

* method
在这个数据上对对话推荐的三个关键点分别进行实验：1）用autoencoder对用户当前语句编码；2）用RNN-based分类器做语义分类、评级；3）带switching mechanism的decoder将上面两个的输出作为输入，生成下句话

![redial](/fig/redial.jpg)

---

### KBRD（alibaba,Tsinghua） - [Towards Knowledge-Based Recommender Dialog System](https://arxiv.org/abs/1908.05391)

* motivation
相比之前端对端的对话推荐系统（redial），增强recommender和ds之间的交互。两者之间可以相互促进。

* method

![kbrd](/fig/kbrd.jpg)

---

### KGSF - [Improving Conversational Recommender Systems via Knowledge Graph based Semantic Fusion](https://arxiv.org/abs/2007.04032)

* motivation

CRS存在两个问题：1）对话数据缺乏充分的语境信息【对话的信息太少】。2）自然语言表达与商品偏好之间存在gap

> In essence, the problem originates from the fact that the dialog component and the recom- mender component correspond to two different semantic spaces, namely word-level and entity-level semantic spaces.

为此，引入基于词【新】的和基于实体的kg，通过互信息将两者对齐，融合、增强对语义的表示。在此基础上采用基于kg的recommender，引入基于kg的dialogue组件用于生成关键词。


* method

1. 基于词的kg：ConceptNet。捕捉词之间的关系，比如同义词、近义词、共现词。
2. 基于实体的kg：DBpedia。捕捉实体属性的结构信心。


---

### TG-ReDial - [Towards Topic-Guided Conversational Recommender System](https://arxiv.org/pdf/2010.04125.pdf) [[code](https://github.com/RUCAIBox/TG-ReDial)]

* motivation

基于话题引导的对话推荐系统。引入话题分支，促使对话自然的转向推荐。

* method

提出一个数据集，TG-ReDial

包含三个部分：
1. item recommender。历史交互和对话文本，SASRec
2. topic prediction。输入历史语句+历史主题+用户信息，预测下一个主题
3. response generation。GPT-2

* thoughts

topic thread还有点意思。以后的论文似乎有参考这篇论文。

### INSPIRED - [INSPIRED: Toward Sociable Recommendation Dialog Systems](https://aclanthology.org/2020.emnlp-main.654.pdf)

* motivation

1）缺乏相关数据（social）。2）发现“分享个人意见”、“鼓励性的交流”有助于推荐

* method

针对上述问题/发现。1）提出一个相关数据集。2）把strategy labels引入，训练一个端到端的对话推荐模型。

两个语言模型，seeker和recommender，strategy labels作为一个特殊token拼接在recommender的输入语句前面。

![inspired](/fig/inspired.jpg)

* thoughts

strategy labels的标注很关键。另外花了大篇幅讲数据是怎么标注的。


### [Building End-To-End Dialogue Systems Using Generative Hierarchical Neural Network Models](https://arxiv.org/abs/1507.04808)

* motivation

把已经提出的hierarchical recurrent neural network（HRED）引入对话生成网络.

* method

对话系统
![hred_ds](/fig/hred_ds.jpg)

* thoughts

比较早的论文，对相关方法的介绍还是比较详细的，对比的baseline是一些ngrams的方法。


### MGCG - [Towards Conversational Recommendation over Multi-Type Dialogs](https://arxiv.org/abs/2005.03954) [[code](https://github.com/PaddlePaddle/models/tree/develop/PaddleNLP/Research/ACL2020-DuRecDial)]

* motivation

多类型对话机器人（QA/chitchat/recommendation），主动自然的引导对话从非推荐转变为推荐。

提出了一个数据集，DuRecDial。与baseline在这个数据集上比较。

* method

multi-goal driven conversation generation framework (MGCG)，用于多类型对话。
![mgcg](/fig/mgcg.png)

* thoughts

这是个真正的系统，组件可太多了。有空的话可以研究一下代码。

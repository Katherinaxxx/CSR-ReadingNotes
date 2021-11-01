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

![](../fig/SASRec.png)

### [Modeling Relational Data with Graph Convolutional Networks](https://arxiv.org/abs/1703.06103)

### REDIAL - [Towards Deep Conversational Recommendations](https://arxiv.org/abs/1812.07617)

* method
在这个数据上对对话推荐的三个关键点分别进行实验：1）用autoencoder对用户当前语句编码；2）用RNN-based分类器做语义分类、评级；3）带switching mechanism的decoder将上面两个的输出作为输入，生成下句话

![](../fig/redial.jpg)

### KBRD（alibaba,Tsinghua） - [Towards Knowledge-Based Recommender Dialog System](https://arxiv.org/abs/1908.05391)

* motivation
端对端的对话推荐系统，增强recommender和ds之间的交互。

* method

![](../fig/kbrd.jpg)





### Improving Conversational Recommender Systems via Knowledge Graph based Semantic Fusion
[https://arxiv.org/abs/2007.04032]

### [Towards Topic-Guided Conversational Recommender System](https://arxiv.org/abs/2010.04125)

### [INSPIRED: Toward Sociable Recommendation Dialog Systems](https://aclanthology.org/2020.emnlp-main.654.pdf)

### [Building End-To-End Dialogue Systems Using Generative Hierarchical Neural Network Models](https://arxiv.org/abs/1507.04808)

### [Towards Conversational Recommendation over Multi-Type Dialogs](https://arxiv.org/abs/2005.03954)

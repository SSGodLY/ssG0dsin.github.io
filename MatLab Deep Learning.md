# Phil Kim  -- MatLab Deep Learing

---

这本书基于matlab代码简单介绍了一点DL的概念，不论是神经网络还是CNN讲的都非常浅显，主要就是把CNN涉及
到的内容，要点都提及了。算法的部分将概念和流程介绍了一下，并没有深入讲下去。

---
## Chapter 1  Machine Learning
  1. Deep Learning 属于 Machine Learning 的一部分，Machine Learning 属于Ai 的一部分。
  2. Machine Learning 就是从训练数据中抽取一个模型。
  3. 为了保证ML有比较好的泛化能力，需要有大量的无偏数据。
  4. 过拟合就是对训练数据拟合的很好，对于测试数据或者实际数据效果不好。
     
    - 正则化 regularization
    + 验证 validation
  5. ML 可以分为有监督、无监督、强化学习
  
| Training Method | Training Data|
|:----:| :----:|
|Supervised Learing|{ input, correct out}|
|Unsupervised Learing|{input}|
|Reinforced Learning|{input,some output,grade for this output}|

---
## Chapter 2 Neural Network
1. >The neural network is a network of nodes, which imitate the
neurons of the brain. The nodes calculate the weighted sum of the
input signals and output the result of the activation function with
the weighted sum.
2. >Most neural networks are constructed with the layered nodes. For
the layered neural network, the signal enters through the input layer,
passes through the hidden layer, and exits through the output layer.
3. >In practice, the linear functions cannot be used as the activation
functions in the hidden layer. This is because the linear function
negates the effects of the hidden layer. However, in some
problems such as regression, the output layer nodes may employ
linear functions.

简单介绍了神经网络的构成，输入层->隐含层->输出层。
简单介绍了修正权值的方法：SGD, BATCH, MINI BATCH.

---
## Chapter 3 Training of Multi-Layer Neural Network
1. >The multi-layer neural network cannot be trained using the delta rule; it should be trained using the back-propagation algorithm,
which is also employed as the learning rule of Deep Learning.
2. >The back-propagation algorithm defines the hidden layer error
as it propagates the output error backward from the output layer.
Once the hidden layer error is obtained, the weights of every layer
are adjusted using the delta rule. The importance of the backpropagation algorithm is that it provides a systematic method to define the error of the hidden node.
3. >The single-layer neural network is applicable only to linearly
separable problems, and most practical problems are linearly
inseparable.
4. >The multi-layer neural network is capable of modeling the
linearly inseparable problems.
5. >Many types of weight adjustments are available in the backpropagation algorithm. The development of various weight
adjustment approaches is due to the pursuit of a more stable
and faster learning of the network. These characteristics are
particularly beneficial for hard-to-learn Deep Learning.
6. >The cost function addresses the output error of the neural
network and is proportional to the error. Cross entropy has
been widely used in recent applications. In most cases, the
cross entropy-driven learning rules are known to yield better
performance.
7. >The learning rule of the neural network varies depending on
the cost function and activation function. Specifically, the delta
calculation of the output node is changed.
8. >The regularization, which is one of the approaches used to
overcome overfitting, is also implemented as an addition of the
weight term to the cost function.

分析BP算法训练神经网络的过程；
介绍了代价函数，交叉熵，以及正则化的应用；

---
## Chapter 4  Neural Network and Classification

1. >For the neural network classifier, the selection of the number of
output nodes and activation function usually depends on whether
it is for a binary classification (two classes) or for a multiclass
classification (three or more classes).
2. >For binary classification, the neural network is constructed with a
single output node and sigmoid activation function. The correct
output of the training data is converted to the maximum and
minimum values of the activation function. The cost function of
the learning rule employs the cross entropy function.
3. >For a multiclass classification, the neural network includes
as many output nodes as the number of classes. The softmax
function is employed for the activation function of the output
node. The correct output of the training data is converted into a
vector using the one-hot encoding method. The cost function of
the learning rule employs the cross entropy function.

神经网络现在主要就是处理分类问题，包括二分类和多分类。

--- 
## Chapter 5 Deep Learning
1. >Deep Learning can be simply defined as a Machine
Learning technique that employs the deep neural network.
2. >The previous neural networks had a problem where the
deeper (more) hidden layers were harder to train and
degraded the performance. Deep Learning solved this
problem.
3. >The outstanding achievements of Deep Learning were not
made by a critical technique but rather are due to many
minor improvements.
4. >The poor performance of the deep neural network is due
to the failure of proper training. There are three major
showstoppers: the vanishing gradient, overfitting, and
computational load.
5. >The vanishing gradient problem is greatly improved by
employing the ReLU activation function and the cross
entropy-driven learning rule. Use of the advanced gradient
descent method is also beneficial.
6. >The deep neural network is more vulnerable to overfitting.
Deep Learning solves this problem using the dropout or
regularization.
7. >The significant training time is required due to the heavy
calculations. This is relieved to a large extent by the GPU
and various algorithms.

对于隐含层比较多的情况，用BP算法训练的时候，靠前的隐含层权值可能训练不到，导致效果不好，
这里介绍了ReLU和Dropout来解决这个问题。

---
## Chapter 6 Convolutional Neural Network
1. >In order to improve the image recognition performance
of Machine Learning, the feature map, which accentuates
the unique features, should be provided rather than the
original image. Traditionally, the feature extractor had
been manually designed. ConvNet contains a special type
of neural network for the feature extractor, of which the
weights are determined via the training process.
2. >ConvNet consists of a feature extractor and classification
neural network. Its deep layer architecture had been a
barrier that made the training process difficult. However,
since Deep Learning was introduced as the solution to this
problem, the use of ConvNet has been growing rapidly.
3. >The feature extractor of ConvNet consists of alternating
stacks of the convolution layer and the pooling layer. As
ConvNet deals with two-dimensional images, most of its
operations are conducted in a two-dimensional conceptual
plane.
4. >Using the convolution filters, the convolution layer
generates images that accentuate the features of the input
image. The number of output images from this layer is the
same as the number of convolution filters that the network
contains. The convolution filter is actually nothing but a
two-dimensional matrix.
5. >The pooling layer reduces the image size. It binds
neighboring pixels and replaces them with a representative
value. The representative value is either the maximum or
mean value of the pixels.

介绍了CNN中卷积层和池化层的概念和算法。

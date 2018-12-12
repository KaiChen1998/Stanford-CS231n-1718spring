# Summary of Assignment 2 (still updating)
## Part 1 Official Homework Instructions
|layout|mathjax|permalink|
| - | - | - |
|page|true|/assignments2018/assignment2/|

In this assignment you will practice writing backpropagation code, and training
Neural Networks and Convolutional Neural Networks. The goals of this assignment
are as follows:


- understand **Neural Networks** and how they are arranged in layered
  architectures
- understand and be able to implement (vectorized) **backpropagation**
- implement various **update rules** used to optimize Neural Networks
- implement **Batch Normalization** and **Layer Normalization** for training deep networks
- implement **Dropout** to regularize networks
- understand the architecture of **Convolutional Neural Networks** and
  get practice with training these models on data
- gain experience with a major deep learning framework, such as **TensorFlow** or **PyTorch**.

You can follow the setup instructions [here](http://cs231n.github.io/setup-instructions/).

### Q1: Fully-connected Neural Network (20 points)
The IPython notebook `FullyConnectedNets.ipynb` will introduce you to our
modular layer design, and then use those layers to implement fully-connected
networks of arbitrary depth. To optimize these models you will implement several
popular update rules.

### Q2: Batch Normalization (30 points)
In the IPython notebook `BatchNormalization.ipynb` you will implement batch
normalization, and use it to train deep fully-connected networks.

### Q3: Dropout (10 points)
The IPython notebook `Dropout.ipynb` will help you implement Dropout and explore
its effects on model generalization.

### Q4: Convolutional Networks (30 points)
In the IPython Notebook ConvolutionalNetworks.ipynb you will implement several new layers that are commonly used in convolutional networks.

### Q5: PyTorch / TensorFlow on CIFAR-10 (10 points)
For this last part, you will be working in either TensorFlow or PyTorch, two popular and powerful deep learning frameworks. **You only need to complete ONE of these two notebooks.** You do NOT need to do both, and we will _not_ be awarding extra credit to those who do. 

Open up either `PyTorch.ipynb` or `TensorFlow.ipynb`. There, you will learn how the framework works, culminating in training a  convolutional network of your own design on CIFAR-10 to get the best performance you can.

## My Summary
### Full Connected Neural Network
- 模块化[affine-ReLU] layer
- FC NN 结构：{affine - [batch/layer norm] - relu - [dropout]} x (L - 1) - affine – softmax <br> **最后的测试集准确率达到了55%**
- NN model参数：hidden layer 组成元组、输入尺寸、类别数、Dropout概率、normalization方式（batchnorm、layernorm）、reg、初始化权重weight_scale，随机种子seed
- Dropout相关参数：mode（train还是test）、p和随机种子seed——全局相同
- BN相关参数：mode —— 每层一个
- Solver优化器参数：模型、数据集（包括训练集和验证集）、updata rules（sgd、sgd_momentum、RMS、Adam）、optim_config（learning rate默认，其他的由不同的优化方式自行添加）、learning rate衰减率、输出相关参数

### Dropout
- 使用inverted dropout，每次dropout之后将权重值除以p，将计算量放在训练过程
- 确实能够延迟过拟合，提高局部验证集准确率，而且会提高收敛速率（实验效果不明显）

### Batch Normalization
- BN前向后向以及与weight初始化以及batch size的关系
- BN会使得模型收敛更快，减少对于weight初始化的依赖
- Layer normalization的实现

### CNN
- 简单三层CNN达到了47%的准确率
- CNN模型参数：输入尺寸、卷积核数量和尺寸、分类数、reg、weight初始化
- 卷积层确实可以提取某些特征从而形成模板（实验中提取了灰度模板和边缘模板）
- CNN（conv-pooling）层前向后向实现
- Spatial Batch Normalization的实现：转化为普通BN，对深度维度上每一个channel取均值和方差
- Spatial Group Normalization的实现

### Tensorlflow
- Three parts: Barebore tensorflow & tf.layers & tf.layers.sequential
- Train cifar-10 using myself model and get an accuracy of 73.2% (imitating VGG) training for 3 hours
- Still trying Resnet to get a better performance

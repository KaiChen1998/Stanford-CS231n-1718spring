# Summary of Assianment 1
**特别注意：所有图像数据在读取的时候都进行了均值归零**
## Knn
- 距离矩阵的向量化和无向量化的实现
- K折交叉验证（是真的严格意义上的k折了）

## Svm、Softmax
- 计算loss和梯度（普通for循环和向量化方式），并使用数值梯度计算法检查结果
- 进行分类器训练，其中svm分类器和softmax分类器都是LinearClassifier 的子类
- SGD的实现，并使用简单的超参数调优（这里主要是learning_rate和reg正则化参数）
- 权重矩阵即学习模板可视化

## Two layer nn——[affine-ReLU]-affine-softmax
- Loss函数：y非none时实现前向传播，y为none时实现的是分类
- 前向与后向、NN训练过程的实现
- 模型类TwoLayerNet，模型训练参数有：训练集验证集、学习速率和衰减率、正则化参数、迭代次数以及batch_size
- 超参数调优，最终可以达到50%左右的测试集正确率

## Feature
- 将图像RGB数据转化为HSV图像特征，使用两层NN训练，测试集正确率提升达到了55%

Details about this assignment can be found [on the course webpage](http://cs231n.github.io/), under Assignment #1 of Spring 2017.

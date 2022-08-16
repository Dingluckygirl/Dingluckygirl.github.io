# Deep Learning 

1. TOC
{:toc}

# step1 ：

定义一个函数Neural Network: 每个里面都有自己的logistic Regression 有自己的weight and bias，就是神经元的参数，这里用theata表示

连接这些神经元，自己想怎么连自己定  参数也是自己定  fully connect feedforward network

连接起来后，就是一个function set

![](/images/1660544420247.png "偏微分")
input layer，deep layer，output layer  深度学习的层数

![](/images/1660544859137.png "偏微分")
Matrix operation 就是那个黄色的矩阵  蓝色的圈就是sigmoid function ，也可以是其他的function
![](/images/1660545012773.png "偏微分")
把所有上面的小的sigmoid函数嵌套起来，就可以用Gpu来计算了

output layer 就是 多分类器  最后通过一个softmax （分权重）  得到结果

NLP 文字处理（用神经网络或许不是很好）


# step2 ：

goodness of function

计算y和y head 的cross entropy   越小越好（所有的求和）
 
相当于theata min 找一个  求total loss L  min

也用gradient descent   求偏导，所有的参数学习率相乘，然后一层一层计算

random 一个初始w，计算每一个w偏微分，新的参数，再偏微分。。。


# step3 ：

pick the best function



## Backpropagation 从输出结果开始反向更新神经网络参数的一个过程

Chain Rule x~y~z   dz/dx = dz/dy*dy/dx

（1）forward pass
![](/images/1660547174442.png "偏微分")

（1）backward pass
![](/images/1660547428270.png "偏微分")

倒着算偏微分，可以算

# tips of deep learning
 训练不好 good results on training data 

1 new activation function

2 adaptive learning rate

训练好了，测试不好  good results on test data 
 
3 early stopping

4 regularization

5 dropout

## 1 ReLU （rectified linear unit） ：
解决前面的层对后面的层影响衰减的问题  训练集很混乱的情况下拟合出结果

1 快

2 生物上的理由

3 无穷多的sigmoid叠加的结果

4 可以解决vanishing gradient problem 前面的层对后面的层影响衰减

等于0 的拿掉
![](/images/1660653899765.png "偏微分")
ReLU 神经元不可微啊，当大于0的时候设为1，小于0 设为0

ReLU 也可以变形，小于0的时候input a=0.01z

## 1 Maxout ：

可以自动学出activation function  
![](/images/1660654322466.png "偏微分")

maxout 也可以设计b, w 设计出ReLU

1.good on training data

## 2 learning rate Adagrad：
给它不同的 learning rate 。
但是Adagrad远远不够  解决学习率的问题

## 2 RMSProp 一个新的方法

learning 除以一个值，

比较相信新的gradient

![](/images/1660655269466.png "偏微分")

## 2 Momentum
惯性的原理，移动带有一定的惯性
![](/images/1660655769301.png "偏微分")
可能借用惯性，就跳出了local minima

## 2 RMSProp +  Momentum
结合

## 3 early stopping
停在测试集最小的时候才对

训练集和测试集的最小loss可能不在同一个位置

切一个Validation set  多切出来一个集进行训练

## 4 Regularization
![](/images/1660656926966.png "偏微分")
w 最后不会变成0 

这个方法的帮助往往不是很大

L2 L1 可以改成绝对值

## 5 Dropout
在训练的时候，每一次都对一个神经元挑选，然后丢掉一些神经元，再去训练这些细长的网络。

每一次更新w,b参数前， d都需要从新dropout一次 ， 所以每次训练的都不一样

在测试集的时候不做dropout
注意：training 的时候丢弃了p%，那么测试集的时候就用1-p%



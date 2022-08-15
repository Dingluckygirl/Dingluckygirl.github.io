## Deep Learning 
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
1. TOC
{:toc}

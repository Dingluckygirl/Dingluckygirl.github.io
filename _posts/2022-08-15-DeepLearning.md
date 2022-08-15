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

step2 ：goodness of function

step3 ：pick the best function




1. TOC
{:toc}

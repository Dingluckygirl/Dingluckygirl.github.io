# Explained ML
local explanation

global explanation

机器判断的能力，机器是否可以解释，对一些决策给出法律的规定

Explanation 也不能完全知道模型做了什么

决策树是可以被解释的机器学习 但是很复杂的决策树是不能被解释的（很多树就是森林）

## Local Explanation
一个object    由 很多部分组成  x1, x2,xn，我们要知道哪个部分重要哪个不重要。

1，把某些部分拿掉，做分类，如果分类很好的话，说明是不重要的部分。某些部分：灰色方块的大小很重要

2，假设图片中有参数x1，x2，xn  ，输出是一个向量yk，假设辨识出是一个狗，对每一个参数加一个小小的扰动，对输出y有很大的变化则是重要的部分。 做偏微分。

上面都是gradient saturation 

## golbal Explanation
activation maximization（review)

低维度向量输入  输出一个图片（gan vae)


## 用一个可解释的model 解释一个不可解释的model
x1,x2,xn === neural network

x1,x2,xn === 可解释的model   得到两个越接近的model ，然后分析上面的那个盒子

假设下面的是linear model，可解释 

LIME  local interpretable model agnostic explanation

## linear model、decision tree  都是可解释的模型

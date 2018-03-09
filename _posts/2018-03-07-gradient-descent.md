---
layout: post
title: Gradient descent algorithm 梯度下降法
categories: [ML]
description: Gradient descent algorithm 梯度下降法
keywords: Gradient descent,梯度下降法,泰勒公式,代码
---

## 简介
快毕业了，补牢一下基础知识。如有错误，烦请指正，谢谢！——马旭   <br />
梯度下降法，不管对于一个凸函数还是非凸函数，都能找到其最优解（设置好合适的步长）。
对于凸函数而言，找到的必是其全局最优解。对于非凸函数而言，找到的只能是局部最优解。

梯度下降法求极小值，梯度上升法求极大值，本质都是一样。

对于目标函数f(x)梯度下降法，随即初始化一个点，找到对应点的梯度，即导数，然后按照反方向规定步长搜索，迭代循环直到收敛于一个局部最小值。相反如果按照梯度的正方向搜索，即局部最大值，梯度上升法。

梯度下降法表达形式为

$$
x=x-step\cdot {f(x))}'
$$

其中$$ step $$为步长，大于0。注意每次迭代步长可以改变。

## 数学原理

###  负梯度原理
梯度下降法又称最速下降法，即在负梯度方向下降速度最快。下面推导下原理。
对于一个传统无约束最小化问题：

$$\min f(x), x\in R^n$$  

函数在点$$x$$处沿方向$$d$$的变化率可以用方向导数表示，为梯度与方向的内积，$$ \triangledown\cdot {f(x)}'\cdot d$$ ,因此，求最快下降方向，就是求这么一个带约束的非线性规划

$$
 \min \triangledown\cdot {f(x)}'\cdot d 
$$


$$
s.t. \left \| d \right \|\leq 1
$$  

根据柯西不等式有




梯度下降法本质就是泰勒公式的一阶展开。
泰勒公式如下：

$$
f(x)=\sum_{n=0}^{\infty } \frac{f^n(a)}{n!}(x-a)^n
$$

那么其对应的泰勒一阶展开就是

$$
f(x)=f(x_0)+{f}'(x-x_0)
$$


## 一维优化例子

## 二维优化例子

## 缺陷

## REFERENCES

梯度下降法的数学推导
http://blog.csdn.net/zengdong_1991/article/details/45563107

梯度下降法
http://blog.csdn.net/u013010889/article/details/61658311

梯度下降法，MALTAB代码，每行都有注释
http://blog.sina.com.cn/s/blog_824188eb0102weos.html

维基百科：梯度下降法
https://zh.wikipedia.org/wiki/%E6%A2%AF%E5%BA%A6%E4%B8%8B%E9%99%8D%E6%B3%95




最近写特征选择，用libsvm 分类。svmtrain方法时会输出一大堆。

用 参数'-q' 来解决。 如下：

```
svmtrain(A,d,'-v 10 -q'); 
```
但是还是有 
```
Cross Validation Accuracy = 87.9444
```
这样的东西出现。

解决办法：

这时候需要修改libsvm里面的代码。

1. 注释输出代码


    我的是libsvm-3.21。在里面 svm-train.c 文件（可能有所不同，自己找找）下的 Cross Validation Accuracy输出注释掉。

2. 重新编译make


    make时除妖进入libsvm的安装目录，/Applications/MATLAB_R2014b.app/toolbox/libsvm-3.21/matlab 这个文件目录下，然后在Matlab命令窗口执行make。



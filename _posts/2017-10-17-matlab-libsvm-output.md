---
layout: post
title: matlab libsvm svmtrain 完全禁止输出
categories: [Matlab]
description: matlab libsvm svmtrain 完全禁止输出
keywords: matlab, libsvm
---

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



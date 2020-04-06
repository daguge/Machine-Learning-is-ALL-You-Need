# Support-Vector-Machine (SVM)

> 分类算法

### 原理
寻找一个超平面作为样本的决策边界，可以将平面两边为两类。

**具体做法：** 
**找到离分隔超平面最近的点，确保它们离分隔面的距离尽可能远。**

**公式推导：**[支持向量机通俗导论（理解SVM的三层境界）](https://blog.csdn.net/v_july_v/article/details/7624837)

SVM的目标是求解出超平面的参数向量w和常量b，而求解过程通过转换成拉格朗日函数，最终可以转化成下述目标函数：

$$
\max_\alpha \sum^n_{i=1}\alpha_i-\dfrac{1}{2}\sum_{i,j=1}^n \alpha_i\alpha_jy_iy_j<x_i,x_j>\\
s.t., 0\le\alpha_i\le C, i=1,\dots,n\\
\sum_{i=1}^n\alpha_iy_i=0
$$


### 步骤
利用求解对偶问题的序列最小最优化SMO算法计算出拉格朗日因子，再计算出w和b。SMO总结下来就是重复下面的过程：
1. 选择两个拉格朗日乘子αi和αj；
2. 固定其他拉格朗日乘子αk(k不等于i和j)，只对αi和αj优化w(α);
3. 根据优化后的αi和αj，更新截距b的值；



### 特性
虽然SVM是用于二分类问题的，但是加上一些操作也可以用于多分类问题。
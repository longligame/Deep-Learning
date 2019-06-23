# 神经网络和深度学习



## Week4 深层神经网络


理解深度学习中的关键计算，使用它们搭建并训练深层神经网络，并应用在计算机视觉中。



### 4.1  深层神经网络

### 4.2  深层网络中的前向传播

### 4.3  核对矩阵的维数

### 4.4  为什么使用深层表示

以面部识别为例子
- 第一隐层作用，一般将边缘作为特征，有各种各样的边缘
- 第二隐层作用，将边缘特征进行组合，组成了一些相对复杂的特征，比如眼耳朵鼻子
- 第三隐层作用，进一步组合上面的特征，生成新的特征面孔。

<img width="500" alt="why" src="https://user-images.githubusercontent.com/41643043/59929260-0c4c7d00-9473-11e9-9f17-30b0b0b275a4.png">

人脑类比
- 人脑其实也是将一个个小的事物链接组合在一起，从而得到更加复杂强大的事物，这在 `learn how to learn` 中是有体现的。





### 4.5  搭建深层神经网络块

**前向传播和反向传播示例**

<img width="500" alt="block" src="https://user-images.githubusercontent.com/41643043/59959704-1f049780-94ef-11e9-8dfc-3f71538de5fa.png">


<img width="500" alt="forward_back" src="https://user-images.githubusercontent.com/41643043/59960005-c683c900-94f3-11e9-8b67-a48b3702779b.png">



**前向传播示例**
- 缓存`Z`

**反向传播示例**
- 缓存`dZ,db`

### 4.6  前向和反向传播

### 4.7 参数 `VS` 超参数

#### **`Hyperparameters`定义**

- **`the parameters control parameters(W&b)`**
- 决定最终的 $W\&b$ 的值


#### **深度学习的超参数**
- 学习率
- 迭代次数
- 隐层数
- 隐层神经元个数
- 激活函数
- 冲量
- `mini batch size`
- 各种正则化参数

<img width="449" alt="hyperpara" src="https://user-images.githubusercontent.com/41643043/57420073-4271cc80-7238-11e9-95db-a7e218ca9c11.png">

#### **应用深度学习**
- 选择更多的超参数进行实验性的测试，选择最优值的超参数
- **深度学习机器学习是一个实验型的测试**


### 4.8  这和大脑有什么关系？
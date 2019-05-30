# S02 改善深层神经网络：超参数调试、正则化以及优化



## Week1 深度学习的实用层面



### 1.1  训练/开发/测试集

#### 数据集划分
`dev set/development set/holdout set`就是验证集

以前小数据集划分
- 为了验证2-6个算法模型的优劣，所以保持60/20/20的比例


大数据时代数据集划分
- 基本开发集和测试集的基本很小

#### 训练集和测试集不是同一分布

不是同一个状况下的分布，比如训练集从精美素材网站找的，测试集是用户手机拍的。

<img width="446" alt="dataset_split" src="https://user-images.githubusercontent.com/41643043/58600276-89dafe00-82b6-11e9-8b08-ad69b09b5d20.png">

**没有测试集也是可以**
- 如果你不需要进行无偏评估`unbiased estimate`
- 验证集现在都被叫`test set`



### 1.2  偏差/方差

`bias-variance tradeoff`

`high variance`
- 泛化能力不好，过拟合

`high bias`
- 模型不好，欠拟合


`high bias & high variance`
- 高纬数据会看到，其实也可以先按照欠拟合来处理








### 1.3  机器学习基础


basic recipe for machine learning


High bias (training data problem)
- bigger network
- train longer
- NN architect

High variance
- More data
- 正则化
- NN architect 

### 1.4  正则化

逻辑回归
<img width="454" alt="lr_reg" src="https://user-images.githubusercontent.com/41643043/58601346-f22bde80-82ba-11e9-88f6-a599f1eec720.png">

神经网络
<img width="451" alt="nn_reg" src="https://user-images.githubusercontent.com/41643043/58601348-f35d0b80-82ba-11e9-94f2-2894f90d5de8.png">






### 1.5  为什么正则化可以减少过拟合？

### 1.6  Dropout 正则化

### 1.7  理解 Dropout

### 1.8  其他正则化方法

### 1.9  正则化输入

### 1.10  梯度消失与梯度爆炸

### 1.11  神经网络的权重初始化

### 1.12  梯度的数值逼近

### 1.13  梯度检验

### 1.14  关于梯度检验实现的注记








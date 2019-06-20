# 神经网络和深度学习


## Week3 浅层神经网络

学习使用前向传播和反向传播搭建出有一个隐藏层的神经网络。

### 3.1  神经网络概览

<img width="500" alt="nn" src="https://user-images.githubusercontent.com/41643043/59572348-3d2d5a80-90df-11e9-8445-55bcc9413fd6.png">




### 3.2  神经网络表示

<img width="500" alt="nn_re" src="https://user-images.githubusercontent.com/41643043/59572350-3ef71e00-90df-11e9-9670-24d875d69134.png">

以前的误区认为是三层神经网络
- 现在学术统一是`2 Laye Neural Network`





### 3.3  计算神经网络的输出



### 3.4  多样本向量化

### 3.5  向量化实现的解释

### 3.6  激活函数

`tanh`和`sigmoid`的关系
- `tanh`由`sigmoid`向下平移`0.5`
- 重新进行幅度缩放到区间`[-1,1]`


`tanh`和`sigmoid`的使用
- `tanh`由于对称性，所以经常用在`hidden layer`
    - 正常输出都是`[-1,1]`
- `sigmoid` 已经很少用了，除非下面二元输出情况
    - 如果输出是二元输出`[0,1]`，可以采用`sigmoid`作为激活函数

`ReLU` 修正线性单元`rectified linear unit`
- 方程 `a = max(0,z)`
- `z=0` 导数是没有定义的，不可微，但很少存在`z`全空间为`0`
- 不确定选择什么作为激活函数，就选择`ReLU`
- 加强版的`leaky ReLU`
    - 方程 `a = max(0.01*z,z)`



为什么`ReLU`和`leaky ReLU`更快？？
- `tanh`和`sigmoid`的激活函数的导数趋近于`0`会降低学习速度
- 对于很多空间的`z`，`ReLU`激活函数的导数和`0`相差很远，比如右侧基本就是`z`
- 学习速度更快

<img width="500" alt="activation" src="https://user-images.githubusercontent.com/41643043/59647251-0cb3f200-91ad-11e9-86ed-5270795d3a83.png">

**激活函数的形状和方程**

<img width="500" alt="shape" src="https://user-images.githubusercontent.com/41643043/59647252-0d4c8880-91ad-11e9-900a-5c98c3079a87.png">

如果不确定选择什么激活函数？
- 尝试所有的激活函数，然后选择出最好的，没有什么太多定论

### 3.7  为什么需要非线性激活函数？


**无激活函数**
- 又名线性激活函数，恒等激活函数
- 会将神经网络转换成线性回归的特性

<img width="500" alt="activate" src="https://user-images.githubusercontent.com/41643043/59764684-da9ab100-92ce-11e9-8608-8d4e6be7be0f.png">

- 激活函数有改变输出特性？！！！



### 3.8  激活函数的导数

**`sigmoid`的导数**
- 两侧大值为0
<img width="500" alt="sigmoid" src="https://user-images.githubusercontent.com/41643043/59764706-e7b7a000-92ce-11e9-8883-5fe53c45c5ed.png">




**`tanh`的导数**
- 由`sigmoid`得到的，所以两侧值为0
<img width="500" alt="tanh" src="https://user-images.githubusercontent.com/41643043/59764708-e8503680-92ce-11e9-8fe0-d7456a8ecd30.png">


**`ReLU`的导数**
- 左边水平线，右侧是45度线

<img width="500" alt="relu" src="https://user-images.githubusercontent.com/41643043/59764703-e71f0980-92ce-11e9-8c3a-72c031a85679.png">


### 3.9  神经网络的梯度下降法




### 3.10  （选修）直观理解反向传播





### 3.11  随机初始化

**随机初始化为`0`**
- 逻辑回归可以随机为`0`
- 神经网络不行
    - 会导致神经元对称性

**随机初始化**
- 选择比较小的初始值 `*0.01`
    - 大的值容易导致激活函数的斜率小，梯度下降就会变慢
- 当训练深层的神经网络，挑选的就不是`0.01`


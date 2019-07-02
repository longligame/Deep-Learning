# 改善深层神经网络：超参数调试、正则化以及优化


## Week2 优化算法


### 2.1  `Mini-batch` 梯度下降法

**为什么使用向量化**
- 加快速度计算`m`个样本

**`mini-batch`定义**
- 切分`m`个样本形成小的`batch`
- 符号 $X^{\{1\}}$

`epoch`定义
- 将训练集所有样本的`mini-batch`来一遍

### 2.2  理解 `mini-batch` 梯度下降法

**`batch VS mini-batch`**
- `batch` 的迭代曲线相对较为平滑
- `mini-batch` 的迭代曲线噪声较多（坐标横轴不一样）

<img width="448" alt="mini-batch" src="https://user-images.githubusercontent.com/41643043/60391279-41189e00-9b1d-11e9-9b11-bd3ad6788f5d.png">



**`mini-batch size`**
- `size = m` 批次梯度下降
    - 下降比较平缓和快
    - 每一个迭代训练时间比较长
- `size = 1` 随机梯度下降
    - 下降噪声会比较大
    - **失去利用向量加速**
- 所以选择了一个中间值作为`mini-batch size`
    - 综合上面的优缺点


**选择`mini-batch size`**
- 样本数m < 2000，选择`batch gradient descent`
- 传统选择`mini-batch size`都是2的幂次方
- 确保选择的`mini-batch`批次样本可以适合`CPU/GPU/memory`
    - 别选太大了
- `mini-batch size`也是超参数

### 2.3  指数加权平均

数据的局部噪声点比较多
- 计算局部平均或者滑动平均



<img width="447" alt="exponetially_weighted_averages" src="https://user-images.githubusercontent.com/41643043/60474731-5a992180-9ca6-11e9-9d36-a4f341925a6c.png">



### 2.4  理解指数加权平均

<img width="500" alt="ewa" src="https://user-images.githubusercontent.com/41643043/60474849-0478ae00-9ca7-11e9-9003-1dd5f9511384.png">

$V_{100}$ 后面的算式系数之和接近`1`
- `1.= 0.1+0.1*0.9+0.1*0.9*0.9+...`
- 利用指数衰减
- 并且系数$\beta=0.9$，并且$0.9^{10}.=1/e$，10天左右才降低到$1/e$
- 并且系数$\beta=0.98$，并且$0.98^{50}.=1/e$，50天左右才降低到$1/e$








### 2.5  指数加权平均的偏差修正


<img width="449" alt="fix_bias" src="https://user-images.githubusercontent.com/41643043/60475573-98984480-9caa-11e9-8b6b-9afb2cc355ad.png">

初始阶段缺少`v0`数据
- 会导致初期的数值比理想的数值低一些
- 所以想了个修正方法
    - $V_t = V_t/1 - \beta^t$



### 2.6  动量梯度下降法

<img width="451" alt="gd_moment" src="https://user-images.githubusercontent.com/41643043/60507119-01f37400-9cfa-11e9-8b1a-2bb1213e1323.png">

**动量梯度下降优点**
- 梯度下降在下降过程中，会进行震荡
- 动量梯度，会减少震动方向变化量，加速前进方向


<img width="445" alt="moment_implementation" src="https://user-images.githubusercontent.com/41643043/60507120-01f37400-9cfa-11e9-9884-41938eb3bc21.png">

**动量梯度下降实施**
- 计算当前`mini-batch`的梯度
- 计算冲量，更新权重



### 2.7  `RMSprop`


<img width="500" alt="RMSprop" src="https://user-images.githubusercontent.com/41643043/60508241-a971a600-9cfc-11e9-96b2-76dc2dd5fecc.png">

**`RMSprop`定义**
- 在指数加权平均的基础上，将第二项换成平方

**难点：搞清等高线的面梯度**
- 比如图上，b的方向梯度要比w方向大
    - 仔细观察等高线，密集就代表梯度大

### 2.8  Adam 优化算法






### 2.9  学习率衰减

### 2.10  局部最优的问题




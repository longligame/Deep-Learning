# 改善深层神经网络：超参数调试、正则化以及优化


## Week2 优化算法



2.1  Mini-batch 梯度下降法

### 2.2  理解 mini-batch 梯度下降法

**`mini-batch size`**
- `size = m` 批次梯度下降
    - 下降比较平缓和快
    - 每一个迭代训练时间比较长
- `size = 1` 随机梯度下降
    - 下降噪声会比较大
    - 失去利用向量加速
- 所以选择了一个中间值作为`mini-batch size`


**选择`mini-batch size`**
- 样本数m < 2000，选择`batch gradient descent`
- 传统选择`mini-batch size`都是2的幂次方
- 确保选择的`mini-batch`批次样本可以适合`CPU/GPU/memory`
    - 别选太大了
- `mini-batch size`也是超参数

### 2.3  指数加权平均

### 2.4  理解指数加权平均

### 2.5  指数加权平均的偏差修正

### 2.6  动量梯度下降法

### 2.7  RMSprop

### 2.8  Adam 优化算法

### 2.9  学习率衰减

### 2.10  局部最优的问题




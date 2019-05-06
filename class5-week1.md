# 序列模型

## Week1 循环序列模型


本周的知识点是循环神经网络。这种类型的模型已经被证明在时间数据上表现非常好，它有几个变体，包括 LSTM、GRU 和双向神经网络，本周的课程中也都包括这些内容。


### 1.1  为什么选择序列模型

需要序列模型的问题很多
- 只要输入或者输出是序列的，都是序列模型需要解决的
- 比如输入x和输出y的长度也可能不一样

<img width="1280" alt="why_seq" src="https://user-images.githubusercontent.com/41643043/57225383-cb251880-703e-11e9-8b8a-ef0e2f0e27c2.png">



### 1.2  数学符号


$x^{<1>}$代表某个样本中的第一个单词

<img width="1280" alt="notion" src="https://user-images.githubusercontent.com/41643043/57225414-dc6e2500-703e-11e9-9334-306eac8a9d33.png">


`one-hot`编码 $x^{<1>}$

<img width="1280" alt="notion2" src="https://user-images.githubusercontent.com/41643043/57225415-dc6e2500-703e-11e9-94db-41b6c076ce97.png">






### 1.3  循环神经网络模型

#### 正常的神经网络为什么不`work`

- 不同样本的输入和输出长度不一样
- 最重要的原因，**不同位置的文本特征没法办共享**

为什么不能共享？


<img width="1277" alt="nn_short" src="https://user-images.githubusercontent.com/41643043/57226670-18ef5000-7042-11e9-808d-34aaa31897bd.png">



#### 循环神经网络

两种结构画法

样本词的输出
- 只能由前面的词决定，没办法由后面的词决定
- 同样的 `teddy`，前样本是名字，后样本就不是，但是后面词也能决定是不是名字


<img width="1280" alt="rnn_struct" src="https://user-images.githubusercontent.com/41643043/57226679-1ee53100-7042-11e9-9a59-13d921b154e0.png">

#### 前向传播

和常规的神经网络类似

$$a^{<0>} = 0$$
$$a^{<1>}= g(W_{aa}a^{<0>}+W_{ax}x^{<1>}+b_a);\ tanh/Relu$$
$$y^{<1>}=g(W_{ya}a^{<1>}+b_y);\ sigmoid$$


<img width="1280" alt="forward" src="https://user-images.githubusercontent.com/41643043/57226691-260c3f00-7042-11e9-9253-885d6249d540.png">


#### 简化`RNN`符号

<img width="1280" alt="simple" src="https://user-images.githubusercontent.com/41643043/57226699-2c022000-7042-11e9-8528-51acae15f07d.png">







#### 1.4  通过时间的反向传播

看起来比较直观，目前没有公式！！

<img width="1277" alt="bptt" src="https://user-images.githubusercontent.com/41643043/57228919-7b971a80-7047-11e9-8dd2-7bd0bb3e6520.png">







1.5  不同类型的循环神经网络

1.6  语言模型和序列生成

1.7  对新序列采样

1.8  带有神经网络的梯度消失

1.9  GRU 单元

1.10  长短期记忆（LSTM）

1.11  双向神经网络

1.12  深层循环神经网络






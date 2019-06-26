# S05 序列模型

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




#### 1.5  不同类型的循环神经网络

`many to one`模型 (情感预测)

<img width="1277" alt="many_to_one" src="https://user-images.githubusercontent.com/41643043/57264817-bb411f00-70a6-11e9-9b11-b612f087c70a.png">

`one to many`模型

<img width="1280" alt="one_to_many" src="https://user-images.githubusercontent.com/41643043/57264902-576b2600-70a7-11e9-8aad-19df26a4b422.png">



`summary`

<img width="1280" alt="summay" src="https://user-images.githubusercontent.com/41643043/57264931-808bb680-70a7-11e9-8764-f4f68580ec9f.png">




#### 1.6  语言模型和序列生成

#### 1.7  对新序列采样

#### 1.8  带有神经网络的梯度消失

 梯度弥散


命名实体识别（NER）：
- 其目的是识别语料中人名、地名、组织机构名等命名实体，识别文本中具有特定意义的实体。
- 它是自然语言处理实用化的重要内容，在信息提取、句法分析、机器翻译等应用领域中具有重要的基础性作用。


梯度爆炸


-  梯度剪枝，超过某个值，收缩



解决方法，


#### 1.9  GRU 单元

门控循环单元 `Gated Recurrent Unit`

引入
- 解决梯度弥散问题，保持长时记忆
- 猫吃饱了例子

C : memory cell

$C^{<t>}= a^{<t>}$

$\Gamma_u = $

`RNN` 单元
<img width="451" alt="gru" src="https://user-images.githubusercontent.com/41643043/57342043-73d29580-716f-11e9-8632-85b00c37211d.png">

**简化的`GRU`**

<img width="447" alt="gru" src="https://user-images.githubusercontent.com/41643043/57817963-89ba0900-77b4-11e9-8c08-935aed5a21dc.png">


**完整的`GRU`**
- 基础上多了一个相关门，需要进一步拓展 `GRU`

<img width="448" alt="full_gru" src="https://user-images.githubusercontent.com/41643043/57817965-8aeb3600-77b4-11e9-9bbb-d777672c1c8e.png">





#### 1.10  长短期记忆（LSTM）

<img width="1280" alt="lstm" src="https://user-images.githubusercontent.com/41643043/57818434-7445de80-77b6-11e9-89a1-95925cbc1c3a.png">


<img width="1280" alt="lstm_pic" src="https://user-images.githubusercontent.com/41643043/57818436-75770b80-77b6-11e9-953a-b2541dafe543.png">



补充学习

[LSTM长短期记忆,GRU单元,双向RNN](https://www.bilibili.com/video/av48131435?from=search&seid=18039820066890376991)


`clipping`
- 梯度爆炸

LSTM
- 解决梯地弥散
- 解决梯度消失所导致的句子长期依赖关系







#### 1.11  双向神经网络

`BRNN: Bidirectional RNN`

动机
- 前向信息并不能完整获取信息，需要后面的信息

<img width="447" alt="brnn" src="https://user-images.githubusercontent.com/41643043/57818806-36e25080-77b8-11e9-8d5b-bbafc26fc8bd.png">





#### 1.12  深层循环神经网络


<img width="1280" alt="deep_rnn_ex" src="https://user-images.githubusercontent.com/41643043/57819844-c984ee80-77bc-11e9-9eaf-0d6cbc638c00.png">


语言模型的特殊`token`
`EOS:end of sentensce`
`UNK:unknown words`






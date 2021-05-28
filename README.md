<h1>新闻文本分类</h1>
<h2>赛题目标</h2>
赛题以新闻数据为赛题数据，整合划分出如下候选分类类别：财经、房产、教育、科技、军事、汽车、体育、游戏、娱乐和其他共10类的新闻文本数据。

<h2>模型选择</h2>

RNN对具有序列特性的数据非常有效，它能挖掘数据中的时序信息以及语义信息.为了解决长程依赖问题，需要引入门控机制来控制信息的累积速度，更好地捕捉时间序列中时间步距离较大的依赖关系。它通过可以学习的门来控制信息的流动，避免模型收敛时出现梯度爆炸或衰减。因此，在模型中采用<strong>门控循环单元</strong>（gated recurrent unit，GRU）网络，gru是一种常用的门控循环神经网络。


<h2>模型结构图</h2>

![image](https://user-images.githubusercontent.com/84953043/119954928-13bb2000-bfd2-11eb-88aa-90bc39c23a62.png)

<h2>训练过程</h2>
<img src="https://user-images.githubusercontent.com/84953043/119974490-4cb1bf80-bfe7-11eb-9968-b4b1f7b8a600.png">![image](https://user-images.githubusercontent.com/84953043/119974490-4cb1bf80-bfe7-11eb-9968-b4b1f7b8a600.png)
![image](https://user-images.githubusercontent.com/84953043/119974514-56d3be00-bfe7-11eb-98cc-0de48982b875.png)

<h2>测试结果</h2>
![image](https://user-images.githubusercontent.com/84953043/119955154-5977e880-bfd2-11eb-81eb-265e8de39d74.png)

<h2>验证结果</h2>
![image](https://user-images.githubusercontent.com/84953043/119955216-6c8ab880-bfd2-11eb-8b2d-a9e5d78a7f7e.png)

<h2>总结</h2>
该模型通过将文本序列按不同时刻输入至堆叠循环神经网络中，得到不同时刻的隐含状态，并将最后一个时刻的隐含状态作为分类器的输入对文本类别进行分类。其中为了解决输入序列过长导致梯度爆炸和消失的问题，因此采用了门控循环单元网络在循环神经网络的基础上引入门控机制来控制信息更新的方式，确保了模型能够正确的收敛。利用堆叠循环神经网络对文本进行分类通过加深循环神经网络的深度从而增加循环神经网络的能力，实践表明对于文本分类的效果显著!





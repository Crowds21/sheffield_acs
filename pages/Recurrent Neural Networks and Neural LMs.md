alias:: 递归神经网络和神经语言模型

- Problem setup
  collapsed:: true
	- Training data is a (large) set of word sequences:
	- $$
	  \begin{aligned}
	  D_{\text {train }} & =\left\{\mathbf{x}^1, \ldots, \mathbf{x}^M\right\} \\
	  \mathbf{x} & =\left[x_1, \ldots x_N\right]
	  \end{aligned}
	  $$
	- We want to learn a model that returns:
	- $$
	  P(\mathbf{x}), \text { for } \forall \mathbf{x} \in V^{\max N}
	  $$
	- $V$ is the vocabulary and $V^{\max N}$ all possible sentences
- Recurrent Neural Networks (RNNs)
  collapsed:: true
	- RNN introduction [[card]]
	  collapsed:: true
		- ((647b7844-7de1-433d-9c4d-5904784abda2))
		- $$
		  s_n=\sigma\left(\mathbf{W} s_{n-1}+\mathbf{U} x_n\right)
		  $$
		- $x_n$
		- $s_{n-1} \in \mathcal{R}^d$
			- ”memory” of the context until word $x_{n-1}$
		- $\sigma()$
			- 激活函数，例如常用的 Sigmoid 函数、Tanh 函数或 ReLU 函数等
		- $\mathbf{W} \in \mathcal{R}^{d \times d}$
			- controls how this memory is passed on (权重)
		- $\mathbf{U} \in \mathcal{R}^{|\mathcal{V}| \times d}$
			- matrix containing the word vectors for all the words, $x_n$ picks one
			- 包含所有单词的词向量矩阵, 给$x_n$ 中挑选一个,然后相乘
		- 为了得到 $x_n$ 的概率分布:
			- $$
			  \mathbf{o}_{n-1}=p\left(x_n \mid x_{n-1} \ldots x_1\right)=\operatorname{softmax}\left(\mathbf{V} s_{n-1}\right)
			  $$
		- $\mathbf{V} \in \mathcal{R}^{d \times|\mathcal{V}|}$
			- output weight matrix
	- ((647b7b86-a3bc-4aff-af09-bc40ee3f2327))
	  collapsed:: true
		- We need to learn
			- word vectors $U$
			- hidden layer parameters $W$
			- output layer parameters $V$
		- Standard backpropagation can’t work in RNN [[card]]
			- Because of the recurrence:we reuse the hidden layer parameters $W$
		- Backpropagation Through Time
			- unroll the graph for $n$ steps and sum the gradients in updating
		- Not as restrictive as the nth-order Markov: we still use **all previous words** through the recurrence.
	- ((647b7fd0-5beb-4ace-b593-4fcb06855814))
	  collapsed:: true
		- RNNs can’t capture long-range dependencies:
		- effectively have one layer per word in the sentence
		  实际上每个句子中的单词都对应一层
		- all context information has to be passed by the hidden layer
		  所有上下文信息都必须通过隐藏层传递
		- vanishing gradients: the gradient from the last word often never reaches the first
		  梯度消失：最后一个单词的梯度常常无法传递到第一个单词
	-
- Train with SGD and Backpropagation through Time
- RNN extensions: Long-Short Term Memory (LSTM)
  collapsed:: true
	- ((647b81fc-d525-492f-bed2-607fbe619408)) 简介 [[card]]
	  collapsed:: true
		- ((647b827b-c649-4981-ae52-9fe39147b225))
		- A memory cell is used in addition to the hidden layer to control what information from previous timesteps is useful in predicting.
		- 在隐藏层中,额外引入了一个记忆单元. 该记忆单元来控制上一个时步中哪些信息对于预测结果是非常有用的.
	- LSTM 具体组成 [[card]]
	  collapsed:: true
		- (LSTM) Forget gate  (what info to throw away from previous steps) [[card]]
			- $$f_t=\sigma\left(W_f\left[h_{t-1}, x_t\right]\right)$$
		- (LSTM) Input gate (what new info will be stored in the memory cell) [[card]]
			- $$
			  i_t=\sigma\left(W_i\left[h_{t-1}, x_t\right]\right)
			  $$
		- (LSTM) New memory cell candidate values: [[card]]
			- $$
			  \tilde{C}_t=\tanh \left(W_C\left[h_{t-1}, x_t\right]\right)
			  $$
		- (LSTM) Update memory cell (using input and output gates): [[card]]
			- $$
			  C_t=f_t * C_{t-1}+i_t * \tilde{C}_t
			  $$
		- (LSTM) Output (decide what’s the output filtered by the memory cell): [[card]]
			- $$
			  \begin{gathered}
			  o_t=\sigma\left(W_o\left[h_{t-1}, x_t\right]\right) \\
			  h_t=o_t * \tanh \left(C_t\right)
			  \end{gathered}
			  $$
- RNN extensions: ((647b84b5-bd39-4dcf-8651-2c78c70df65a)) [[card]]
  collapsed:: true
	- LSTM(Long-Short Term Memor) variant
	- (GRU) Update gate (combines input and forget gates):
	  > 决定了当前时间步的隐藏状态应该在多大程度上保留前一时间步的隐藏状态信息
		- $$
		  z_t=\sigma\left(W_z\left[h_{t-1}, x_t\right]\right)
		  $$
	- (GRU) Recurrent state (merges cell state with hidden state):
	  > 决定了计算新的候选隐藏状态时，应该在多大程度上使用前一时间步的隐藏状态
		- $$
		  r_t=\sigma\left(W_r\left[h_{t-1}, x_t\right]\right)
		  $$
	- (GRU) New output candidate values:
		- $$
		  \tilde{h}_t=\tanh \left(W\left[r_t * h_{t-1}, x_t\right]\right)
		  $$
	- (GRU) Output:
		- $$
		  h_t=\left(1-z_t\right) * h_{t-1}+z_t * \tilde{h}_t
		  $$
- ((647b8680-f06c-4757-975a-17cdd535678c)) [[card]]
  collapsed:: true
	- ((647b8694-30c0-44c1-92ef-1c1770721fba))
	- many to one (接收一个序列作为输入，但只产生一个输出): e.g. text classification, 情感分析
	- many to many (既接收序列作为输入，也产生序列作为输出 equal): e.g. PoS tagging
	- many to many (既接收序列作为输入，也产生序列作为输出 unequal): e.g. machine translation (coming next week), language generation, summarisation
- TODO ((647b86af-6775-4a5a-89f2-16637c311e20))
  collapsed:: true
	- RNNs 学习单词和句子/文档的表示
	- 由于RNNs的训练速度比Skip-Gram慢，所以单词的学习并不那么有趣：因此使用的数据更少
	- 一个提示是：使用预训练的单词向量（如skipgram）来初始化RNN的单词向量
	- 然而，RNN的句子/文档表示经常被使用！
	- 双向RNNs也可以用来学习文档的表示：一个RNN从头到尾解析输入，另一个从尾到头解析输入。
- Language modelling: return sentence probabilities as well as representations
- Text classification: learn contextualised word representations and use them to predict a given class
- Improve RNNs with Attention
	- > 传统的RNN模型会遇到长距离依赖的问题，即模型难以捕捉到序列中相隔较远的元素之间的依赖关系。通过使用注意力机制，模型可以给予这些关键信息更多的重视，从而改善其性能
	- ((647b88b8-3252-4b3e-8620-d7de2ff0654d))
		- 在多对一的任务中（例如，文本分类），通常每个时间步的输出会被合并（连接/平均/求和）然后传递给输出层
		- 这种简单的组合假设所有的表示（来自每个时间步）都有相等的贡献
		- 但这可能并非事实！
		- 注意力机制：
			- 计算从RNN获取的所有上下文化表示的加权线性组合
			- compute a weighted linear combination of all the contextualised representations obtained from the RNN:
			- $$
			  \mathbf{c}=\sum_i \mathbf{h}_i \alpha_i
			  $$
		- Pass $c$ to the output layer for classification
	- 介绍 ((647b898d-ccee-43a5-9578-ee813b44b7d0)) [[card]]
	  collapsed:: true
		- Attention usually consists of a similarity function $\phi$ followed by softmax:
			- $$
			  a_i=\frac{\exp \left(\phi\left(\mathbf{h}_{\mathbf{i}}, \mathbf{q}\right)\right)}{\sum_{k=1}^t \exp \left(\phi\left(\mathbf{q}, \mathbf{h}_{\mathbf{k}}\right)\right)}
			  $$
		- $\mathbf{q} \in R^N$ is a trainable vector (learns task specific information)
		- Additive (or tanh):
			- $$
			  \phi\left(h_i, \mathbf{q}\right)=\mathbf{q}^T \tanh \left(W \mathbf{h}_i\right)
			  $$
		- Scaled Dot-Product
			- $$
			  \phi\left(h_i, \mathbf{q}\right)=\frac{\mathbf{h}_i^T \mathbf{q}}{\sqrt{N}}
			  $$
			-
-
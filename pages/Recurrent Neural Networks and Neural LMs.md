alias:: 递归神经网络和神经语言模型

- Problem setup
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
	- RNN introduction [[card]]
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
-
- Language modelling: return sentence probabilities as well as representations
- Text classification: learn contextualised word representations and use them to predict a given class
- Improve RNNs with Attention
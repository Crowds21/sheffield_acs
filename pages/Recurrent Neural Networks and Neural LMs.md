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
	- We need to learn
		- word vectors $U$
		- hidden layer parameters $W$
		- output layer parameters $V$
	- Standard backpropagation can’t work in RNN [[card]]
		- Because of the recurrence:we reuse the hidden layer parameters $W$
	- Backpropagation Through Time
- Train with SGD and Backpropagation through Time
- RNN extensions: Long-Short Term Memory (LSTM)
- RNN extensions: Gated-Recurrent Unit (GRU)
- Language modelling: return sentence probabilities as well as representations
- Text classification: learn contextualised word representations and use them to predict a given class
- Improve RNNs with Attention
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
	- $V$ is the vocabulary and
- Recurrent Neural Networks (RNNs)
- Train with SGD and Backpropagation through Time
- RNN extensions: Long-Short Term Memory (LSTM)
- RNN extensions: Gated-Recurrent Unit (GRU)
- Language modelling: return sentence probabilities as well as representations
- Text classification: learn contextualised word representations and use them to predict a given class
- Improve RNNs with Attention
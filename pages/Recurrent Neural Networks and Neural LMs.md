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
	- ((647b7844-7de1-433d-9c4d-5904784abda2))
	- $$
	  s_n=\sigma\left(\mathbf{W} s_{n-1}+\mathbf{U} x_n\right)
	  $$
		- $s_{n-1} \in \mathcal{R}^d$
			- ”memory” of the context until word $x_{n}
		- $\mathbf{W} \in \mathcal{R}^{d \times d}$
		- $\mathbf{U} \in \mathcal{R}^{|\mathcal{V}| \times d}$
- Train with SGD and Backpropagation through Time
- RNN extensions: Long-Short Term Memory (LSTM)
- RNN extensions: Gated-Recurrent Unit (GRU)
- Language modelling: return sentence probabilities as well as representations
- Text classification: learn contextualised word representations and use them to predict a given class
- Improve RNNs with Attention
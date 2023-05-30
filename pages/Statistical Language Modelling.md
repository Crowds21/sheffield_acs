- Applications of Language Modelling
	- ((6474c887-00df-4031-b001-b80a5a16173b))
	- ((6474c8b9-68c1-4857-97fc-7d71cf472279))
	- ((6474c8c0-a054-4922-b58b-b5df4d0468f1))
	- ((6474c8c9-c1c5-47f3-aa64-7522a5b47354))
- The background of the problem
	- Training data: sentences $x^m$ with words $x_n$
	- $$
	  \begin{aligned}
	  D_{\text {train }} & =\left\{\mathbf{x}^1, \ldots, \mathbf{x}^M\right\} \\
	  \mathbf{x} & =\left[x_1, \ldots x_N\right]
	  \end{aligned}
	  $$
- Sentence probabilities
	- ((6475fb63-c2bd-4da8-a17a-584b52efef94))
	- $$
	  P(\mathbf{x})=P\left(x_1, \ldots, x_n\right), \text { for } \forall \mathbf{x} \in V^{\max N}
	  $$
	- $V$ is the vocabulary and $V^{maxN}$ all possible sentences.
- ((6476078e-e89b-4ee3-85e9-6f6e3efc9e1a)) 一元语言模型
  collapsed:: true
	- Introduction
		- Multiply $P$(each word appearing in the sentence x)
		- $$
		  P(\mathbf{x})=\prod_{n=1}^N P\left(x_n\right)=\prod_{n=1}^N \frac{c\left(x_n\right)}{\sum_{x \in V} c(x)}
		  $$
		- $c(x_n)$
			- The total number of occurrences of the word $x_n$ in the document.
		- $c(x)$
			- The number of words in the sentence. (include `<s> </s>`)
	- The potential problem
		- ((64760aa9-2bea-44e7-8921-ec223848b18f))
- ((64760ab2-3fe6-4586-802b-fbf77162f98d))
  collapsed:: true
	- Introduction
		- Assume that each word is dependent on all previous ones:
		- $$
		  \begin{aligned}
		  P(\mathbf{x}) & =P\left(x_1, \ldots, x_N\right) \\
		  & =P\left(x_1\right) P\left(x_2 \ldots x_N \mid x_1\right) \\
		  & =P\left(x_1\right) P\left(x_2 \mid x_1\right) \ldots P\left(x_N \mid x_1, \ldots, x_{N-1}\right) \\
		  & =\prod_{n=1}^N P\left(x_n \mid x_1, \ldots x_{n-1}\right) \quad \text { (chain rule) }
		  \end{aligned}
		  $$
		- $$
		  P\left(x_n \mid x_{n-1 \ldots x_1}\right)=\frac{c\left(x_1 \ldots x_{n-1}, x_n\right)}{c\left(x_1 \ldots x_{n-1}\right)}
		  $$
	- Problems of MLE
		- As we condition on more words, the counts become sparser(稀疏)
		- 我们假设训练数据是从真实分布中独立采样得到的，但在实际情况下，很多单词序列并不是等概率出现的
		- 最大似然估计在面对数据稀疏的情况下，可能会高估或低估某些事件的概率，从而影响模型的性能和预测准确性。
- ((64760bd9-f6da-4a54-8f7e-83f5d4c0c781)) 二元语言模型
	- Introduction
		- ((64760be5-a928-44da-a374-313cc7af7da7))
		- $$
		  P(\mathbf{x})=\prod_{n=1}^N P\left(x_n \mid x_{n-1}\right)=\prod_{n=1}^N \frac{c\left(x_{n-1}, x_n\right)}{c\left(x_{n-1}\right)}
		  $$
		- ((64760bfd-7e58-45b0-b4d0-a26a95bac7b5))
			- $$
			  P\left(x_n \mid x_{n-1}, \ldots, x_1\right) \approx P\left(x_n \mid x_{n-1}, \ldots, x_{n-k}\right)
			  $$
			-
	- From counts to probabilities
		- Row is the $x_{i-1}$th wrod. Col is the $x_i$th word
		- ((64762b81-265e-4037-9f4c-352dee52300e))
		- ((64762be9-a3ab-4b89-b655-b660780b382f))
			- For example $P(monkeys) = \dfrac{monkeys\ bigram\ counts}{arctic\ unigram\ counts}=0.1$
		- The result of the Bigram language model in this example
			- $\mathbf{x}=[$ arctic, monkeys, are, my, favourite, band $]$
			- $$
			  \begin{aligned}
			  P(\mathbf{x}) & =P(\text { monkeys } \mid \text { arctic }) P(\text { are } \mid \text { monkeys }) P(\text { my } \mid \text { are }) \\
			  & P(\text { favourite } \mid \text { my }) P(\text { band } \mid \text { favourite }) \\
			  & =\frac{c(\text { arctic, monkeys })}{c(\text { arctic })} \ldots \frac{c \text { (favourite, band })}{c(\text { favourite })} \\
			  & =0.1 \cdot 0.417 \cdot 0.15 \cdot 0.1 \cdot 0.1 \\
			  & =0.00006255
			  \end{aligned}
			  $$
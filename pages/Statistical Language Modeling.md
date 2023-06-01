- Applications of Language Modelling
  collapsed:: true
	- ((6474c887-00df-4031-b001-b80a5a16173b))
	- ((6474c8b9-68c1-4857-97fc-7d71cf472279))
	- ((6474c8c0-a054-4922-b58b-b5df4d0468f1))
	- ((6474c8c9-c1c5-47f3-aa64-7522a5b47354))
- The background of the problem
  collapsed:: true
	- Training data: sentences $x^m$ with words $x_n$
	- $$
	  \begin{aligned}
	  D_{\text {train }} & =\left\{\mathbf{x}^1, \ldots, \mathbf{x}^M\right\} \\
	  \mathbf{x} & =\left[x_1, \ldots x_N\right]
	  \end{aligned}
	  $$
- Sentence probabilities
  collapsed:: true
	- ((6475fb63-c2bd-4da8-a17a-584b52efef94))
	- $$
	  P(\mathbf{x})=P\left(x_1, \ldots, x_n\right), \text { for } \forall \mathbf{x} \in V^{\max N}
	  $$
	- $V$ is the vocabulary and $V^{maxN}$ all possible sentences.
- How many different kinds of Statistical Language Modelling
	- N-gram language model
	- ((64760ab5-4060-42a1-b1bf-cbbeba83054a))
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
- ((64760ab2-3fe6-4586-802b-fbf77162f98d)) 最大似然估计
  id:: 64760ab5-4060-42a1-b1bf-cbbeba83054a
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
- ((64760bd9-f6da-4a54-8f7e-83f5d4c0c781)) 二元语言模型 (Markov assumption:)
  collapsed:: true
	- Introduction
	  collapsed:: true
		- ((64760be5-a928-44da-a374-313cc7af7da7))
		- $$
		  P(\mathbf{x})=\prod_{n=1}^N P\left(x_n \mid x_{n-1}\right)=\prod_{n=1}^N \frac{c\left(x_{n-1}, x_n\right)}{c\left(x_{n-1}\right)}
		  $$
		- ((64760bfd-7e58-45b0-b4d0-a26a95bac7b5))
			- $$
			  P\left(x_n \mid x_{n-1}, \ldots, x_1\right) \approx P\left(x_n \mid x_{n-1}, \ldots, x_{n-k}\right)
			  $$
			- 在前几个单词是 xxx 的条件下, 后一个单词是 x_n 的概率
	- From counts to probabilities
	  collapsed:: true
		- Row is the $x_{i-1}$th wrod. Col is the $x_i$th word
		- ((64762b81-265e-4037-9f4c-352dee52300e))
		- ((64762be9-a3ab-4b89-b655-b660780b382f))
			- For example $P(monkeys) = \dfrac{monkeys\ bigram\ counts}{arctic\ unigram\ counts}=0.1$
		- The result of the Bigram language model in this example
		  collapsed:: true
			- $\mathbf{x}=[ arctic, monkeys, are, my, favourite, band ]$
			- $$
			  \begin{aligned}
			  P(\mathbf{x}) & =P(\text { monkeys } \mid \text { arctic }) P(\text { are } \mid \text { monkeys }) P(\text { my } \mid \text { are }) \\
			  & P(\text { favourite } \mid \text { my }) P(\text { band } \mid \text { favourite }) \\
			  & =\frac{c(\text { arctic, monkeys })}{c(\text { arctic })} \ldots \frac{c \text { (favourite, band })}{c(\text { favourite })} \\
			  & =0.1 \cdot 0.417 \cdot 0.15 \cdot 0.1 \cdot 0.1 \\
			  & =0.00006255
			  \end{aligned}
			  $$
- Longer contexts ((6478ab0c-ca0f-410d-bd37-799b7a7f525c))
  collapsed:: true
	- $$
	  P(x \mid \text { context })=\frac{P(\text { context }, x)}{P(\text { context })}=\frac{c(\text { context }, x)}{c(\text { context })}
	  $$
	- Influence of longer context
		- the more likely to capture long-range dependencies:
		- the sparser the counts (zero probabilities)
	- Normarlly 5-grams and training sets with billions of tokens are common.
- Handle ((6478ade1-e1ce-403b-afed-7db1d622c5ab))
  collapsed:: true
	- If a word was never encountered in training, any sentence containing it will have probability 0
	- Unknown words problems happen when
	  collapsed:: true
		- all corpora are finite(有限的)
		- new words emerging
	- Solutions
	  collapsed:: true
		- replacing low-frequency words with a special UNKNOWN token
		- TODO Use classes of unknown words, e.g. names and numbers
- ((6478ae8e-e02e-4d7d-97c7-af9e1e956c76)) of LM
	- Dealing with large datasets requires efficiency [[card]]
	  collapsed:: true
		- Use log probabilities to avoid underflows (small numbers)
		- Efficient data structures for sparse counts, e.g. lossy data structures Bloom filters)
	- Train and evaluate the language models
- ((6478afdc-8cb5-44c2-ac16-562350498a85)) 内部评估
	- ((6478b049-bd2f-4c8b-b9e1-b311a70cc230)) of LMs [[card]]
	  collapsed:: true
		- How often the LM predicts the correct word, the higher the better
	- ((6478b043-df43-44f2-be12-dbb396a9dfc1)) of LMs[[card]]
		- Perplexity is the inverse probability of the test set
		- $\mathbf{x}=\left[x_1, \ldots, x_N\right]$, normalised by the number of words $N$:
		- $$
		  \begin{aligned}
		  P P(\mathbf{x}) & =P\left(x_1, \ldots, x_N\right)^{1 / N} \\
		  & =\sqrt[N]{\frac{1}{P\left(x_1, \ldots, x_N\right)}} \\
		  & =\sqrt[N]{\frac{1}{\prod_{i=1}^N P\left(x_i \mid x_1, \ldots x_{i-1}\right)}}
		  \end{aligned}
		  $$
		-
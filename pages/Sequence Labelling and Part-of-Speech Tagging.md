- The first problem of modeling: Language Modeling
- Assign a label to each word in a sequence
	- Part-of-Speech (POS) Tagging
		- Usage
			- text classification
			- language modelling
			- syntactic parsing
			- named entity recognition
			- question answering
		- Most used tag set [Penn Treebank P.O.S. Tags (upenn.edu)](https://www.ling.upenn.edu/courses/Fall_2003/ling001/penn_treebank_pos.html)
			- Also we can use [Universal POS tags (universaldependencies.org)](https://universaldependencies.org/u/pos/)
	- Named Entity Recognition
	- Machine Translation (reconstruct word alignments)
- Sequence labelling
	- $$
	  \begin{aligned}
	  D_{\text {train }} & =\left\{\left(\mathbf{x}^1, \mathbf{y}^1\right) \ldots\left(\mathbf{x}^M, \mathbf{y}^M\right)\right\} \\
	  \mathbf{x}^m & =\left[x_1, \ldots x_N\right] \\
	  \mathbf{y}^m & =\left[y_1, \ldots y_N\right]
	  \end{aligned}
	  $$
	- $x$ is the sequence of words. And $y$ is the sequence of POS tag
	- $$
	  \hat{\mathbf{y}}=\underset{\mathbf{y} \in \mathcal{Y}^{\mathcal{N}}}{\arg \max } f(\mathbf{x}, \mathbf{y})
	  $$
- Markov model 存在的问题
	- 使用 tags $y$ 而不是单词
	- $$
	  P(\mathbf{y})=\prod_{n=1}^N P\left(y_n \mid y_{n-1}\right)
	  $$
-
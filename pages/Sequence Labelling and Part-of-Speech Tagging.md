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
- Hidden Markov Model (HMM)
  ref:: ((64073a20-f69f-432b-9eb8-77099c627b10))
	- ((64073cfb-8b18-43e0-b4b3-5fcf7435615e))
		- Bayes rule
			- $\hat{\mathbf{y}}=\underset{\mathbf{y} \in \mathcal{Y}^{\mathcal{N}}}{\arg \max } P(\mathbf{y} \mid \mathbf{x})$
		- word probabilities are constant
			- $\hat{\mathbf{y}}=\underset{\mathbf{y} \in \mathcal{Y}^{\mathcal{N}}}{\arg \max } \frac{P(\mathbf{x} \mid \mathbf{y}) P(\mathbf{y})}{P(\mathbf{x})}$
		- 1st order Markov
			- $\hat{\mathbf{y}}=\underset{\mathbf{y} \in \mathcal{Y}^{\mathcal{N}}}{\arg \max } P(\mathbf{x} \mid \mathbf{y}) P(\mathbf{y})$
		- $\hat{\mathbf{y}} \approx \underset{\mathbf{y} \in \mathcal{Y}^{\mathcal{N}}}{\arg \max } \prod_{n=1}^N P\left(x_n \mid y_n\right) P\left(y_n \mid y_{n-1}\right)$
		-
	- ((64073e47-8618-4cc8-be69-a3548fff1581))
		- Maximum likelihood estimation
	- ((64073ead-7e23-445d-9f0c-81604e15b073))
		- $$
		  \hat{\mathbf{y}}=\underset{\mathbf{y} \in \mathcal{Y}^{\mathcal{N}}}{\arg \max } \prod_{n=1}^N P\left(x_n \mid y_n\right) P\left(y_n \mid y_{n-1}\right)
		  $$
	- ((64073eda-c8b2-4f78-9531-8d8fefbaf4b6))
		-
-
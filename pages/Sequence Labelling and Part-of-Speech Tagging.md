- Applications of Sequence Labelling [[card]]
	- Part-of-Speech (POS) Tagging
	- Named Entity Recognition
	- Machine Translation (reconstruct word alignments)
- Classes of PoS Tags
- Assign a label to each word in a sequence
	- Part-of-Speech (POS) Tagging
		- Open class (具有较高的词汇变化和词汇增长能力的词性类别)
			- nouns, verbs, adjevtives
		- Closed class (具有相对稳定、数量较少且不易增加新成员的词性类别)
			- determiners, prepositions, conjunctions, etc
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
	- ((64073ee4-219b-4fe1-9ea6-cbbc1fa5add5))
- ((64073f07-fb05-4a54-b2a7-9625e591a103))
- ((64073fe6-0f5a-4952-8a4a-4b70f50c1fea))
- ((64074195-6461-4bbf-8d0c-9fd327b1794e))
- ((640746f7-d2bf-4f45-9723-d7942db3509f))
	- [维特比算法 - 维基百科，自由的百科全书 (wikipedia.org)](https://zh.wikipedia.org/zh-hans/%E7%BB%B4%E7%89%B9%E6%AF%94%E7%AE%97%E6%B3%95)
	- ((64074707-ea47-4d02-85e4-eb00b3494ac0))
- ((64074700-35a9-4304-9f3e-adad07046319))
- ((640749d5-1510-4229-b719-eb976e71e2ee))
	- [如何通俗的理解beam search？ - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/82829880)
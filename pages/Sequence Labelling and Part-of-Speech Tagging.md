- Applications of Sequence Labelling [[card]]
	- Part-of-Speech (POS) Tagging
	- Named Entity Recognition
	- Machine Translation (reconstruct word alignments)
- Classes of PoS Tags
- Assign a label to each word in a sequence
	- Part-of-Speech (POS) Tagging [[card]]
		- Open class (具有较高的词汇变化和词汇增长能力的词性类别)
			- nouns, verbs, adjevtives
		- Closed class (具有相对稳定、数量较少且不易增加新成员的词性类别)
			- determiners, prepositions, conjunctions, etc
	- ((6478ca45-d231-4659-849e-7ae837d08dbd))
		- Most used tag set [Penn Treebank P.O.S. Tags (upenn.edu)](https://www.ling.upenn.edu/courses/Fall_2003/ling001/penn_treebank_pos.html)
		- Also we can use [Universal POS tags (universaldependencies.org)](https://universaldependencies.org/u/pos/)
- Sequence labelling problem background
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
	- 在序列标注（Sequence Labeling）中，上述公式表示了一种常见的序列标注模型的形式。
	- $D_{\text{train}}$ 表示训练数据集，其中包含 $M$ 个训练样本。每个样本由一个输入序列 $\mathbf{x}^m$ 和对应的标签序列 $\mathbf{y}^m$ 组成。
	- $\mathbf{x}^m$ 表示第 $m$ 个训练样本的输入序列，由 $N$ 个元素 $x_1, x_2, \ldots, x_N$ 组成。这些元素可以是单词、字符或其他语言单位，根据具体任务而定。
	- $\mathbf{y}^m$ 表示第 $m$ 个训练样本的标签序列，由 $N$ 个元素 $y_1, y_2, \ldots, y_N$ 组成。这些标签表示了对应输入序列元素的分类或标记。
	- $\hat{\mathbf{y}}$ 表示预测的标签序列，它是通过最大化函数 $f(\mathbf{x}, \mathbf{y})$ 得到的最优解。函数 $f(\mathbf{x}, \mathbf{y})$ 是序列标注模型定义的得分函数或概率模型，它接受输入序列 $\mathbf{x}$ 和标签序列 $\mathbf{y}$，并计算出一个得分值。通过寻找使得得分最大的标签序列 $\mathbf{y}$，我们可以得到最佳的预测结果。
	  
	  这个公式展示了序列标注的基本框架，其中通过训练数据集来学习模型的参数，然后使用学习得到的模型来对新的输入序列进行预测，得到最优的标签序列。具体的模型和优化算法可以根据任务的特点和需求进行选择和定制。
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
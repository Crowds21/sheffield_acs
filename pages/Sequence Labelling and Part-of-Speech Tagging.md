- X(Input) Sequence of words
- Y(Output) Sequence of POS
- Applications of Sequence Labelling [[card]]
	- Part-of-Speech (POS) Tagging
	- Named Entity Recognition
	- Machine Translation (reconstruct word alignments)
- Classes of PoS Tags
- Assign a label to each word in a sequence
  collapsed:: true
	- Part-of-Speech (POS) Tagging [[card]]
		- Open class (具有较高的词汇变化和词汇增长能力的词性类别)
			- nouns, verbs, adjevtives
		- Closed class (具有相对稳定、数量较少且不易增加新成员的词性类别)
			- determiners, prepositions, conjunctions, etc
	- ((6478ca45-d231-4659-849e-7ae837d08dbd))
		- Most used tag set [Penn Treebank P.O.S. Tags (upenn.edu)](https://www.ling.upenn.edu/courses/Fall_2003/ling001/penn_treebank_pos.html)
		- Also we can use [Universal POS tags (universaldependencies.org)](https://universaldependencies.org/u/pos/)
- Sequence labelling problem background
  collapsed:: true
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
	- 模型$f()$ 应该使得 $\hat{\mathbf{y}}$结果最大
- Markov model 存在的问题
  collapsed:: true
	- 使用 tags $y$ 而不是单词
	- $$
	  P(\mathbf{y})=\prod_{n=1}^N P\left(y_n \mid y_{n-1}\right)
	  $$
- Hidden Markov Model (HMM)
  ref:: ((64073a20-f69f-432b-9eb8-77099c627b10))
	- ((64073cfb-8b18-43e0-b4b3-5fcf7435615e)) [[card]]
		- Bayes rule
			- $\hat{\mathbf{y}}=\underset{\mathbf{y} \in \mathcal{Y}^{\mathcal{N}}}{\arg \max } P(\mathbf{y} \mid \mathbf{x})$
		- word probabilities are constant
			- $\hat{\mathbf{y}}=\underset{\mathbf{y} \in \mathcal{Y}^{\mathcal{N}}}{\arg \max } \frac{P(\mathbf{x} \mid \mathbf{y}) P(\mathbf{y})}{P(\mathbf{x})}$
		- 1st order Markov
			- $\hat{\mathbf{y}}=\underset{\mathbf{y} \in \mathcal{Y}^{\mathcal{N}}}{\arg \max } P(\mathbf{x} \mid \mathbf{y}) P(\mathbf{y})$
		- $\hat{\mathbf{y}} \approx \underset{\mathbf{y} \in \mathcal{Y}^{\mathcal{N}}}{\arg \max } \prod_{n=1}^N P\left(x_n \mid y_n\right) P\left(y_n \mid y_{n-1}\right)$
		- 能够使得该改概率公式结果最大的那个 $y$ 即为对应的 POS (Tag)
		  collapsed:: true
			- To derive the approximation, let's break down the equation step by step:
			  The joint probability of the tag sequence y and the word sequence x is denoted as P(y, x). We want to find the best tag sequence that maximizes this joint probability given the word sequence, i.e., ˆy = argmax y∈YN P(y|x).
			  Using the chain rule of probability, we can express P(y, x) as the product of conditional probabilities:
			  P(y, x) = P(x|y)P(y).
			  Applying the approximation, we assume that the word probabilities P(x|y) can be factorized as a product of individual word probabilities:
			  
			  P(x|y) = ∏n=1P(xn|yn).
			  
			  This assumes that the probability of observing each word in the sequence depends only on its corresponding tag and is independent of other tags and words.
			  
			  Similarly, we assume that the tag probabilities P(y) can be factorized as a product of conditional tag probabilities:
			  
			  P(y) = ∏n=1P(yn|yn−1).
			  
			  This assumes that the probability of each tag in the sequence only depends on the previous tag and is independent of other tags and words.
			  
			  Combining the above equations, we have:
			  
			  P(y, x) ≈ P(x|y)P(y) ≈ ∏n=1P(xn|yn)P(yn|yn−1).
			  
			  Therefore, the approximation for the best tag sequence ˆy becomes:
			  
			  ˆy = argmax y∈YN ∏n=1P(xn|yn)P(yn|yn−1).
			  
			  By making these simplifying assumptions, the computation of the best tag sequence can be approximated as the product of individual word probabilities and conditional tag probabilities. This approximation allows for more efficient and tractable calculations in practice, although it may not capture all possible dependencies in the data.
	- ((64073e47-8618-4cc8-be69-a3548fff1581))
		- Maximum likelihood estimation
		- $P\left(y_n \mid y_{n-1}\right)=\frac{c\left(y_n, y_{n-1}\right)}{c\left(y_{n-1}\right)}$ (transition probabilities)
		  id:: 6478cdf0-e41e-49ba-b985-a25b528cf194
		  collapsed:: true
			- 转移概率表示从一个标签转移到另一个标签的概率
			- 举个例子，我们希望知道在已知前一个标签的情况下，下一个标签出现的概率是多少。继续以词性标注为例，我们希望知道在已知前一个词的词性为"noun"（名词）的情况下，下一个词的词性为"verb"（动词）的概率有多大。
		- $P\left(x_n \mid y_n\right)=\frac{c\left(x_n, y_n\right)}{c\left(y_n\right)}$ (emission probabilities)
		  id:: 6478cdfc-dede-4193-b1ea-95a421a6e148
		  collapsed:: true
			- 发射概率表示给定某个标签时，观察到某个特定输入的概率
			- 举个例子，假设我们要进行词性标注任务，我们希望知道在已知一个词性标签的情况下，观察到某个单词的概率。例如，对于标签"noun"（名词），我们想知道在这个标签下，观察到单词"cat"（猫）的概率有多大。
		- $c(x)$ 指的是 x 在词库中出现的次数
		- 示例
		  ((6478cf59-a798-4cce-92f7-aaf9e26a88bc))
		  计算$P(\mathbf{y} \mid \mathbf{x})$ [[card]]
			- TODO $\begin{aligned} P(\mathbf{y} \mid \mathbf{x})= & P(I \mid P P S S) P(P P S S \mid S T A R T) \\ & P(\text { can } \mid M D) P(M D \mid P P S S) \\ & P(f l y \mid N N) P(N N \mid M D)\end{aligned}$
			- emission probabilities * transition probabilities
	- ((64073ead-7e23-445d-9f0c-81604e15b073))
		- $$
		  \hat{\mathbf{y}}=\underset{\mathbf{y} \in \mathcal{Y}^{\mathcal{N}}}{\arg \max } \prod_{n=1}^N P\left(x_n \mid y_n\right) P\left(y_n \mid y_{n-1}\right)
		  $$
		- emission probabilities * transition probabilities
	- ((64073eda-c8b2-4f78-9531-8d8fefbaf4b6))
	- ((64073ee4-219b-4fe1-9ea6-cbbc1fa5add5)) [[card]]
		- They generate probabilities for words and labels, we just want labels
		- No overlapping features (e.g. unigrams+bigrams)
			- "No overlapping features"（没有重叠特征）是指在特征表示中不允许特征之间有重叠或重复的部分。例如，如果使用了单个词的特征（unigrams）和相邻两个词的特征（bigrams），则这两种特征之间不能有重叠。
		- No subword features (e.g. suffixes)
			- "No subword features"（没有子词特征）是指在特征表示中不考虑词的子词部分。例如，不使用词的后缀作为特征。这意味着特征的选择仅限于整个词本身，而不包括词的任何子词信息。
- ((64073f07-fb05-4a54-b2a7-9625e591a103))
  collapsed:: true
	- 使用逻辑回归表示概率
- ((64073fe6-0f5a-4952-8a4a-4b70f50c1fea)) 条件随机场 CRF
  ref:: [从隐马尔科夫到条件随机场 | MaxMa Blog (anxiang1836.github.io)](https://anxiang1836.github.io/2019/11/05/NLP_From_HMM_to_CRF/)
  collapsed:: true
	- > 与传统的隐马尔可夫模型（Hidden Markov Models，HMM）相比，CRF在建模能力和表达能力上更强大。CRF能够建模更复杂的特征依赖关系，不仅考虑当前观测到的特征，还能利用上下文信息进行预测。
	- Introduction
	  collapsed:: true
		- Formula
			- $\underset{\mathbf{y} \in \mathcal{Y}^{\mathcal{N}}}{\arg \max } P_{C R F}(\mathbf{y} \mid \mathbf{x} ; \mathbf{w})=\underset{\mathbf{y} \in \mathcal{Y}^{\mathcal{N}}}{\arg \max } \sum_{n=1}^N \mathbf{w} \cdot \phi\left(y_n, y_{n-1}, \mathbf{x}, n\right)$
			- 条件随机场（Conditional Random Field，CRF）模型的目标函数，用于对给定输入序列 $\mathbf{x}$ 的输出序列 $\mathbf{y}$ 进行预测
			- $\mathcal{Y}$ 表示可能的标签集合
			- $\mathcal{N}$ 表示输入序列 $\mathbf{x}$ 的长度
			- 目标是找到使得条件随机场模型的概率 $P_{CRF}(\mathbf{y} \mid \mathbf{x}; \mathbf{w})$ 最大化的输出序列 $\mathbf{y}$。
			- $\mathbf{w}$ 是参数向量，它用于对特征函数 $\phi(y_n, y_{n-1}, \mathbf{x}, n)$ 进行加权求和。
			- 特征函数 $\phi(y_n, y_{n-1}, \mathbf{x}, n)$ 是一组根据当前标签 $y_n$、前一个标签 $y_{n-1}$、输入序列 $\mathbf{x}$ 和位置 $n$ 计算得到的特征。这些特征可以根据具体的问题和任务进行设计，用于捕捉输入序列和输出标签之间的关联关系。
		- 目标函数的含义是，通过调整参数向量 $\mathbf{w}$ 的取值，使得特征函数的加权求和最大化，从而获得最大可能的输出序列 $\mathbf{y}$。
		- 通常，为了实现这个目标，会使用一些优化算法（如随机梯度下降）来对参数向量 $\mathbf{w}$ 进行学习和优化。
		- 总结起来，上述公式表示了条件随机场模型中的目标函数，通过最大化特征函数的加权求和，来预测给定输入序列 $\mathbf{x}$ 的最佳输出序列 $\mathbf{y}$
	- ((64074195-6461-4bbf-8d0c-9fd327b1794e))
	- ((6479fc61-4061-4454-9e81-e0b8cb43d0be)) [[card]]
	  collapsed:: true
		- ((6479fcd5-6d73-4a88-841b-4f7dccc41bb2))
		  通过最小化负对数似然目标进行训练
		- $$
		  \mathbf{w}=\underset{\mathbf{w} \in \Re^d}{\arg \min } \sum_{m=1}^M-\log P_{C R F}\left(\mathbf{y}^{\mathbf{m}} \mid \mathbf{x}^{\mathbf{m}} ; \mathbf{w}\right)
		  $$
		- 使用 Stochastic Gradient Descent
- ((6479fd90-fcb5-4d7a-94b3-fec12291047f)) 使用维特比算法进行解码
	- 原理
		- 在隐马尔可夫模型（Hidden Markov Model，HMM）和条件随机场（Conditional Random Field，CRF）中，枚举所有可能的标签序列是不可行的！
		- 这时可以使用动态规划来存储和重复使用计算结果。
		- 这种做法是基于模型对独立性假设的结果。
		- 动态规划的思想是跟踪每个单词的每个词性标签达到的最高概率以及如何到达这个最高概率的路径。
	- [维特比算法 - 维基百科，自由的百科全书 (wikipedia.org)](https://zh.wikipedia.org/zh-hans/%E7%BB%B4%E7%89%B9%E6%AF%94%E7%AE%97%E6%B3%95)
	- ((64074707-ea47-4d02-85e4-eb00b3494ac0))
	  collapsed:: true
		- Backpointer matrix (回溯指针矩阵)
		  $$
		  \begin{equation}
		  \text { backptr }^{|\mathcal{Y}| \times N}
		  \end{equation}
		  $$
			- > 回溯指针矩阵（backpointer matrix）是一个大小为$|\mathcal{Y}| \times N$的矩阵，其中$|\mathcal{Y}|$表示标签集合$\mathcal{Y}$的大小，$N$表示输入序列的长度。在维特比算法中，回溯指针矩阵用于记录在计算最优路径的过程中，每个时刻每个标签的最优路径中的前一个标签。
		- instead of the max score, keep the previous tag that got it
		  > 通常情况下，维特比算法会记录每个时刻每个标签的最大分数，即到达该标签的最优路径的分数。但在这种情况下，我们不仅记录最大分数，还记录了获得最大分数的前一个标签。这是为了在后续的回溯过程中能够恢复整个最优路径。
		- argmax instead of max
		  $$
		  \text { backptr }[y, n]=\arg \max _{y^{\prime} \in \mathcal{Y}} V\left[y^{\prime}, n-1\right] \times P\left(y \mid y^{\prime}\right) \times P\left(x_n \mid y\right)
		  $$
	- ((64074700-35a9-4304-9f3e-adad07046319))
		- ((647a01a6-a60c-46a0-b4c4-ebb2955d2c13))
- ((640749d5-1510-4229-b719-eb976e71e2ee)) 束搜索 [[card]]
	- [如何通俗的理解beam search？ - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/82829880)
	- 贪心搜索每次只要最优的一个解. Beam Search 可以理解为每次保留最优的 k 个解. 贪心即为 k=1 的 Beam Search
	- ((647a038b-e682-4843-a7f6-2c0d78bbc986))
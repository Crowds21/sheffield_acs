- ![com6513.pdf](../assets/com6513_1685374358009_0.pdf)
- Part1
	- What is a language model? 
	  Describe the data required to train a language model
	  and what a trained model is expected to return
		- Language model is
			- A language model is a type of artificial intelligence model that is **designed to predict and generate human-like text based on the patterns and structures learned from a given training dataset.** It **captures the statistical relationships and dependencies between words or characters in a language.**
			  语言模型是一种人工智能模型，旨在根据从给定训练数据集中学习的模式和结构来预测和生成类似人类的文本。它捕获语言中单词或字符之间的统计关系和依赖关系
		- The data: Train set, test set, validation set. Pre-annotated text.
		- They are expected to return the probability of an unseen sentence x.
	- What is the equation for the probability of a sentence?
	  How is this probability approximated in an n-gram language model?
	  Explain the equation and the approximation terms. [[card]]
		- $$
		  P(\mathbf{x})=P\left(x_1, \ldots, x_n\right), \text { for } \forall \mathbf{x} \in V^{\max N}
		  $$
		- Different models
			- Unigram
			  $$
			  P(\mathbf{x})=\prod_{n=1}^N P\left(x_n\right)=\prod_{n=1}^N \frac{c\left(x_n\right)}{\sum_{x \in V} c(x)}
			  $$
			- Likehood
			  $$
			  \begin{aligned}
			  P(\mathbf{x}) & =P\left(x_1, \ldots, x_N\right) \\
			  & =P\left(x_1\right) P\left(x_2 \ldots x_N \mid x_1\right) \\
			  & =P\left(x_1\right) P\left(x_2 \mid x_1\right) \ldots P\left(x_N \mid x_1, \ldots, x_{N-1}\right) \\
			  & =\prod_{n=1}^N P\left(x_n \mid x_1, \ldots x_{n-1}\right) \quad \text { (chain rule) }
			  \end{aligned}
			  $$
			- Bigram
			  $$
			  P(\mathbf{x})=\prod_{n=1}^N P\left(x_n \mid x_{n-1}\right)=\prod_{n=1}^N \frac{c\left(x_{n-1}, x_n\right)}{c\left(x_{n-1}\right)}
			  $$
		- Context(N-gram)
		  $$
		  P(x \mid \text { context })=\frac{P(\text { context }, x)}{P(\text { context })}=\frac{c(\text { context }, x)}{c(\text { context })}
		  $$
		-
	- What is add-1 smoothing? 
	  Why is it important for language modelling? 
	  Describe using equations how add-1 smoothing is applied to the bigram language model. [[card]]
		- {{embed ((6478b78a-05e0-4e22-9076-ab0f9eb8c33f))}}
		- {{embed ((6478b7b7-adbf-4498-99c4-d8a7d8f0cfe5))}}
		- {{embed ((6478b22a-97ba-45d9-8280-5faf76a70efe))}}
		- {{embed ((6478b22a-e2b9-4dfb-bb6e-6a0ecb7e226a))}}
		- $$
		  P(\mathbf{x})=\prod_{n=1}^N P\left(x_n \mid x_{n-1}\right)=\prod_{n=1}^N \frac{c\left(x_{n-1}, x_n\right)+1}{c\left(x_{n-1}\right)+ |V|}
		  $$
		-
	- Language models can be evaluated intrinsically and extrinsically. 
	  Discuss the advantages and disadvantages for each approach
	  Describe TWO methods for intrinsic and THREE for extrinsic evaluation. [[card]]
		- 内部评价 (通过评估内部质量和预测语言的能力,来直接评估语言模型的性能)
			- 直接评估 direct assessment 受环境控制 Controled environment,
			- 有限的上下文 limited context
		- 外部评价(根据模型在特定的下游任务和应用程序中的表现,来评估模型)
			- 和任务相关 task relevance,
			- dependency on downstream tasks
		- Intrinsic evaluation
			- {{embed ((6478b22a-998d-4e95-8a2d-479cc1b4c52e))}}
			- {{embed ((6478b22a-a1f5-4bab-8a43-817a2e39ebaf))}}
		- {{embed ((6478b412-ed9b-47a3-8253-94c61d7cfaba))}}
- Part2
	- In HMM tagger's estimate, 
	  $x=\left\{x_1, \ldots, x_n\right\}$ is the given word sequence.
	  $y=\left\{y_1, \ldots, y_n\right\}$, and $Y$ is a set of possible tags.
	  $\hat{y}=\underset{y \in \mathcal{Y}^{\mathcal{N}}}{\operatorname{argmax}} P(y \mid x)$, $\hat{y}$ is the best tag sequence.
	  
	  $\hat{y}=\underset{y \in \mathcal{Y}^{\mathcal{N}}}{\operatorname{argmax}} \prod_{n=1}^N P\left(x_n \mid y_n\right) P\left(y_n \mid y_{n-1}\right)$
	  How this approximation is derived? [[card]]
		- Based on Bayes rule, we can get
		  $P(\mathbf{y} \mid \mathbf{x})=\frac{P(\mathbf{x} \mid \mathbf{y}) P(\mathbf{y})}{P(\mathbf{x})}$
		  $\hat{\mathbf{y}}=\underset{\mathbf{y} \in \mathcal{Y}^{\mathcal{N}}}{\arg \max } \frac{P(\mathbf{x} \mid \mathbf{y}) P(\mathbf{y})}{P(\mathbf{x})}$
		- And word probabilities are constant, so we can ignore $P(x)$
		  $\hat{\mathbf{y}}=\underset{\mathbf{y} \in \mathcal{Y}^{\mathcal{N}}}{\arg \max } P(\mathbf{x} \mid \mathbf{y}) P(\mathbf{y})$
		  The sequence $y$  which can make $P(x|y)P(y)$ has the largest value is the sequence we want.
		- Based on 1st order Markov, we know
		  $P(\mathbf{y})=\prod_{n=1}^N P\left(y_n \mid y_{n-1}\right)$
		- $\hat{\mathbf{y}} \approx \underset{\mathbf{y} \in \mathcal{Y}^{\mathcal{N}}}{\arg \max } \prod_{n=1}^N P\left(x_n \mid y_n\right) P\left(y_n \mid y_{n-1}\right)$
		- > Joint Probability Distribution: $P(x,y) = P(x)P(y)$
	- Consider the sentence `I play games`. The following counts are observed in a corpus:
	  1. unigram word/tag counts; 
	  2. bigram tag counts; and
	  3. counts of occurrences of a word with a particular part-of-speech tag (see the corresponding tables below). 
	  
	  Here <s> denotes a special start of sentence marker.
	  ((647e0e63-efa3-4799-8866-0b8c3e7ac618))
	  
	  **Questions**
	  1. Write down the equations for computing the Maximum Likelihood estimates of $P(x_n|y_n)$ and $P(y_n|y_{n−1})$
	  2. Use them to tag the given word sequence by computing $\hat{y}$
	  3. You do not need to calculate all of the transition probabilities or the emission probabilities, but you should show how you would calculate one of each.
	  > Note: If you do not have a calculator, you may leave your answer in the form of an arithmetic expression(s) involving integers.
		- ### Maximum likelihood estimates
		  ((6478cdf0-e41e-49ba-b985-a25b528cf194))
		  ((6478cdfc-dede-4193-b1ea-95a421a6e148))
		- Draft
			- We assume that each word is dependent on all previous ones.
			  $$
			  \begin{aligned}
			  P(\mathbf{x}) & =P\left(x_1, \ldots, x_N\right) \\
			  & =P\left(x_1\right) P\left(x_2 \ldots x_N \mid x_1\right) \\
			  & =P\left(x_1\right) P\left(x_2 \mid x_1\right) \ldots P\left(x_N \mid x_1, \ldots, x_{N-1}\right) \\
			  & =\prod_{n=1}^N P\left(x_n \mid x_1, \ldots x_{n-1}\right) \quad \text { (chain rule) }
			  \end{aligned}
			  $$
			  
			  Problems: As we condition on more words, the counts become **sparser**
			  >  Sparser: When certain data (words) have not appeared in the training set, resulting in a probability of zero for these 'words'. This can impact the prediction results.
		- ### Tag the given word sequence (Example of greedy)
		  $P\left(x_n \mid x_{n-1 \ldots x_1}\right)=\frac{c\left(x_1 \ldots x_{n-1}, x_n\right)}{c\left(x_1 \ldots x_{n-1}\right)}$
		- $$P\left(x_1 \mid y_1\right)=\left\{\begin{array}{l}V B=0 \\ N N=0 \\ P R P= not 0\end{array}\right.$$
		- $$P\left(y_1 \mid y_0\right)=\left\{\begin{array}{l}
		  V B=\frac{789}{50000} \\ 
		  N N=\frac{5783}{50000} \\ 
		  P R P=\frac{2304}{50000}
		  \end{array}\right.$$
		- So $y_1 = PRP$
		- $$P\left(x_2 \mid y_2\right)=\left\{\begin{array}{l}V B=\frac{26}{148787} \\ NN=\frac{35}{253048} \\ P R P=0 \end{array}\right.$$
		- $$
		  P\left(y_2 \mid y_1 \right)=\left\{\begin{array}{l}
		  VB=\frac{1492}{64520} \\ 
		  NN=\frac{68}{64520} 
		  \end{array}\right.$$
		- Because $\underset{y \in \mathcal{Y}^{\mathcal{N}}}{\operatorname{argmax}}  P\left(x_2 \mid y_2\right) P\left(y_2 \mid y_{1}\right)$
		  So $y2=VB$
		- $$
		  P\left(x_3 \mid y_3\right)=\left\{\begin{array}{l}
		  V B=\frac{82}{148787} \\ 
		  NN=\frac{171}{253048} \\ 
		  P R P=0 \end{array}\right.
		  $$
		- $$
		  P\left(y_3 \mid y_2\right)=\left\{\begin{array}{l}
		  V B=\frac{43}{148787} \\ 
		  NN=\frac{7432}{148787} \\ 
		  P R P=0 \end{array}\right.
		  $$
		- So $y_3=NN$
		-
	- ((647f5225-b67f-4ad4-a3cb-8908346c7cce)) is the most commonly used algorithm to calculate the most probable path through a HMM efficiently. 
	  Describe the Viterbi algorithm using pseudocode and any auxiliary data structures it employs. [[card]]
		- ### Data structure
			- **Backpointer matrix** $\text { backptr }^{|\mathcal{Y}| \times N}$
				- The tag of the previous word when the current word is tagged with a certain tag with the highest probability.
			- **Viterbi matrix** $v^{|\mathcal{Y}| \times N}$
				- The  highest probabilities of current word with specific tag
			- **Input word sequence** $x=\left[x_1, \ldots, x_N\right]$
			- **Tag sequence** $y=\left[y_1, \ldots, y_N\right]$
			- **Tag collection** $s=\left[s_1, \ldots, s_T\right]$
			- **Transition probabilities**: $Tans(y_n, y_{n-1})$
			- **Emission probabilities**: $Emi(x_n,y_n)$
		- ### Pseudocode
			- ((647a01a6-a60c-46a0-b4c4-ebb2955d2c13))
		- 矩阵 V 中的每一个节点中存储的是,单词 x_n 对于不同的 y_n 所获得的最大 emission * transion.
		  矩阵 Back 中存储的是 单词 x_n 对于不同的 y_n 所获得最大 emission * transion后,此时 x_(n-1)对应的 y_(n-1)
		- 类似一个全连接的神经网络
	- Beam Searc Pseudocode and Data structure
		- **Current layer result** $current$
		- **Last layer result**  $last$
		- **Input word sequence** $x=\left[x_1, \ldots, x_N\right]$
		- **Tag collection** $s=\left[s_1, \ldots, s_T\right]$
		- **Transition probabilities**: $Tans(y_n, y_{n-1})$
		- **Emission probabilities**: $Emi(x_n,y_n)$
		- **TOP-K:** function to keep the max value.
		- for n in N
			- for y in S
				- current = last * $Tans(y_n, y_{n-1})$ * $Emi(x_n,y_n)$
				- last = TOP-K (current)
		- return TOP-1
		-
- Part3
	- What are distributed word representations? How do they compare to one-hot encoding [[card]]
		- distributed word representations 可以表示词与词之间的相似度.
		  Distributed word representations, also known as word embeddings, are vector representations of words in a continuous and low-dimensional space.
		- 可以画一个坐标系,画一个 onehot 示例
		- onehot 只能表示该句子在词库中是否存在. 但是无法计算两个词之间的相似度
	- What is one-hot encoding, what’s the problem in one-hot encoding? And how to solve this problem?
	  ref:: ((63dfaf3c-7e1d-4c93-9465-580cd48af74b))
	  $\mathcal{V}=\{\text { apple, apricot, chocolate, love, pie, pineapple }\}$ [[card]]
		- $|\mathcal{V}|=6$
		- $\begin{aligned}\text { apricot } & =\mathbf{x}_2=[0,1,0,0,0,0] \\ \text { pineapple } & =\mathbf{x}_3=[0,0,0,0,0,1]\end{aligned}$
		- The problem
			- $$
			  \begin{aligned}
			  \operatorname{dot}\left(\mathbf{x}_2, \mathbf{x}_3\right) & =0 \cdot 0+1 \cdot 0+0 \cdot 0+0 \cdot 0+0 \cdot 0+0 \cdot 1 \\
			  & =0
			  \end{aligned}
			  $$
			- $$
			  \operatorname{cosine}\left(\mathbf{x}_2, \mathbf{x}_3\right)=\frac{\mathbf{x}_2 \cdot \mathbf{x}_3}{\left|\mathbf{x}_2\right|\left|\mathbf{x}_3\right|}=\frac{0}{1 \cdot 1}=0
			  $$
			- Every word is equally different from every other word. But apricot(杏) and pineapple(菠萝) are related
		- Use contextual information.
	- Calculate Vector Similarity [[card]] 
	  ref:: ((63dfa77e-72b9-4abb-b0bf-2a9711d76136))
		- Dot(inner) product
			- $\operatorname{dot}\left(\mathbf{x}_1, \mathbf{x}_2\right)=\mathbf{x}_1 \cdot \mathbf{x}_2=\mathbf{x}_1 \mathbf{x}_2^{\top}=\sum_{i=1}^d x_{1, i} x_{2, i}$
		- Cosine similarity
			- $\operatorname{cosine}\left(\mathbf{x}_1, \mathbf{x}_2\right)=\frac{\mathbf{x}_1 \cdot \mathbf{x}_2}{\left|\mathbf{x}_1\right|\left|\mathbf{x}_2\right|}=\frac{\sum_{i=1}^d x_{1, i} \cdot x_{2, i}}{\sqrt{\sum_{i=1}^d\left(x_{1, d}\right)^2} \sqrt{\sum_{i=1}^d\left(x_{2, d}\right)^2}}$
			-
	- How one can obtain sparse distributed word representations from a corpus by counting word contexts
		- 通过 ifidf 来获取词向量时,由于文档-词汇矩阵中,大部分位置为 0,所以被称为稀疏矩阵
	- how the choices of context window size, context representation and count post-processing affect the representations learned.
		- ((6478b22a-22b2-4481-92ae-8a9c5819239a))
		- window size
			- 窗口大获取的信息更多
		- context representation
			- Continuous Bag-of-Words (CBOW)
			- Skip-gram
			- ((64811055-5f93-4cd3-b051-1f2e9a6d2582))
		- count post-processing
			- Subsampling Frequent Word
			- Negative Sampling
	- One example of intrinsic word representation evaluation and One example of extrinsic word representation
		- {{embed ((6478b412-ed9b-47a3-8253-94c61d7cfaba))}}
		- {{embed ((6478b22a-97fb-4cad-b22f-3ec4efacd4b2))}}
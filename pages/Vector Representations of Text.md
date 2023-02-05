-
- Introduction
  collapsed:: true
	- Why is nlp challenging (overall) [[card]] 
	  ref:: ((63dfa07c-7f26-4748-9b6e-83e438c17179))
	  collapsed:: true
		- Natural languages (unlike programming languages) are not designed; they evolve
			- new words appear constantly
			- syntactic rules are flexible
			- ambiguity is inherent
		- world knowledge is necessary for interpretation
		- many languages, dialects, styles
	- Challenges in Traditional rule-based artificial intelligenc and Learning from data (machine learning) adapts [[card]]
	  collapsed:: true
		- Rule-based
			- requires expert knowledge to engineer the rules
			- not flexible to adapt in multiple languages, domains, applications
		- Machine leanring
			- to evolution: just learn from new data
			- to different applications: just learn with the appropriate target representation
- Vectors and Vector Spaces
  collapsed:: true
	- ((63dfa75a-3616-4992-8703-6c1f7b2f58ae))
	- ((63dfa760-9d6f-4e6d-9938-6fbd0d1eaac7))
- Calculate Vector Similarity [[card]] 
  ref:: ((63dfa77e-72b9-4abb-b0bf-2a9711d76136))
  collapsed:: true
	- Dot(inner) product
		- $\operatorname{dot}\left(\mathbf{x}_1, \mathbf{x}_2\right)=\mathbf{x}_1 \cdot \mathbf{x}_2=\mathbf{x}_1 \mathbf{x}_2^{\top}=\sum_{i=1}^d x_{1, i} x_{2, i}$
	- Cosine similarity
		- $\operatorname{cosine}\left(\mathbf{x}_1, \mathbf{x}_2\right)=\frac{\mathbf{x}_1 \cdot \mathbf{x}_2}{\left|\mathbf{x}_1\right|\left|\mathbf{x}_2\right|}=\frac{\sum_{i=1}^d x_{1, i} \cdot x_{2, i}}{\sqrt{\sum_{i=1}^d\left(x_{1, d}\right)^2} \sqrt{\sum_{i=1}^d\left(x_{2, d}\right)^2}}$
		-
- Types of Vector Spaces of Text
  collapsed:: true
	- word-word (term-context)
	- document-word (bag-of-words)
- Its purpose of vector representations of text
  ref:: ((63dfa9b7-0b0a-408b-9350-fcf02cf32525))
  collapsed:: true
	- Encode the meaning of words so we can compute ==semantic similarity== between them
	- Document retrieval
	- Apply Machine Learning on textual data
- Text units
  ref:: ((63dfaea8-5504-4321-8634-048530c47c5a))
  collapsed:: true
	- word (token/term):
	- document (text sequence/snippet)
- The steps of Textprocessing
  collapsed:: true
	- ((63dfaede-9ef5-44aa-b0ac-d5155ea6a3bd))
	- lowercasing
	- punctuation/number/stop/infrequent word removal
	- stemming
- TODO ((63dfaf3c-7e1d-4c93-9465-580cd48af74b))
- Distributional Hypothesis in NLP [[card]]
  collapsed:: true
	- ((63dfaf8c-1ffc-4ee4-9fbe-92b341b1bff3))
- Word-Word Matrix
  ref:: ((63dfafb3-3d18-4d8d-8a33-e7e6db41c3e8))
  collapsed:: true
	- 矩阵$X$,维度为$n\times m$,$n=|\mathcal{V}|$ (目标词汇) , $m=\left|\mathcal{V}_c\right|$ (context 词汇)
	- 对于$\mathcal{V}$中的每一个单词$x_i$,计算他和上下文中的词汇$x_j$一起出现的次数
	- 用一个上下文窗口($\pm k$, 即$x_i$左右两侧的单词数)
	- 计算大文档的词汇频率
	- 通常，目标词和上下文词词汇表是相同的，形成一个方阵
	- 示例, 行为target words, 列为 context words
	  $$
	  \begin{array}{lrrrr|rrr|} 
	  & \text { aardvark } & \text { computer } & \text { data } & \text { pinch } & \text { result } & \text { sugar } & \ldots \\
	  \hline \text { apricot } & 0 & 0 & 0 & 1 & 0 & 1 & \\
	  \text { pineapple } & 0 & 0 & 0 & 1 & 0 & 1 \\
	  \text { digital } & 0 & 2 & 1 & 0 & 1 & 0 \\
	  \text { information } & 0 & 1 & 6 & 0 & 4 & 0
	  \end{array}
	  $$
	  根据上图计算
	  $$
	  \begin{aligned}
	  & \operatorname{cosine}(\text { apricot, pineapple })=1 \\
	  & \operatorname{cosine}(\text { apricot, digital })=0
	  \end{aligned}
	  $$
- Document-Word Matrix
  ref:: ((63dfb2cb-18ed-421b-89c5-0a46bf1cef41))
	- 一个矩阵 $X$,$|D| \times|\mathcal{V}|$, 其中行是语料库$D$中的文档，列是$V$中的词汇
	- 对于每一个文档,确定单词$w \in \mathcal{V}$出现的次数
	- $$
	  \begin{array}{|c|c|c|c|c|}
	  \hline Doc  &  \text { bad } & \text { good } & \text { great } & \text { terrible } \\
	  \hline Doc 1 &  14 & 1 & 0 & 5 \\
	  \hline Doc 2 & 2 & 5 & 3 & 0 \\
	  \hline Doc 3 &0 & 2 & 5 & 0 \\
	  \hline
	  \end{array}
	  $$
	- $X$也能够
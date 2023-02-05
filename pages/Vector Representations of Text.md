-
- Introduction
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
- Vector Spaces of Text
	- word-word (term-context)
	- document-word (bag-of-words)
- The role of vector representations of text
	- Semantic similarity
- ![com6513.pdf](../assets/com6513_1685374358009_0.pdf)
- Part1
	- What is a language model? 
	  Describe the data required to train a language model
	  and what a trained model is expected to return
		- Language model is
		- The data: Train set, test set, validation set. Pre-annotated text.
		- They are expected to return the probability of an unseen sentence x.
	- What is the equation for the probability of a sentence?
	  How is this probability approximated in an n-gram language model?
	  Explain the equation and the approximation terms.
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
	- What is add-1 smoothing? 
	  Why is it important for language modelling? 
	  Describe using equations how add-1 smoothing is applied to the bigram language model. [[card]]
		- {{embed ((6478b78a-05e0-4e22-9076-ab0f9eb8c33f))}}
		- {{embed ((6478b7b7-adbf-4498-99c4-d8a7d8f0cfe5))}}
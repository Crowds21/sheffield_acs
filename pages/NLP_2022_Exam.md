- ![com6513.pdf](../assets/com6513_1685374358009_0.pdf)
- Part1
	- What is a language model? 
	  collapsed:: true
	  Describe the data required to train a language model
	  and what a trained model is expected to return
		- Language model is
		- The data: Train set, test set, validation set. Pre-annotated text.
		- They are expected to return the probability of an unseen sentence x.
	- What is the equation for the probability of a sentence?
	  How is this probability approximated in an n-gram language model?
	  Explain the equation and the approximation terms.
		- $$
		  P(\mathbf{x})=P\left(x_1, \ldots, x_n\right), \text { for } \forall \mathbf{x} \in V^{\max N}
		  $$
		- For different models
		  collapsed:: true
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
	  collapsed:: true
	  Why is it important for language modelling? 
	  Describe using equations how add-1 smoothing is applied to the bigram language model. [[card]]
		- {{embed ((6478b78a-05e0-4e22-9076-ab0f9eb8c33f))}}
		- {{embed ((6478b7b7-adbf-4498-99c4-d8a7d8f0cfe5))}}
- Part2
	- In HMM tagger's estimate, 
	  collapsed:: true
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
	  collapsed:: true
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
		  collapsed:: true
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
		- $$P\left(x_1 \mid y_1\right)=\left\{\begin{array}{l}V B=0 \\ N N=0 \\ P R P=1\end{array}\right.$$
		  So $y_1 = PRP$
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
	- The Viterbi algorithm is the most commonly used algorithm to calculate the most probable path through a HMM efficiently. Describe the Viterbi algorithm using pseudocode and any auxiliary data structures it employs.
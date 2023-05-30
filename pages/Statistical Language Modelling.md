- Applications of Language Modelling
	- ((6474c887-00df-4031-b001-b80a5a16173b))
	- ((6474c8b9-68c1-4857-97fc-7d71cf472279))
	- ((6474c8c0-a054-4922-b58b-b5df4d0468f1))
	- ((6474c8c9-c1c5-47f3-aa64-7522a5b47354))
- The background of the problem
	- Training data: sentences $x^m$ with words $x_n$
	- $$
	  \begin{aligned}
	  D_{\text {train }} & =\left\{\mathbf{x}^1, \ldots, \mathbf{x}^M\right\} \\
	  \mathbf{x} & =\left[x_1, \ldots x_N\right]
	  \end{aligned}
	  $$
- Sentence probabilities
	- ((6475fb63-c2bd-4da8-a17a-584b52efef94))
	- $$
	  P(\mathbf{x})=P\left(x_1, \ldots, x_n\right), \text { for } \forall \mathbf{x} \in V^{\max N}
	  $$
	- $V$ is the vocabulary and $V^{maxN}$ all possible sentences.
- ((6476078e-e89b-4ee3-85e9-6f6e3efc9e1a))
	- Multiply $P$(each word appearing in the sentence x)
	- $$
	  P(\mathbf{x})=\prod_{n=1}^N P\left(x_n\right)=\prod_{n=1}^N \frac{c\left(x_n\right)}{\sum_{x \in V} c(x)}
	  $$
	- $c(x_n)$
		- The total number of occurrences of the word $x_n$ in the document.
	- $c(x)$
		- The number of words in the sentence. (include `<s> </s>`)
	-
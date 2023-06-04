- ((647b9356-b285-4609-82b1-50e1f1bace0c))
  collapsed:: true
	- 输入是一个序列（任意序列）
	- 输出也是一个序列（同样是任意序列，但对于我们的目标来说，这是文本）
- Demonstrating Task Neural Machine Translation (任务型神经机器翻译)
  collapsed:: true
	- What is Machine Translation? [[card]]
		- Machine Translation (MT) consists of translating a sentence $x$ from one language (the source) to a sentence $y$ in another language (the target)
	- What is Neural Machine Translation Model? [[card]]
		- Neural Machine Translation (NMT) is Machine Translation using neural networks (as opposed to alignment and phrase based translation).
		- Typically we use sequence-to-sequence models (seq2seq).
		- These models are end-to-end differentiable
	- Task Formulation
		- Example: We want to translate from English to Spanish
			- We want to find best Spanish sentence $y$, given English sentence  $x$
		- ((647cac80-2ad0-4fd2-ab21-eed164b5d387))
			- Generate sentences using a neutral network (seq2seq)
			- We are going to teach the neural network to generate candidate sentences
		- ((647cac8c-ea55-4d36-8fdb-ea6110406d04))
			- Beam Search
		- $$
		  y^{\prime}=\arg \max _y p(y \mid x, \theta)
		  $$
			- p -> model
			- $\theta$ -> parameters
- The Model Encoder-Decoder Architecture(with RNNs)
  collapsed:: true
	- ((647cad8c-f00e-4d79-a818-c3eb62ccc86a))
	- ((647cadad-4b6a-440d-a023-f0fc6c1c8890))
		- Text
		- Images
		- ((647cadde-91b0-4658-a21d-be7931ca130c))
	- ((647cade4-01e9-40d5-807a-3f958524d8bd))
		- Encoder reads the source, produces its representation, and gives it to the Decoder
		- Decoder uses the source representation to generate the output
		- representation 表示数据/输入 在模型中通过什么方式来 存储/计算 比如单词转换为 onehot.
		- ((647cae03-5633-4cf5-ac2d-8e3ca23e62dc))
	- ((647cae40-53bd-4b22-a89c-850b386a4ae0))
	- ((647cae46-c07c-4c57-93b0-fed62a24408e))
	- ((647cae91-2ced-4de5-b9d6-00cf069699b0))
	- ((647caec8-a82f-4485-aef6-ff268753c291))
	- ((647caf01-b1f0-42b9-8092-04e99b23c106))
		- Thought vector
			- 在深度学习和自然语言处理中，"思维向量"是一个高维向量，它代表了输入序列（如一段文本或一句话）的抽象表示。这个向量被用作解码器的初始状态，解码器然后根据这个"思维向量"生成输出序列
	- ((647caf4d-b6b6-4cac-8930-18344b86ad78))
		- ((647caf70-9f2b-49d7-a8b4-7874d3659e8a))
		- ((647caf83-f635-4079-9ea6-0ace05511b5e))
		- Models where information from previous time-steps is used to predict the output at the current time step are called [[Autoregressive]]
	- Alternatives of ((647cb00c-6bc7-4a55-88ef-fcb4ed627e92))
		- ((647cb040-33a9-4f6f-9dac-6c208fae6b21))
		- 指通过保留了初始权重,增加了远距离记忆
		- Take multinomial distribution instead of making a hard choice(在多个可能结果中,选择可能性最高的一个) and taking a single word
	- Find the parameters $\theta$
		- ((647cb0b0-3350-4150-b87b-93d3de6768ea))
			- Get probability distribution for the next token
			- Find the correct next target token
			- Evaluate loss and update [[Cross-Entropy Loss]]
			  $\operatorname{loss}=-\log (p( \operatorname{computadoras} ))$
			  Seq2seq is optimized as simultaneously. Backpropagation operates “end-to-end”.
				- Computadoras" 是西班牙语单词, ppt 中指计算将 computer 翻译为 Computadoras 后的概率
	- ((647cb1e1-5b3e-428f-9c52-8d47446f2aed))
		- $$
		  y^{\prime}=\arg \max _y p(y \mid x)=\arg \max _y \prod_{t=1} p\left(y_t \mid y_{<t}, x\right)
		  $$
		- Greedy Search
			- Take the argmax (most probable word) on each step of the decoder
			- PROBLEM The best token at the current step does not necessarily lead to the best sequence
		- [[Beam Search]]
			- On each step of decoder, keep track of the k most probable partial translations(called hypotheses)
			- Beam search is not guaranteed to find optimal solution. But it’s efficient!
			- $$
			  \operatorname{score}\left(y_1, \ldots, y_t\right)=\log P_{\mathrm{LM}}\left(y_1, \ldots, y_t \mid x\right)=\sum_{i=1}^t \log P_{\mathrm{LM}}\left(y_i \mid y_1, \ldots, y_{i-1}, x\right)
			  $$
			- [#A] ((647cb3c9-a45e-4033-9d4e-00324c114c4c))
			- ((647cb494-ca96-4d10-9f08-b320ac2f049d)) [[card]]
				- Different hypotheses may produce <eos> tokens on different timesteps
					- **When a hypothesis produces <eos>**, that hypothesis is complete
					- **Place it aside and continue exploring other hypotheses** via beam search
				- Usually we continue beam search until:
					- **We reach timestep T** (where T is some pre-defined cutoff), or
					- **We have at least n completed hypotheses** (where n is pre-defined cutoff)
- Improvement Attention
	- The problem we need to fix by using "Attention"
		- Translation quality drops with increase in the length of sentences.
		- (Notice that the encoder has to“pack” more information into the same vector representation or thought vector)
		- 随着句子长度的增加，翻译质量会下降。（注意，编码器必须将更多的信息'打包'到相同的向量表示或思维向量中）
	- Attention: A Biological Motivation
		- Focusing on specific information is the only way to avoid information overload.
		- Critical to biological systems. (Only way to avoid information overload, remember information processing is expensive)
	- Usage in NLP
		- We need a way to allow models to attend to (focus on) different parts of the input at different timesteps.
		- 在解码器的每一步，使用与编码器的直接连接关注源序列的特定部分。
			- 这一方法首次在 "神经机器翻译通过共同学习对齐和翻译" (Bahdanau等人，2015年) 中被提出
		- 编码器不必将整个 srouce 压缩成一个单一的向量
			- 它为所有源令牌提供表示（例如，所有的RNN状态，而不仅仅是最后一个）
	- ((647cb69c-7d3f-4bc3-86a1-46cfe07b33d2))
		- The Goal
			- 当我们生成输出时,能够直接使用到 Encoder 中的一部分 representations
			- ((647cb7fc-48e9-469c-9aa9-1ae61e12be11))
		- Weighted sum
			- Find out how “important” each of these representations.
				- $\operatorname{score}\left(s_t, h_h\right), k=1 . . N$
				- How relevant is ==source token== k for ==target step t==?
				- collapsed:: true
				  $$
				  \alpha_k^{(t)}=\frac{\exp \left(\text { score }\left(s_t, h_k\right)\right)}{\sum_{i=1}^N \exp \left(\text { score }\left(s_t, h_i\right)\right)}, k=1 . . N
				  $$
					- ((647cb8f8-c9dc-4a95-9eb0-398ddbfbb6fa))
				- WARNING: Do not confuse attention weights with learnable weights.
				  background-color:: red
				- collapsed:: true
				  $$
				  c^{(t)}=\alpha_1^{(t)} h_1+\alpha_2^{(l)} h_2+\ldots+\alpha_N^{(t)} h_N=\sum_{k=1}^N \alpha_k^{(t)} h_k
				  $$
					- ((647cb95e-877b-455d-b530-d67e6d98191e))
			-
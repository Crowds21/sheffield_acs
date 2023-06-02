- Feedforward neural networks
- ((647a0766-f61b-4090-8682-450c120927ba))
	- Sigmoid
		- $g(z)=\sigma(z)$
	- Hyperbolic Tangent
		- $g(z)=\tanh (z)=\frac{e^{2 z}-1}{e^{2 z}+1}$
	- Rectified Linear Unit (ReLU)
		- $g(z)=\max (0, z)$
- ((647a07c4-e79f-4f67-9f6c-0a8a8f8a8fd8)) [[card]]
	- ((647a07fd-0668-4c98-ab16-d85ae74623b3))
- ((647a083e-d402-48fe-88c8-a6eb85ab9f4a)) [[card]]
	- Forward Pass
		- Compute and store all the output values of all the hidden units (for each hidden layer) and the output layer
	- Backward Pass
		- Compute the gradients for the output and hidden layers with respect to the cost function $L$ and update the weights for each layer
- ((647a08ef-a0ed-4120-9599-f9482b39b5fa))
  collapsed:: true
	- ((647a090b-f14c-4938-96eb-3cd58f9cd746))
	-
- ((647a0ab9-5d5d-46b3-ad78-05d21ad93e84)) algorithm
	- ((647a0ae1-c00e-494b-b8aa-95ce70c85849))
- ((647a0aec-6eb0-4c2e-8d2a-59344e9a4670))
	- ((647a0afc-ac36-45a8-82a4-992b48f2a9b3))
- Regularisation
	- ((647a0d36-9de9-4d75-95f8-0de88b04b18c))
	- ((647a0dc6-8ae2-463a-bf53-3c20c9242424))
		- ==在激活函数之后==应用一个随机二进制掩码，即与一个包含20%随机位置为0的向量进行逐元素乘法
- ((647a10ad-1381-448d-9bff-caa162f1468b)) 实现时的注意事项
	- 学习目标非凸: 初始值很重要
		- 从小的非零值开始
		- 随机重新启动以避免局部最优解
	- 更大的学习容量会增加过拟合的可能性：需要进行正则化
	- 有许多开放的库可供使用：PyTorch、Tensorflow、MxNet、Keras等等。
- ((647a1150-f35f-43a6-9995-57bea646eaac))
	- Word vectors
	- Word2Vec
- ((647a117a-a516-4fe5-ae82-94638ac7d9dd))
  collapsed:: true
	- Skip-gram model
		- Given a word predict its context words
		- the **cat** sat → cat, {the, sat}
	- Continuous BOW (CBOW)
		- Given context words predict the current word
		- the **cat** sat → {the, sat}, cat
	- Input
		- A word, represented as a one-hot vector over vocabulary (or the vocabulary index for memory efficiency!)
	- Hidden layer
		- One hidden layer of size vocabulary × hidden size (usually 300), linear activation function
	- Output
		- Softmax over the vocabulary to predict the correct context/target words respectively
	- Evaluation: standard approaches for word representation (see Lecture 1)
	- Pre-trained word embeddings are widely re-used in other NLP tasks, i.e. transfer learning (more in Lecture 10)
- ((647a14df-d0e7-421f-beaa-95ce1c63d85c))
	- Negative Sampling
	- Subsampling frequent words
- ((647a14f7-ebd1-4ecd-8ed5-466272642e58))
	- Approach 1: Pass BOW vectors into a series of hidden layers
	  (extending the LR model in Lecture 2)
	- Approach 2: Pass one-hot word vectors through an
	  embedding layer to obtain embeddings for each word in a
	  document which are subsequently concatenated (or
	  added/averaged) and passed through a series of hidden
	  layers
	- Approach 2 is more contemporary and usually the embedding
	  layer is pre-trained (e.g. using Word2Vec) and is not updated
	  during training
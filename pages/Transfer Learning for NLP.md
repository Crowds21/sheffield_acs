- Transfer learning: Re-use and adapt already pre-trained supervised machine learning models on a target task
- How we can re-use and neural LMs on target tasks (e.g. text classification, machine translation, question answering, etc.)
- ((647cedd0-ee95-4f93-9f2f-1c2f0da274ca))
	- A machine learning approach where models trained on a source task (or domain) are adapted to a related target task1 (or domain)
	  一种机器学习方法，其中在源任务（或领域）上训练的模型被适应到相关的目标任务1（或领域）
- ((647cedf1-39f5-48e9-9c45-750ea1fcf1d5))
	- Domain: $\mathcal{D}=\{\mathcal{X}, P(X)\}$
	- Task: $\mathcal{T}$ where $y \in \mathcal{Y}$
	- Cond. Prob. Distrib.: $P(Y \mid X)$
	- Given a source domain $\mathcal{D}_S$ and a corresponding task $T_S$, a target domain $\mathcal{D}_T$ and task $\mathcal{T}_T$, earn a new model that computes the target conditional probability distribution $P\left(Y_T \mid X_T\right)$ in $\mathcal{D}_T$ given information from $\mathcal{D}_S$ and $\mathcal{T}_S$
- ((647ceea5-8972-4f5f-835e-93c938e98b68))
	- $\mathcal{X}_S \neq \mathcal{X}_T$
		- Different feature spaces in source and target domains, e.g. documents written in different languages (cross-lingual adaptation)
	- $P\left(X_S\right) \neq P\left(X_T\right)$
		- Different marginal probability distributions in source and target domains, e.g. restaurant reviews vs electronic product reviews (domain adaptation)
	- $\mathcal{Y}_S \neq \mathcal{Y}_T$
		- Different tasks (label sets), e.g. LM as source task and sentiment analysis as target task
	- $P\left(Y_S \mid X_S\right) \neq P\left(Y_T \mid X_T\right)$
		- Different conditional probability distributions between source and target tasks, e.g. source and target documents are unbalanced regarding to their classes
- ((647ceefa-4ee3-482b-8ed1-7d4d204d6561))
- ((647cef02-fc82-4ba2-8719-9c9df57de5ae))
- ((647cef10-bec0-4d30-b061-f1aa9e4d77d8))
- ((647cef1d-b3f4-4111-895b-9b1d1b8f9edd))
- ((647cef31-7151-4e47-bc7b-8f53744c15c1))
	- ((647cef3e-7a97-4c0a-9e02-73119abd8b3a))
	- ((647cef44-4348-4556-b613-b461e311e34a))
- ((647cef53-513d-4c4f-820a-d5ace756f78f)) 适应过程：
	- 使用在语言模型（LM）中学习到的权重初始化目标任务的编码器
	- 改变网络的输出层以匹配目标任务
	- 冻结预训练的词嵌入/编码器的权重
	  Freeze the weights of the pretrained word embeddings/encoder
	- 在目标任务数据上学习输出层的权重
	  Learn the weights of the output layer on the target task data
	- 解冻预训练组件的权重并进行微调(使用非常小的学习率进行额外的训练步骤)
	  Unfreeze the weights of the pretrained components and fine-tune them 
	  (additional training steps with very small learning rate)
	- 在 ULMFiT 中，LM 编码器（LSTM）在适应之前就在目标任务数据上进行了微调
	- 这个过程基本上是一种迁移学习的策略，首先在一个大型任务（例如，语言模型）上预训练模型，然后将学习到的知识（例如，权重）迁移到目标任务上。冻结和解冻的步骤是为了在保持预训练知识的同时，让模型能够学习目标任务的特定知识。在最后的微调阶段，模型会在目标任务的数据上进行额外的训练，以进一步优化其性能。
- Transfer learning: Re-use and adapt already pre-trained supervised machine learning models on a target task
- How we can re-use and neural LMs on target tasks (e.g. text classification, machine translation, question answering, etc.)
- ((647cedd0-ee95-4f93-9f2f-1c2f0da274ca))
	- A machine learning approach where models trained on a source task (or domain) are adapted to a related target task1 (or domain)
	  一种机器学习方法，其中在源任务（或领域）上训练的模型被适应到相关的目标任务1（或领域）
- ((647cedf1-39f5-48e9-9c45-750ea1fcf1d5))
	- Domain: $\mathcal{D}=\{\mathcal{X}, P(X)\}$
	- Task: $\mathcal{T}$ where $y \in \mathcal{Y}$
	- Cond. Prob. Distrib.: $P(Y \mid X)$
	- Given a source domain $\mathcal{D}_S$ and a corresponding task $T_S$,
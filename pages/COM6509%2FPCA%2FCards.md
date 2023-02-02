- PCA
	- PCA目的是对数据空间中的进行偏转,最终找到 {{cloze 方差最大}}的方向, 方差代表数据的离散程度 [[card]]
	- 已知原数据空间中,$x$的向量为
	  id:: 63da7afa-31ef-4a0a-b0cf-a6ecdb02c498
	  collapsed:: true
	  $$
	  \mathbf{x}=\left[\begin{array}{l}
	  a \\ b
	  \end{array}\right]
	  $$
	  特征空间中对应的向量为
	  $$
	  \mathbf{y}=\left[\begin{array}{l}
	  c \\
	  d
	  \end{array}\right]=\left[\begin{array}{c}
	  \mathbf{u}_1^T \mathbf{x} \\
	  \mathbf{u}_2^T \mathbf{x}
	  \end{array}\right]
	  $$
	  对应的transformation matrix 为 
	  $$
	  \mathbf{U}^T=\left[\begin{array}{l}
	  \mathbf{u}_1^T \\
	  \mathbf{u}_2^T
	  \end{array}\right]
	  $$
	  根据 $\operatorname{Cov}=\frac{1}{N} \sum_{n=1}^N\left(y_{n i}-\mathbb{E}\left(y_i\right)\right)\left(y_{n j}-\mathbb{E}\left(y_j\right)\right)$ 
	  推导对应的矩阵表达式 [[card]]
		- 协方差特征向量矩阵
			- $$
			  C_{i j}=\frac{1}{N} \sum_{n=1}^N\left(x_{n i}-\mu_i\right)\left(x_{n j}-\mu_j\right)
			  $$
		- $$
		  \begin{aligned}
		   \operatorname{Cov}\left(y_i, y_j\right) & = \frac{1}{N} \sum_{n=1}^N\left(y_{n i}-\mathbb{E}\left(y_i\right)\right)\left(y_{n j}-\mathbb{E}\left(y_j\right)\right) \\
		  \ & =\frac{1}{N} \sum_{n=1}^N \mathbf{u}_i^T\left(\mathbf{x}_n-\boldsymbol{\mu}\right)\left(\mathbf{x}_n-\boldsymbol{\mu}\right)^T \mathbf{u}_j \\
		  \ & =\mathbf{u}_i^T \mathbf{C} \mathbf{u}_j
		  \end{aligned}
		  $$
		- $$
		  \begin{aligned}
		  y_{n i} & =\mathbf{u}_i^T \mathbf{x}_n \\
		  \mathbb{E}\left(y_i\right) & =\mathbf{u}_i^T \boldsymbol{\mu}
		  \end{aligned}
		  $$
		- $\mu$为转换之前$X$的均值, 即原本$E(x)-x$ 乘以转换函数
	- 通过Lagrange multipliers,进行第1次PCA的优化标准 [[card]]
	  card-last-interval:: -1
	  card-repeats:: 1
	  card-ease-factor:: 2.5
	  card-next-schedule:: 2023-02-03T00:00:00.000Z
	  card-last-reviewed:: 2023-02-02T15:52:11.752Z
	  card-last-score:: 1
		- $$
		  L\left(\mathbf{u}_1, \lambda_1\right)=\mathbf{u}_1^T \mathbf{C} \mathbf{u}_1+\lambda_1\left(1-\mathbf{u}_1^T \mathbf{u}_1\right)
		  $$
		- $$
		  \begin{aligned}
		  \frac{d L\left(\mathbf{u}_1, \lambda_1\right)}{d \mathbf{u}_1} & =2 \mathbf{C} \mathbf{u}_1-2 \lambda_1 \mathbf{u}_1=\mathbf{0} \\
		  \mathbf{C} \mathbf{u}_1 & =\lambda_1 \mathbf{u}_1 \\
		  \end{aligned}
		  $$
		- 对 $L(u_1,\lambda_1)$求导,导数为 0 时,即可得极值
		- 但是得到的特征向量$u_1$有多个值,需要进一步处理
	- 矩阵特征值:设 $A$ 是$n$阶方阵，如果存在数$m$和非零$n$维列向量 $x$，使得 $Ax=mx$ 成立，则称 $m$ 是矩阵A的一个特征值（characteristic value)或本征值（eigenvalue). 在 pca 中,特征向量就是最大方差的方向 , 这里 $x$ 就是Eigenvectors [[card]]
	- TODO 将一个$3\times1$的向量转换为$2\times1$的
	- 已知$\lambda_i=\mathbf{w}_i^T \mathbf{C} \mathbf{w}_i$, $\lambda_i$是 {{cloze 特征值}},$w$是 {{cloze 特征向量}},$C$是 {{cloze 协方差矩阵}} [[card]]
	  card-last-interval:: -1
	  card-repeats:: 1
	  card-ease-factor:: 2.5
	  card-next-schedule:: 2023-02-03T00:00:00.000Z
	  card-last-reviewed:: 2023-02-02T15:31:09.235Z
	  card-last-score:: 1
	- 已知协方差矩阵 
	  collapsed:: true
	  $$
	  \mathbf{C}=\left(\begin{array}{ccc}
	  4 & -2 & 0 \\
	  -2 & 1 & 1 \\
	  0 & 1 & 2
	  \end{array}\right)
	  $$
	  特征向量
	  $$
	  \mathbf{w}_1=\left(\begin{array}{c}
	  -0.872 \\
	  0.466 \\
	  0.152
	  \end{array}\right), \mathbf{w}_2=\left(\begin{array}{c}
	  -0.390 \\
	  -0.847 \\
	  0.361
	  \end{array}\right), \mathbf{w}_3=\left(\begin{array}{c}
	  0.297 \\
	  0.256 \\
	  0.920
	  \end{array}\right)
	  $$
	  求对应的特征值 [[card]]
		- $\lambda_i=\mathbf{w}_i^T \mathbf{C} \mathbf{w}_i$
		-
	- 已知 $\mathbf{x}_1=(2,3,3)^T$ , $\mathbf{x}_2=(4,1,0)^T$ ,以及对应的特征值
	  collapsed:: true
	  $\lambda_1=5.070, \lambda_2=-0.346, \lambda_3=2.278$
	  对应的特征向量为
	  $$
	  \mathbf{w}_1=\left(\begin{array}{c}
	  -0.872 \\
	  0.466 \\
	  0.152
	  \end{array}\right), \mathbf{w}_2=\left(\begin{array}{c}
	  -0.390 \\
	  -0.847 \\
	  0.361
	  \end{array}\right), \mathbf{w}_3=\left(\begin{array}{c}
	  0.297 \\
	  0.256 \\
	  0.920
	  \end{array}\right) .
	  $$
	  协方差矩阵为
	  $$
	  \mathbf{C}=\left(\begin{array}{ccc}
	  4 & -2 & 0 \\
	  -2 & 1 & 1 \\
	  0 & 1 & 2
	  \end{array}\right)
	  $$
	  使用 PCA transformation 计算转换后的两个向量 [[card]]
		- 选择$\lambda_i$最大的两个对应的$w$
		- $$
		  \mathbf{U}=\left(\begin{array}{ll}
		  \mathbf{w}_1 & \mathbf{w}_3
		  \end{array}\right)=\left(\begin{array}{cc}
		  -0.872 & 0.297 \\
		  0.466 & -0.256 \\
		  0.152 & 0.920
		  \end{array}\right)
		  $$
		- 根据转换矩阵$U$,计算$\mathbf{y}_i=\mathbf{U}^T \mathbf{x}_i$
	- TODO  (Worksheet8-3)证明...
- K-means
	- K-means 计算公式以及每一项的含义 [[card]]
		- $$
		  E_{\mathrm{KM}}=\frac{1}{2} \sum_{k=1}^K \sum_{n \in C_k}^{n_k}\left(\mathbf{x}_n-\mathbf{m}_k\right)^2
		  $$
			- K numbers of clusters
			- $m_k$ centroid of cluster k
			- $C_k$ List of data points in cluster k
			- $n_k$ Number of data points in cluster k
	- K-means步骤 [[card]]
		- 挑选一个随机的初始中心点 starting centroids
		- 重复以下步骤,直到不再产生变化
			- 将数据点分配给最近的中心点 (一次性全部分了)
			- 将中心点更新为指定数据点的平均值
			- $$
			  \mathbf{m}_k=\frac{1}{n_k} \sum_{n \in C_k} \mathbf{x}_n
			  $$
	- K-means 模型成分 [[card]]
		- Input : Data  + pre-processing
		- Model:
			- Structure/architecture: linear separation between clusters
			- Parameters: position of cluster centroids
			- Hyper-parameters: number of clusters
		- Evaluation metric: within cluster scatter
		- Optimisation: Gradient descent (back-prop) or similar
- Spectral Clustering
	- 创建 graph 的流程
		- 通过Gaussian Kernel 计算两个对之间的相似性
			- $$
			  W_{i j}=\exp \left(-\frac{\left|\mathbf{x}_i-\mathbf{x}_j\right|^2}{2 \sigma^2}\right)
			  $$
		- 创建 graph
			- a fully connected graph
				- 每个数据点都与其他数据点相连
			- K-neareast neighbour graph
				- 每个节点只与它的K个邻居相连（局部连接）。
		- Clustering
			- Graph cut / partitioning
			- 目的是进行最小化切割
	- Cutting the graph
		- 把两个相连的 graph 进行切割
		- ((63da96fc-753a-4d20-bb6b-1f18f19b8779))
		- cut 的过程就是计算各组连接之和
		- $$
		  \operatorname{cut}(A, B)=\sum_{i \in A} \sum_{j \in B} W_{i j}
		  $$
	- minimum cut
		- 并不总是最佳的选择,有时候会被异常值影响
		- ((63da977f-f8e3-433c-bb37-b5e93ab9abde))
		- 解决minimum cut的一个方法是 Normalised Cut
	- Normalised Cut
		- 计算 Normallised Cut[[card]]
		  collapsed:: true
		  card-last-interval:: -1
		  card-repeats:: 1
		  card-ease-factor:: 2.5
		  card-next-schedule:: 2023-02-03T00:00:00.000Z
		  card-last-reviewed:: 2023-02-02T16:16:18.373Z
		  card-last-score:: 1
			- 根据每组的 volumes 考虑两组之间的连通性
			- $$
			  \operatorname{Ncut}(A, B)=\frac{\operatorname{Cut}(A, B)}{\operatorname{Vol}(A)}+\frac{\operatorname{Cut}(A, B)}{\operatorname{Vol}(B)}
			  $$
			- $$
			  \operatorname{Ncut}(A, B)=\operatorname{Cut}(A, B)\left(\frac{\operatorname{Vol}(A)+\operatorname{Vol}(B)}{\operatorname{Vol}(A) \operatorname{Vol}(B)}\right)
			  $$
			- ((63da986b-9ad5-4a91-8db2-afdf85335d5b))
				- $Vol(A)$ 就是 graph A 中每个点求值后的和
				- $Vol(A)=d_1+d_2+d_3$
				- $d_1= 0.8+0.6+0.1=1.5$
				- $Cut(A,B)$是 A 和 B 之间连同的值
				- $Cut(A,B)=0.1+0.2=0.3$
		- minimise the normalised cut [[card]]
		  collapsed:: true
			- $$
			  \min _{\mathbf{x}} \operatorname{Ncut}(\mathbf{x})=\min _{\mathbf{y}} \frac{\mathbf{y}^T(\mathbf{D}-\mathbf{W}) \mathbf{y}}{\mathbf{y}^T \mathbf{D} \mathbf{y}}
			  $$
				- $x$ and $y$ are vectors indicate which cluster a data point is in.
				- Degree matrix $D_{i i}=d_i=\sum_j W_{i j}$
			- 上式可以通过求解 generalise eigenvalue 来最小化
				- $$
				  (\mathbf{D}-\mathbf{W}) \mathbf{y}=\lambda \mathbf{D y}
				  $$
				- 第二低的特征值 (和特征向量) 对应将图形一分为二所需的切割
	- Spectral Clustering模型成分
	  collapsed:: true
		- Data + pre-processing
		- Model:
			- Structure/architecture: non-linear separation between clusters
			- Parameters: (generalised eigenvectors (cluster assignment vector)
			- Hyper-parameters: number of clusters, kernel length scale
		- Evaluation metric: normalised graph cut
		- Optimisation: Eigen-decomposition (and expectation maximisation in k-
		  means)
- Discriminative 模型 和 Generative 模型
	- Discriminative 模型 和 Generative 模型 之间的区别 [[card]]
		- Discriminative
			- Optimise an explicitly defined form of the decision boundary
			- Assume some functional form for $P(y \mid \mathbf{x})$
			- Estimate parameters for this based on training data.
		- Generative
			- Define a process that could have generated the observations
			- Assume some functional form for $P(\mathbf{x} \mid y)$ and $P(y)$
			- Use Bayes’ rule to find  $P(\mathbf{x} \mid y)$
- the formula of normalization(min-max scaling, $(a,b)$ )[[card]]
  card-last-interval:: 1.81
  card-repeats:: 2
  card-ease-factor:: 2.36
  card-next-schedule:: 2023-01-26T11:43:26.768Z
  card-last-reviewed:: 2023-01-24T16:43:26.768Z
  card-last-score:: 3
	- $s_i^{\prime}=\frac{s_i-\min (s)}{\max (s)-\min (s)} \times(b-a)+a$
- the formula of standarisation [[card]]
  card-last-interval:: 1.81
  card-repeats:: 2
  card-ease-factor:: 2.36
  card-next-schedule:: 2023-01-26T11:44:15.118Z
  card-last-reviewed:: 2023-01-24T16:44:15.118Z
  card-last-score:: 3
	- $x_i^{\prime}=\frac{s_i-\mu}{\sigma}$
- 如何计算 Precision [[card]]
  card-last-interval:: 7.31
  card-repeats:: 1
  card-ease-factor:: 2.6
  card-next-schedule:: 2023-01-29T17:33:42.389Z
  card-last-reviewed:: 2023-01-22T10:33:42.389Z
  card-last-score:: 5
	- $\dfrac{TP}{TP+FP}$
	- 所有预测为 Positive 的样本中, 预测结果为 True 的
- 如何计算 Recall [[card]]
  card-last-interval:: -1
  card-repeats:: 1
  card-ease-factor:: 2.36
  card-next-schedule:: 2023-02-03T00:00:00.000Z
  card-last-reviewed:: 2023-02-02T19:24:28.607Z
  card-last-score:: 1
	- $\dfrac{TP}{TP+FN}$
	- 所有 Actual Positive 中,成功召回的
- 训练集经过 min-max scaling 后训练得到的模型,在测试时,对于测试集中的数据,也需要进行 {{cloze min-max scaling }} [[card]]
  card-last-interval:: 1.95
  card-repeats:: 2
  card-ease-factor:: 2.36
  card-next-schedule:: 2023-01-25T08:20:55.258Z
  card-last-reviewed:: 2023-01-23T10:20:55.258Z
  card-last-score:: 3
- 对于随机变量 X,Y 的联合分布函数 $P(X,Y)$ 如何求边缘质量函数 [[card]]
  card-last-interval:: 1.95
  card-repeats:: 2
  card-ease-factor:: 2.36
  card-next-schedule:: 2023-01-25T08:19:10.007Z
  card-last-reviewed:: 2023-01-23T10:19:10.008Z
  card-last-score:: 3
	- {{embed ((63320d74-5fec-42da-ba5a-194f926b17eb))}}
	- ((63bc534b-bf69-4acb-9a66-a88cf7b94ab5))
- 对于随机变量 X,Y. 已知联合分布函数 $P(X,Y)$. 如何计算协方差 $cov{X,Y}$ [[card]]
  card-last-interval:: 1.81
  card-repeats:: 2
  card-ease-factor:: 2.36
  card-next-schedule:: 2023-01-26T11:44:06.412Z
  card-last-reviewed:: 2023-01-24T16:44:06.412Z
  card-last-score:: 3
	- ((63398e51-cf75-4236-abfe-91d0018114d4))
- DONE 对于随机变量 X,Y. 已知联合分布函数 $P(X,Y)$.  如何判断随机变量 X,Y 是否线性相关 [[card]]
  card-last-score:: 3
  card-repeats:: 2
  card-next-schedule:: 2023-01-25T08:19:33.170Z
  card-last-interval:: 1.95
  card-ease-factor:: 2.36
  card-last-reviewed:: 2023-01-23T10:19:33.170Z
	- $\sigma_{X, Y}=E\{X Y\}-E\{X\} E\{Y\}$
	- 如果计算结果为 0 则随机变量 X, Y 线性相关
- 证明两个随机变量如果相互独立,则不相关 [[card]]
  card-last-interval:: 8.88
  card-repeats:: 3
  card-ease-factor:: 2.22
  card-next-schedule:: 2023-02-11T16:24:42.721Z
  card-last-reviewed:: 2023-02-02T19:24:42.721Z
  card-last-score:: 3
	- $\begin{aligned}E\{X Y\} & =\sum_{y_j} \sum_{x_i} x_i y_j P\left(x_i, y_j\right)=\sum_{y_j} \sum_{x_i} x_i y_j P\left(x_i\right)P\left(y_j\right) \\& =\left[\sum_{x_i} x_i P\left(x_i\right)\right]\left[\sum_{y_j} y_j P\left(y_j\right)\right]=E\{X\} E\{Y\}\end{aligned}$
	- $\begin{aligned}E\{X Y\} & =\int_{-\infty}^{\infty} \int_{-\infty}^{\infty} x y p(x, y) d x d y=\int_{-\infty}^{\infty} \int_{-\infty}^{\infty} x y p(x) p(y) d x d y \\& =\int_{-\infty}^{\infty} x p(x) d x \int_{-\infty}^{\infty} y p(y) d y=E\{X\} E\{Y\}\end{aligned}$
- 如何计算两个随机变量的相关系数 [[card]]
  card-last-interval:: -1
  card-repeats:: 1
  card-ease-factor:: 2.5
  card-next-schedule:: 2023-02-03T00:00:00.000Z
  card-last-reviewed:: 2023-02-02T19:24:26.598Z
  card-last-score:: 1
	- $\rho=\frac{\operatorname{Cov}(X, Y)}{\sqrt{\operatorname{Var}(X) \operatorname{Var}(Y)}}$
	- XY的协方差
	- X 和 Y 的方差
-
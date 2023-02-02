- 计算熵和信息增益的公式 [[card]]
  card-last-interval:: -1
  card-repeats:: 1
  card-ease-factor:: 2.5
  card-next-schedule:: 2023-01-25T00:00:00.000Z
  card-last-reviewed:: 2023-01-24T16:46:25.703Z
  card-last-score:: 1
	- 熵
		- ((a612d7a1-39bf-4a48-abda-9ee38a0ccaa0))
	- 信息增益
		- ((634d7ca4-5e42-496b-851c-44c0c1d900ae))
		- 后半部分可以写作 $rem = \sum_{i=1}^N p(A=i) H(S \mid A=i)$
- 已知熵为$H(S)$这里的 S 指的是什么? [[card]]
  card-last-interval:: 1.95
  card-repeats:: 1
  card-ease-factor:: 2.36
  card-next-schedule:: 2023-01-25T08:26:01.401Z
  card-last-reviewed:: 2023-01-23T10:26:01.401Z
  card-last-score:: 3
	- 指的是决策树最后的预测结果 $S=\{ s_1,s_2,s_3\}$
- 已知计算$IG(S, A)=H(S)-\operatorname{rem}(d, \mathcal{D})$ 
  card-last-interval:: 1.95
  card-repeats:: 1
  card-ease-factor:: 2.36
  card-next-schedule:: 2023-01-25T08:23:59.043Z
  card-last-reviewed:: 2023-01-23T10:23:59.043Z
  card-last-score:: 3
  计算$rem$时,$p(A=i) H(S \mid A=i)$分别指的是什么? [[card]]
	- $p(A=i)$
		- 指的是类别 $i$ 在 $A$ 中占据的比例
	- $H(S \mid A=i)=-\sum_{i=1}^n p_i \log p_i$
		- 当 $A$ 取$i$时, $p_i$就是, 当 $A=i$时,  $S=\{ s_1,s_2,s_3\}$分别是多少
	- 参考 ((63cd67a8-4b1d-4956-8f67-a53978800cff))
- Gini 系数公式 [[card]]
  card-last-interval:: -1
  card-repeats:: 1
  card-ease-factor:: 2.5
  card-next-schedule:: 2023-02-03T00:00:00.000Z
  card-last-reviewed:: 2023-02-02T12:29:43.319Z
  card-last-score:: 1
	- ((6362e08a-d392-4b8a-b285-8110f7fbe49b))
- 如何通过 Gini 系数计算Information Gain [[card]]
  card-last-interval:: -1
  card-repeats:: 1
  card-ease-factor:: 2.5
  card-next-schedule:: 2023-01-25T00:00:00.000Z
  card-last-reviewed:: 2023-01-24T16:46:39.933Z
  card-last-score:: 1
	- $$
	  IG(S, A)=G(S)-\sum_{i=1}^N p(A=i) G(S \mid A=i)
	  $$
	- 例: $I G(\text { EDUCATION } \mathcal{D})=\text { Gini }(\text { ANNUAL INCOME }, \mathcal{D})-\operatorname{rem}(\text { EDUCATION }, \mathcal{D})$
	- 与使用熵计算 $IG$公式一样,只是将熵换成 $Gini$
- 对于输出结果为连续型变量的决策树,节点的选择不使用$IG$而是 {{cloze 方差}},计算公式为? [[card]]
  card-last-interval:: -1
  card-repeats:: 1
  card-ease-factor:: 2.5
  card-next-schedule:: 2023-02-03T00:00:00.000Z
  card-last-reviewed:: 2023-02-02T12:31:20.546Z
  card-last-score:: 1
	- $\operatorname{var}(t, \mathcal{D})=\frac{\sum_{i=1}^n\left(t_i-\bar{t}\right)^2}{n-1}$
- 对于输出结果为连续型变量的决策树,如何选择特征来进行分类? [[card]]
  card-last-interval:: 1.81
  card-repeats:: 2
  card-ease-factor:: 2.36
  card-next-schedule:: 2023-01-26T11:45:48.016Z
  card-last-reviewed:: 2023-01-24T16:45:48.017Z
  card-last-score:: 3
	- 计算方差,选择方差最小的作为分类依据
- TODO WrokSheet3 1- ((63cd6cd5-8c6f-4517-884a-f4fc0555f955)) [[card]]
  card-last-interval:: -1
  card-repeats:: 1
  card-ease-factor:: 2.5
  card-next-schedule:: 2023-01-25T00:00:00.000Z
  card-last-reviewed:: 2023-01-24T16:44:53.372Z
  card-last-score:: 1
- 给定三组样本,如何生成一个随机森林 [[card]]
  card-last-interval:: -1
  card-repeats:: 1
  card-ease-factor:: 2.5
  card-next-schedule:: 2023-02-03T00:00:00.000Z
  card-last-reviewed:: 2023-02-02T12:34:00.588Z
  card-last-score:: 1
	- ((63cd6d3b-dc12-45e1-87ad-1bd8686885ce))
	- 对每个样本计算 熵和IG,最后依次确定分类依据的特征
	- 最终结果: 三个决策树
-
-
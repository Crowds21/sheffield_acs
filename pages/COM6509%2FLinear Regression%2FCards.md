-
- 矩阵运算
	- 矩阵的inner product 和 outer product [[card]]
	  collapsed:: true
	  card-last-interval:: 2.29
	  card-repeats:: 1
	  card-ease-factor:: 2.36
	  card-next-schedule:: 2023-02-05T01:16:40.551Z
	  card-last-reviewed:: 2023-02-02T19:16:40.551Z
	  card-last-score:: 3
		- Inner Product
			- $$\begin{aligned}
			  &a \cdot b=a^{\top} b=
			  &a_1 b_1+a_2 b_2+\ldots+a_N b_N
			  \end{aligned}$$
		- Outer Product
			- $$a \otimes b=a b^{\top} = \left[\begin{array}{cccc}
			  a_1 b_1 & \cdots & a_1 b_M \\
			  a_2 b_1 & \ddots & \vdots \\
			  \vdots & \ddots & \vdots  \\
			  a_N b_1 & \cdots & a_N b_N
			  \end{array}\right]$$
	- 已知矩阵$w$, $n \times m$, 矩阵$x$,$m \times 1$,矩阵$y$,$n \times 1$,将下面的式子改写为矩阵相乘的形式
	  collapsed:: true
	  card-last-interval:: -1
	  card-repeats:: 1
	  card-ease-factor:: 2.5
	  card-next-schedule:: 2023-02-03T00:00:00.000Z
	  card-last-reviewed:: 2023-02-02T19:12:03.134Z
	  card-last-score:: 1
	  $$
	  \sum_{i=1}^n \sum_{j=1}^m w_{i, j} x_j+\sum_{j=1}^m \sum_{i=1}^n y_i w_{i, j}
	  $$
	  提示: $\mathbf{1}_p=[1 \cdots 1]^{\top}$ of dimensions $p \times 1$ 
	  [[card]]
		- $$
		  \sum_{i=1}^n \sum_{j=1}^m w_{i, j} x_j+\sum_{j=1}^m \sum_{i=1}^n y_i w_{i, j}=\mathbf{1}_n^{\top} \mathbf{W} \mathbf{x}+\mathbf{y}^{\top} \mathbf{W} \mathbf{1}_m
		  $$
- [[高斯分布]]
	- [[高斯分布]]的定义 [[card]]
	  card-last-interval:: -1
	  card-repeats:: 1
	  card-ease-factor:: 2.5
	  card-next-schedule:: 2023-02-03T00:00:00.000Z
	  card-last-reviewed:: 2023-02-02T13:27:14.118Z
	  card-last-score:: 1
		- $$
		  f(x) = \frac{1}{\sigma \sqrt{2\pi }} \exp \left[-\frac{(x - \mu )^2}{2\sigma ^2} \right] , -\infty<x<+\infty 
		  $$
		- 记作$X\sim N(\mu,\sigma^2)$  ，读作 $X$服从 $N(\mu,\sigma^2)$ ，或 $X$ 服从正态分布
		- $\mu$ 为均值
		- $\sigma^2$ 为方差
	- 标准正态分布 [[card]]
	  collapsed:: true
	  card-last-interval:: -1
	  card-repeats:: 1
	  card-ease-factor:: 2.5
	  card-next-schedule:: 2023-02-03T00:00:00.000Z
	  card-last-reviewed:: 2023-02-02T19:17:54.332Z
	  card-last-score:: 1
		- 当$\mu=0,\sigma=1$ 时，正态分布就成为标准正态分布
		- $$
		  f(x) = \frac{1}{ \sqrt{2\pi }} e ^{ \left[-\frac{x^2}{2} \right] }
		  $$
	- 如果$X\sim N(\mu,\sigma^2)$ 且a与b是实数，那么 $aX+b\sim N()$ [[card]]
	  collapsed:: true
	  card-last-interval:: -1
	  card-repeats:: 1
	  card-ease-factor:: 2.5
	  card-next-schedule:: 2023-02-03T00:00:00.000Z
	  card-last-reviewed:: 2023-02-02T19:18:13.609Z
	  card-last-score:: 1
		- $aX+b\sim N(a\mu+b,(a\sigma)^2)$
	- 如果 $X \sim N\left(\mu_{X}, \sigma_{X}^{2}\right)$ 和  $Y \sim N\left(\mu_{Y}, \sigma_{Y}^{2}\right)$是统计独立的正态随机变量
	  collapsed:: true
	  card-last-interval:: 2.29
	  card-repeats:: 1
	  card-ease-factor:: 2.36
	  card-next-schedule:: 2023-02-05T01:21:49.629Z
	  card-last-reviewed:: 2023-02-02T19:21:49.629Z
	  card-last-score:: 3
	  $U=X+Y \sim N$
	  $V=X-Y \sim N$
	  [[card]]
		- 它们的和也满足正态分布 $U=X+Y \sim N\left(\mu_{X}+\mu_{Y}, \sigma_{X}^{2}+\sigma_{Y}^{2}\right)$
		- 它们的差也满足正态分布 $V=X-Y \sim N\left(\mu_{X}-\mu_{Y}, \sigma_{X}^{2}+\sigma_{Y}^{2}\right)$
		- U与V两者是相互独立的（要求X与Y的方差相等）
- Log Likelihood
	- 简介
		- 对数似然方程(log-likelihood equation)，简称“似然方程”, 对数似然方程与原似然方程同解，由于独立同分布的样本的似然函数上具有连乘积，对似然方程取对数更方便计算
	- TODO 对正态分布使用 look likelihood, 推导 normal equation [[card]]
	  card-last-interval:: -1
	  card-repeats:: 1
	  card-ease-factor:: 2.5
	  card-next-schedule:: 2023-02-03T00:00:00.000Z
	  card-last-reviewed:: 2023-02-02T17:39:06.070Z
	  card-last-score:: 1
		- $$
		  f(x) = \frac{1}{\sigma \sqrt{2\pi }} \exp \left[-\frac{(x - \mu )^2}{2\sigma ^2} \right] , -\infty<x<+\infty 
		  $$
		- 贝叶斯中的 Likelihood
		  $$
		  \mathcal{L}\left(\omega, \sigma^2\right)=\prod_{i=1}^N N\left(y \mid x_i^{\top} \omega, \sigma^2\right)
		  $$
			- $$
			  \mathcal{L}\left(\omega, \sigma^2\right)=\prod_{i=1}^N\frac{1}{\sigma \sqrt{2\pi }} \exp \left[-\frac{(y_i - x_i^T \omega )^2}{2\sigma ^2} \right] 
			  $$
			- $N$ 服从正太分布
			- $\omega$ 参数矩阵
			- $\sigma^2$ 方差
		- 通过 log Likelihood 处理后,得到
			- $\log \mathcal{L}\left(\omega, \sigma^2\right)=\sum_{i=1}^{N}\log \frac{1}{\sigma \sqrt{2\pi }}\exp \left[-\frac{(y_i - x_i^T \omega )^2}{2\sigma ^2} \right]$
			- $\sum_{i=1}^{N}-\log \frac{1}{\sigma \sqrt{2\pi }} \exp \left[-\frac{(y_i - x_i^T \omega )^2}{2\sigma ^2} \right]$
			- $$-N\log\sigma\sqrt{2\pi} - \sum_{i=1}^{N}\frac{(y_i - x_i^T \omega )^2}{2\sigma ^2}$$
		- 将上述结果转换为矩阵的形式
			- id:: 63daed33-814b-4d61-82dd-efd9d66ddd3a
			  $$
			  -N\log\sigma\sqrt{2\pi} - \frac{1}{2\sigma ^2}(y-X\omega)^T(y-X\omega)
			  $$
			- 上式类似error function
		- 对上述结果进行求导$\dfrac{dy}{d \omega}$
			- 令$x^Ty-x\omega x^T=0$
			- $x^Ty=x\omega x^T$
			- $\left(x^{\top} x\right)^{-1} x^{\top} y=\omega$
	- TODO 对于下式求$\dfrac{dy}{d\sigma}$,并给出关于$\sigma^2$的等式
	  card-last-interval:: -1
	  card-repeats:: 1
	  card-ease-factor:: 2.5
	  card-next-schedule:: 2023-02-03T00:00:00.000Z
	  card-last-reviewed:: 2023-02-02T13:24:21.543Z
	  card-last-score:: 1
	  ((63daed33-814b-4d61-82dd-efd9d66ddd3a)) [[card]]
		- 最终可得 $\sigma^2=\frac{1}{N}(\mathbf{y}-\mathbf{X} \mathbf{w})^{\top}(\mathbf{y}-\mathbf{X} \mathbf{w})$
		- 首先需要根据符合正态分布的对数似然函数求导,即上式,然后对该式再求导..
	- l2 正则化,并化简整个式子,来通过 inner product 和 differentiate 整个式子,来表示最后一项 [[card]]
	  collapsed:: true
	  card-last-interval:: -1
	  card-repeats:: 0
	  card-ease-factor:: 2.5
	  card-next-schedule:: nil
	  card-last-reviewed:: nil
	  card-last-score:: nil
		- $$
		  E=\frac{1}{N}\left(\boldsymbol{y}-\boldsymbol{X} \boldsymbol{w}_*\right)^{\top}\left(\boldsymbol{y}-\boldsymbol{X} \boldsymbol{w}_*\right)+\frac{\lambda}{2}\|\boldsymbol{w}\|_2^2
		  $$
		- $\|\boldsymbol{w}\|_2^2$ L2 范数,$\omega$元素平方和的平方根 $\left(\sqrt{\sum\omega_i^2}\right)^2$,可以看做是 $\lambda\|\boldsymbol{w}\|_2^2=\lambda \boldsymbol{w}^{\top} \boldsymbol{w}$
		-
		- $\frac{\partial E}{\partial \boldsymbol{w}}=\frac{2}{N}\left(\boldsymbol{X}^{\top} \boldsymbol{X}\right) \boldsymbol{w}-\frac{2}{N} \boldsymbol{X}^{\top} \boldsymbol{y}+2 \frac{\lambda}{2} \boldsymbol{w}$
		- $0=\left(\frac{1}{N}\left(\boldsymbol{X}^{\top} \boldsymbol{X}\right)+\frac{\lambda}{2} \boldsymbol{I}\right) \boldsymbol{w}-\frac{1}{N} \boldsymbol{X}^{\top} \boldsymbol{y}$
		- $\left(\boldsymbol{X}^{\top} \boldsymbol{X}+\frac{\lambda}{2} N \boldsymbol{I}\right) \boldsymbol{w}=\boldsymbol{X}^{\top} \boldsymbol{y}$
		- $\boldsymbol{w}_*=\left(\boldsymbol{X}^{\top} \boldsymbol{X}+\frac{\lambda N}{2} \boldsymbol{I}\right)^{-1} \boldsymbol{X}^{\top} \boldsymbol{y}$
		-
	- 对于 $E(m, c)=\sum_{i=1}^n r_i\left(y_i-f\left(x_i\right)\right)^2=\sum_{i=1}^n r_i\left(y_i-m x_i-c\right)^2$,假设 c=1, 求两次梯度下降,设置初始 m 为 0. 两个样本为 $\left(r_1, x_1, y_1\right)=\left(1, \frac{1}{3}, \frac{1}{2}\right)$ , $\left(r_2, x_2, y_2\right)=\left(\frac{1}{2},-3, \frac{5}{2}\right)$ [[card]]
		- $m_{k+1}=m_k - \alpha \dfrac{d}{dm}E(m)$, $\alpha$为学习率
		- 初始$m_0=0$ 然后带如样本求$m_1$
		- 根据$m_1$再求
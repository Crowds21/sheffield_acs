public:: true
alias:: 高斯分布,正态分布,normal distribution

- 正态分布（英语：normal distribution）又名高斯分布（英语：Gaussian distribution），是一个非常常见的连续概率分布。
- 一维正态分布定义
	- 若随机变量$X$服从一个位置参数为$\mu$、尺度参数为 $\sigma$ 的概率分布，且其[[概率密度函数]]函数为
	  id:: 62d959ce-5a6d-4726-8c7d-088d3870d788
		- $$
		  f(x) = \frac{1}{\sigma \sqrt{2\pi }} \exp \left[-\frac{(x - \mu )^2}{2\sigma ^2} \right] , -\infty<x<+\infty 
		  $$
			- $exp(x) =e^x$
	- 则这个随机变量就称为正态随机变量，正态随机变量服从的分布就称为正态分布，记作$X\sim N(\mu,\sigma^2)$  ，读作 $X$服从 $N(\mu,\sigma^2)$ ，或 $X$ 服从正态分布。
		- $\mu$ 为均值
		- $\sigma^2$ 为方差
- 标准正态分布
  id:: 62d959ce-dbef-45b7-a26e-c2fb7c3bf951
	- 当$\mu=0,\sigma=1$ 时，正态分布就成为标准正态分布
		- $$
		  f(x) = \frac{1}{ \sqrt{2\pi }} e ^{ \left[-\frac{x^2}{2} \right] }
		  $$
- 正态分布的一些性质
	- 如果$X\sim N(\mu,\sigma^2)$ 且a与b是实数，那么 $aX+b\sim N(a\mu+b,(a\sigma)^2)$
	- 如果 $X \sim N\left(\mu_{X}, \sigma_{X}^{2}\right)$ 和  $Y \sim N\left(\mu_{Y}, \sigma_{Y}^{2}\right)$是统计独立的正态随机变量，那么：
		- 它们的和也满足正态分布 $U=X+Y \sim N\left(\mu_{X}+\mu_{Y}, \sigma_{X}^{2}+\sigma_{Y}^{2}\right)$
		- 它们的差也满足正态分布 $V=X-Y \sim N\left(\mu_{X}-\mu_{Y}, \sigma_{X}^{2}+\sigma_{Y}^{2}\right)$
		- U与V两者是相互独立的。（要求X与Y的方差相等）。
	- 如果 $X \sim N\left(0, \sigma_{X}^{2}\right)$ 和 $Y \sim N\left(0, \sigma_{Y}^{2}\right)$ 是独立正态随机变量, 那么:
		- 它们的积XY服从概率密度函数为p的分布
			- $p(z)=\frac{1}{\pi \sigma_{X} \sigma_{Y}} K_{0}\left(\frac{|z|}{\sigma_{X} \sigma_{Y}}\right)$, 其中 $K_{0}$ 是修正贝塞尔函数 (modified Bessel function)
		- 它们的比符合柯西分布, 满足 $X / Y \sim \operatorname{Cauchy}\left(0, \sigma_{X} / \sigma_{Y}\right)$.
	- 如果 $X_{1}, \cdots, X_{n}$ 为独立标准正态随机变量, 那么 $X_{1}^{2}+\cdots+X_{n}^{2}$ 服从自由度为 $n$ 的卡方分布。
- 正态分布的图像特征
	- 集中性：正态曲线的高峰位于正中央，即均数所在的位置。
	- 对称性：正态曲线以均数为中心，左右对称，曲线两端永远不与横轴相交。
	- 均匀变动性：正态曲线由均数所在处开始，分别向左右两侧逐渐均匀下降。
	- 曲线与横轴间的面积总等于1，相当于概率密度函数的函数从正无穷到负无穷积分的概率为1。即频率的总和为100%。
	- 关于 $\mu$ 对称, 并在 $\mu$ 处取最大值, 在正 (负) 无穷远处取值为 0 , 在 $\mu \pm \sigma$ 处有拐点, 形状呈现中间高两边低, 正态分布的概率密 度函数曲线呈钟形, 因此人们又经常称之为钟形曲线。
- 正态分布的参数性质
	- $\mu$是正态分布的位置参数，描述正态分布的集中趋势位置。
		- 概率规律为取与$\mu$邻近的值的概率大，而取离$\mu$越远的值的概率越小。正态分布以X=$\mu$为对称轴，左右完全对称。正态分布的期望、均数、中位数、众数相同，均等于$\mu$。
	- $\sigma$描述正态分布资料数据分布的离散程度
		- $\sigma$越大，数据分布越分散，$\sigma$越小，数据分布越集中。也称为是正态分布的形状参数，$\sigma$越大，曲线越扁平，反之，$\sigma$越小，曲线越瘦高。
- 多维正态分布定义
	- 当 $\mu$ 维随机向量具有类似的概率规律时，称此随机向量遵从多维正态分布
- 二维正态分布定义
	- 满足下述的概率密度分布的随机变量分布叫做二维正态分布
	- $$
	  f(x, y)=\left(2 \pi \sigma_{1} \sigma_{2} \sqrt{1-\rho^{2}}\right)^{-1} \exp \left[-\frac{1}{2\left(1-\rho^{2}\right)}\left(\frac{\left(x-\mu_{1}\right)^{2}}{\sigma_{1}^{2}}-\frac{2 \rho\left(x-\mu_{1}\right)\left(y-\mu_{2}\right)}{\sigma_{1} \sigma_{2}}+\frac{\left(y-\mu_{2}\right)^{2}}{\sigma_{2}^{2}}\right)\right]
	  $$
	- 其中 $\mu_{1}, \mu_{2}, \sigma_{1}, \sigma_{2}, \rho$ 都是常数, 我们称 $\left(X_{1}, X_{2}\right)$ 服从参数为 $\mu_{1}, \mu_{2}, \sigma_{1}, \sigma_{2}, \rho$ 的二维正态分布, 常把这个分布记作 $N\left(\mu_{1}, \mu_{2}, \sigma_{1}^{2}, \sigma_{2}^{2}, \rho\right)$ ) 。
	- $\mu_{1}, \mu_{2}, \sigma_{1}, \sigma_{2}, \rho$ 的范围分别为 $-\infty<\mu_{1}<+\infty ;-\infty<\mu_{2}<+\infty ;-1<\rho<1$ $\sigma_{1}>0 ; \sigma_{2}>0$ 。这个函数在三维空间中的图像是一个椭圆切面的钟倒扣在 $O x_{1} x_{2}$ 平面上, 其中心在 $\left(\mu_{1}, \mu_{2}\right)$ 点。
- 二维正态分布参数性质
	- $\rho$刻画了两个分量 $X_1,X_2$的关系, 为0时表示两个变量不相关（也称相互独立）；ρ的取值区间在0到1之间，如果P=1，则Y=aX+b成立。$\rho$ 值就是接受原假设是出错的概率
	-
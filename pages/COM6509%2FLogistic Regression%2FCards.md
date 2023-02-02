- 公式
  collapsed:: true
	- id:: 63daa9fa-c609-4474-8907-e9ac45f48a00
	  $$
	  \begin{aligned}
	  & y_1=f_1\left(x_1, x_2, x_3\right)=x_1 x_3+\log \left(x_2+x_1\right) \times \exp \left(-x_3\right), \\
	  & y_2=f_2\left(x_1, x_2, x_3\right)=\exp \left(-x_2\right)+\cos \left(x_1 x_3\right) .
	  \end{aligned}
	  $$
- 逻辑回归
	- 根据$\log \left(\frac{\pi}{1-\pi}\right)=\mathbf{w}^T \mathbf{x}$ 推导 Sigmoid 函数 [[card]]
	  card-last-interval:: -1
	  card-repeats:: 1
	  card-ease-factor:: 2.5
	  card-next-schedule:: 2023-02-03T00:00:00.000Z
	  card-last-reviewed:: 2023-02-02T13:12:00.222Z
	  card-last-score:: 1
		- 右边变成 exp{WX}
	- $P(\mathbf{x})=\frac{1}{1+\exp \left(-\mathbf{w}^T \mathbf{x}\right)}$的计算结果就代表  {{cloze 结果为1 的概率}} [[card]]
	- TODO (worksheet6-3)推导逻辑回归的代价函数 $\sum_{i=1}^N\left(y_i \log (\pi)+\left(1-y_i\right) \log (1-\pi)\right)$ [[card]]
	  card-last-interval:: -1
	  card-repeats:: 1
	  card-ease-factor:: 2.5
	  card-next-schedule:: 2023-02-03T00:00:00.000Z
	  card-last-reviewed:: 2023-02-02T13:24:31.584Z
	  card-last-score:: 1
	-
- Jacobain
	- 使用using manual differentiation的方法.给定以下函数, 求 Jacobain 矩阵 
	  collapsed:: true
	  ((63daa9fa-c609-4474-8907-e9ac45f48a00))
	  求在点$\left(x_1=3, x_2=5, x_3=1\right)$的Jacobain矩阵 [[card]]
		- $$
		  \mathbf{J}=\left[\begin{array}{l}
		  \frac{\partial f_1}{\partial x_1}, \frac{\partial f_1}{\partial x_2}, \frac{\partial f_1}{\partial x_3} \\
		  \frac{\partial f_2}{\partial x_1}, \frac{\partial f_2}{\partial x_2}, \frac{\partial f_2}{\partial x_3}
		  \end{array}\right]
		  $$
		- 求得第一行
			- $$
			  \begin{aligned}
			  & \frac{\partial f_1}{\partial x_1}=x_3+\frac{\exp \left(-x_3\right)}{x_2+x_1} \\
			  & \frac{\partial f_1}{\partial x_2}=\frac{\exp \left(-x_3\right)}{x_2+x_1} \\
			  & \frac{\partial f_1}{\partial x_3}=x_1-\log \left(x_2+x_1\right) \exp \left(-x_3\right)
			  \end{aligned}
			  $$
		- 第二行
			- $$
			  \begin{aligned}
			  & \frac{\partial f_2}{\partial x_1}=-x_3 \sin \left(x_1 x_3\right) \\
			  & \frac{\partial f_2}{\partial x_2}=-\exp \left(-x_2\right) \\
			  & \frac{\partial f_2}{\partial x_3}=-x_1 \sin \left(x_1 x_3\right)
			  \end{aligned}
			  $$
		- 最终结果
			- $$
			  \mathbf{J}\left(x_1=3, x_2=5, x_3=1\right)=\left[\begin{array}{ccc}
			  1.0459849301 & 0.0459849301 & 2.2350162077 \\
			  -0.1411200081 & -0.006737947 & -0.4233600242
			  \end{array}\right]
			  $$
- Evaluation Trace
	- Evaluation Trace 数学符号 [[card]]
		- $\mathbf{y}=\mathbf{f}\left(x_1, \ldots, x_n\right)$ 表示 n 个输入, m 个输出
		- Input variables
			- $v_{i-n}=x_i \text { with } i=1, \ldots, n$
		- Intermediate variables
			- $v_i \text { with } i=1, \ldots, l$
		- Output Variables
			- $y_i=v_{l+i} \text { with } i=1, \ldots, m$
- Computational graph
	- 画出下式的计算图 [[card]] 
	  ((63daa9fa-c609-4474-8907-e9ac45f48a00))
		- 画的时候要两个一起画
		- ![](https://cdn.mathpix.com/snip/images/J5LbccB8_dcVp6XFM4iQYBP7hpKyftp3O0-vnlMESaE.original.fullsize.png)
- Forward accumulation mode
	- Forward accumulation mode 简介
	  collapsed:: true
		- 计算 f w.r.t $x_k$的导数,每一个中间变量$v_i$都有一个导数
			- w.r.t 关于, 提及..
		- $$
		  \dot{v}_i=\frac{\partial v_i}{\partial x_j}
		  $$
		- Essentially, this is just implementing the chain rule:
		- $$
		  \frac{d y}{d x}=\frac{d y}{d u} \frac{d u}{d z} \frac{d z}{d x}
		  $$
	- 使用以下计算图计算函数的 Jacobain 矩阵 [[card]] 
	  ((63daa9fa-c609-4474-8907-e9ac45f48a00))
	  ![](https://cdn.mathpix.com/snip/images/J5LbccB8_dcVp6XFM4iQYBP7hpKyftp3O0-vnlMESaE.original.fullsize.png) [[card]]
		- 通过正向传播得下表
		- $$
		  \begin{array}{|l|l|}
		  \hline \text { Forward primal trace } & \text { Forward tangent trace } \\
		  \hline v_{-2}=x_1 & \dot{v}_{-2}=\dot{x}_1 \\
		  v_{-1}=x_2 & \dot{v}_{-1}=\dot{x}_2 \\
		  v_0=x_3 & \dot{v}_0=\dot{x}_3 \\
		  \hline v_1=v_{-2} v_0 & \dot{v}_1=v_0 \dot{v}_{-2}+v_{-2} \dot{v}_0 \\
		  v_2=v_{-2}+v_{-1} & \dot{v}_2=\dot{v}_{-2}+\dot{v}_{-1} \\
		  v_3=\exp \left(-v_0\right) & \dot{v}_3=-\exp \left(-v_0\right) \dot{v}_0=-v_3 \dot{v}_0 \\
		  v_4=\exp \left(-v_{-1}\right) & \dot{v}_4=-\exp \left(-v_{-1}\right) \dot{v}_{-1}=-v_4 \dot{v}_{-1} \\
		  v_5=\cos \left(v_1\right) & \dot{v}_5=-\sin \left(v_1\right) \dot{v}_1 \\
		  v_6=\log \left(v_2\right) & \dot{v}_6=\dot{v}_2 / v_2 \\
		  v_7=v_3 v_6 & \dot{v}_7=v_6 \dot{v}_3+\dot{v}_6 v_3 \\
		  v_8=v_1+v_7 & \dot{v}_8=\dot{v}_1+\dot{v}_7 \\
		  v_9=v_4+v_5 & \dot{v}_8=\dot{v}_4+\dot{v}_5 \\
		  \hline y_1=v_8 & \dot{y}_1=\dot{v}_8 \\
		  y_2=v_9 & \dot{y}_2=\dot{v}_9 \\
		  \hline
		  \end{array}
		  $$
		- 根据上表,可以计算 Jacobin 矩阵
		- $$
		  \begin{array}{|l|l|l|l|}
		  \hline \text { Forward primal trace } & \text { Value } & \text { Forward tangent trace } & \text { Value } \\
		  \hline v_{-2}=x_1 & =3 & \dot{v}_{-2}=\dot{x}_1 & =1 \\
		  v_{-1}=x_2 & =5 & \dot{v}_{-1}=\dot{x}_2 & =0 \\
		  v_0=x_3 & =1 & \dot{v}_0=\dot{x}_3 & =0 \\
		  \hline v_1=v_{-2} v_0 & =3 & \dot{v}_1=v_0 \dot{v}_{-2}+v_{-2} \dot{v}_0 & =1 \\
		  v_2=v_{-2}+v_{-1} & =8 & \dot{v}_2=\dot{v}_{-2}+\dot{v}_{-1} & =1 \\
		  v_3=\exp \left(-v_0\right) & =0.367 & \dot{v}_3=-\exp \left(-v_0\right) \dot{v}_0=-v_3 \dot{v}_0 & =0 \\
		  v_4=\exp \left(-v_{-1}\right) & =0.006 & \dot{v}_4=-\exp \left(-v_{-1}\right) \dot{v}_{-1} & =-0.1411 \\
		  v_5=\cos \left(v_1\right) & =-0.989 & \dot{v}_5=-\sin \left(v_1\right) \dot{v}_1 & =0 \\
		  v_6=\log \left(v_2\right) & =2.079 & \dot{v}_6=\dot{v}_2 / v_2 & =0.125 \\
		  v_7=v_3 v_6 & =0.765 & \dot{v}_7=v_6 \dot{v}_3+\dot{v}_6 v_3 & =0.0459 \\
		  v_8=v_1+v_7 & =3.765 & \dot{v}_8=\dot{v}_1+\dot{v}_7 & =1.0459 \\
		  v_9=v_4+v_5 & =-0.983 & \dot{v}_8=\dot{v}_4+\dot{v}_5 & =-0.1411 \\
		  \hline y_1=v_7 & =3.765 & \dot{y}_1=\dot{v}_7 & =1.0459 \\
		  y_2=v_8 & =-0.983 & \dot{y}_2=\dot{v}_8 & =-0.1411 \\
		  \hline
		  \end{array}
		  $$
			- Value and derivatives for $j = 1$ giving $dy1/dx1$ and $dy2/dx1$ when $x1 = 3, x2 = 5, x3 = 1$
			- 上表是对$\dfrac{dy1}{dx1}$ 和 $\dfrac{dy2}{dx1}$的求偏导结果 ,$\dot{v}_{-2}=\dot{x}_1$ 可以看做是 $\dfrac{dx_1}{dx_1}$因此结果为 1
			- 如果想要求$\dfrac{dy1}{dx2}$ 和 $\dfrac{dy2}{dx2}$那么此时x1,x2,x3 对应的结果分别为 $0,1,0$
		- 最终的两个结果代表 Jacobain 中的一列
		- Ellis 的回复
		  collapsed:: true
			- Yes, you are right. They are set to those values because we are finding the derivatives for a specific input. Since there are three inputs there will be three derivatives per output that we need to find. In the solutions, I give the results for the derivative with respect to the first input x_1. When calculating the derivatives of all the intermediate variables, we can do this in a general manner as they only depend on the previous intermediate variable. Only v_-2, v_-1 and v_0 depend on the inputs (as they are the inputs re-assigned to those variables). Therefore depending on which input we want to find the derivative with respect to it changes the values of v̇-2, v̇-1 and v̇0.
			- Let's consider finding the derivative with respect to x_1 first.  When we come to v_-2, v_-1 and v_0  then we should find that v̇-2 = d x_1/ dx_1 =1, while v̇-1 = d x_2 / dx_1 = 0 and v̇0 = dx_3 / dx_1 = 0. Similarly if we want to find the derivative with respect to x_2 then as a said before all the derivatives of the intermediate variables are the same and only v̇-2, v̇-1 and v̇0 ( it should 0,1,0 respectively this time). The same happens when we do x_3.
			- What this means is that we can use the forward tangent trace as a function to calculate the derivative, all we need to do is specify which input we want to find the derivatives for by setting the inputs (v̇-2, v̇-1 and v̇0) to the corresponding 1 or 0 to get the corresponding derivative.
			- Backwards mode is similar but in that case we choose which output we are trying to find the derivative for instead of the input.
- AD reverse mode
  collapsed:: true
	- AD reverse mode简介
		- 根据输出反向传播求导, 通过计算中间变量的 adjoints 来完成的
		- adjoints : $\bar{v}_i=\frac{\partial y_j}{\partial v_i}$ 代表输出$y_i$对变量$v_i$的敏感度
		- AD在 reverse 模式有两个阶段
			- 通过 forward step 来计算变量$v_i$然后将相关依赖存储到计算图中
			- 在 reverse step, adjoints被用来计算导数,从输出开始最后返回到输入
	- 通过 AD reverse mode 计算该计算图的 Jacobin 矩阵 [[card]]
	  ![](https://cdn.mathpix.com/snip/images/J5LbccB8_dcVp6XFM4iQYBP7hpKyftp3O0-vnlMESaE.original.fullsize.png){:height 286, :width 503}
		- adjoints : $\bar{v}_i=\frac{\partial y_j}{\partial v_i}$. 输出变量的 adjoints就等于最终输出的导数,即
		- $$
		  \begin{aligned}
		  & \bar{v}_9=\frac{\partial y_j}{\partial v_9}=\bar{y}_2 \\
		  & \bar{v}_8=\frac{\partial y_j}{\partial v_8}=\bar{y}_1
		  \end{aligned}
		  $$
		- 继续向前传播,根据链式求导法则可得
		- $$
		  \begin{aligned}
		  & \bar{v}_7=\frac{\partial y_j}{\partial v_7}=\frac{\partial y_j}{\partial v_8} \frac{\partial v_8}{\partial v_7}=\bar{v}_8 \frac{\partial}{\partial v_7}\left(v_1+v_7\right)=\bar{v}_8 \\
		  & \bar{v}_6=\frac{\partial y_j}{\partial v_6}=\frac{\partial y_j}{\partial v_7} \frac{\partial v_7}{\partial v_6}=\bar{v}_7 \frac{\partial}{\partial v_6}\left(v_6 v_3\right)=\bar{v}_7 v_3 \\
		  & \bar{v}_5=\frac{\partial y_j}{\partial v_5}=\frac{\partial y_j}{\partial v_9} \frac{\partial v_9}{\partial v_5}=\bar{v}_9 \\
		  & \bar{v}_4=\frac{\partial y_j}{\partial v_4}=\frac{\partial y_j}{\partial v_9} \frac{\partial v_9}{\partial v_4}=\bar{v}_9 \\
		  & \bar{v}_3=\frac{\partial y_j}{\partial v_3}=\frac{\partial y_j}{\partial v_7} \frac{\partial v_7}{\partial v_3}=\bar{v}_7 v_6 \\
		  & \bar{v}_2=\frac{\partial y_j}{\partial v_2}=\frac{\partial y_j}{\partial v_6} \frac{\partial v_6}{\partial v_2}=\frac{\bar{v}_6}{v_2}
		  \end{aligned}
		  $$
		- 对于$v_1, v_0, v_{−1} , v_{−2}$每次都依赖两个节点
		- $$
		  \begin{aligned}
		  \bar{v}_1 & =\frac{\partial y_j}{\partial v_1}=\frac{\partial y_j}{\partial v_5} \frac{\partial v_5}{\partial v_1}+\frac{\partial y_j}{\partial v_8} \frac{\partial v_8}{\partial v_1} \\
		  & =-\sin \left(v_1\right) \bar{v}_5+\bar{v}_8 \\
		  \bar{v}_0 & =\frac{\partial y_j}{\partial v_0}=\frac{\partial y_j}{\partial v_1} \frac{\partial v_1}{\partial v_0}+\frac{\partial y_j}{\partial v_3} \frac{\partial v_3}{\partial v_0} \\
		  & =\bar{v}_1 v_{-2}-\exp \left(-v_0\right) \bar{v}_3 \\
		  \bar{v}_{-1} & =\frac{\partial y_j}{\partial v_{-1}}=\frac{\partial y_j}{\partial v_2} \frac{\partial v_2}{\partial v_{-1}}+\frac{\partial y_j}{\partial v_4} \frac{\partial v_4}{\partial v_{-1}} \\
		  & =\bar{v}_2-\exp \left(-v_{-1}\right) \bar{v}_4 \\
		  \bar{v}_{-2} & =\frac{\partial y_j}{\partial v_{-2}}=\frac{\partial y_j}{\partial v_1} \frac{\partial v_1}{\partial v_{-2}}+\frac{\partial y_j}{\partial v_2} \frac{\partial v_2}{\partial v_{-2}} \\
		  & =\bar{v}_1 v_0+\bar{v}_2
		  \end{aligned}
		  $$
		- 通过反向模式,带入数值后,每次我们都能够得到 Jacobain 矩阵的一行,$\left(\partial y_1 / \partial x_1, \partial y_1 / \partial x_2, \partial y_1 / \partial x_3\right)$
		- 假设 $\bar{y}_1=1$, $\bar{y}_2=0$,$(j=1)$, 对应的 adjoints 为
			- $$
			  \begin{aligned}
			  \bar{v}_9 & =\bar{y}_2=0 \\
			  \bar{v}_8 & =\bar{y}_1=1 \\
			  \bar{v}_7 & =\bar{v}_8=1 \\
			  \bar{v}_6 & =\bar{v}_7 v_3=0.367 \\
			  \bar{v}_5 & =\bar{v}_9=0 \\
			  \bar{v}_4 & =\bar{v}_9=0 \\
			  \bar{v}_3 & =\bar{v}_7 v_6=2.079 \\
			  \bar{v}_2 & =\bar{v}_6 \frac{1}{v_2}=0.0459 \\
			  \bar{v}_1 & =-\sin \left(v_1\right) \bar{v}_5+\bar{v}_8=1 \\
			  \bar{v}_0 & =\bar{v}_1 v_{-2}-\exp \left(-v_0\right) \bar{v}_3=2.235 \\
			  \bar{v}_{-1} & =\bar{v}_2-\exp \left(-v_{-1}\right) \bar{v}_4=0.0459 \\
			  \bar{v}_{-2} & =\bar{v}_1 v_0+\bar{v}_2=1.0459
			  \end{aligned}
			  $$
			- 最后三个结果代表Jacobain 的一行
-
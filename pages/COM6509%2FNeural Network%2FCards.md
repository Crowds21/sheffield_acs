-
- Neural Networks
	- TODO  (worksheet7-1)对于神经网络,求最终表达式 [[card]]
- CNN
	- 根据输入和卷积核,求输出结果 
	  $$
	  x=\left[\begin{array}{lllll}
	  1 & 1 & 1 & 0 & 0 \\
	  0 & 1 & 1 & 1 & 0 \\
	  0 & 0 & 1 & 1 & 1 \\
	  0 & 1 & 1 & 1 & 0 \\
	  1 & 1 & 1 & 0 & 0
	  \end{array}\right]
	  $$
	  卷积核为 
	  $$
	  W=\left[\begin{array}{lll}
	  1 & 0 & 0 \\
	  0 & 1 & 0 \\
	  0 & 0 & 1
	  \end{array}\right]
	  $$
	  [[card]]
		- 降维结果为
		- $$
		  y=\left[\begin{array}{lll}
		  3 & 3 & 3 \\
		  1 & 3 & 2 \\
		  2 & 1 & 2
		  \end{array}\right]
		  $$
		- 根据卷积求覆盖的矩阵的元素和
	- CNN 根据输入通道,步长等信息,计算输出通道 [[card]]
		- $$
		  O=\frac{I+2 P-F}{S}+1
		  $$
		- $O$ 输出通道
		- $I$ 输入通道
		- $P$ Padding
		- $S$ Stride 步长
		- $F$ filter size
	- 已知 512 × 512 RGB colour image, apply 100 5 × 5 filters with a stride of 7 and a padding of 2. 求该层共有多少 parameters [[card]]
		- (==Filter width== x ==filter height== x ==number of channels in previous layer== + 1) x ==number of output channels==
		- $(5 \times 5 \times 3 +1) \times 100 = 7600$
-
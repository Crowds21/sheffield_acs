- The source code analysis process
  collapsed:: true
	- Parsing from source text into abstract syntax tree.
	- Decompilation, reflection, byte-code analysis.
	- Dependence graphs, call graphs, def-use chains, ..
	- Metrics, slices, dead code, dependence relations, ...
- Two levels of analysis
  collapsed:: true
	- Function-level analysis
		- Examine control and data-flow within a function.
		- Useful for identifying information-flow vulnerabilities.
	- System-level analysis
		- More useful for obtaining a high-level overview
- ((63ea48b7-c559-45f5-8904-852dc1699b3e))
	- Control Flow Graph
	  collapsed:: true
		- <img src="https://www.plantuml.com/plantuml/png/HOqn3e9044NxFSMKIpR6Vf4hq9ZOBpZ09Ej2PWTKAi_0VJoEXRTm8L6RNxoy_pz05CUYgD4JCZNta_CZnWoamw3ihN9Su9IO4mJzVYolvvBbYd509ygICRcoTS-CjL0Vm1GmRGkmWxNyLU7QaKSDTAYmfUI1nz1AbodBA2E7pJRwFxMFT1aypaUQCJsYZmW_kNHbGk5CpPhg0m00" />
		  collapsed:: true
		  {{renderer :plantuml_rukfkaee}}
			- ```plantuml 
			  start
			  if(verifyValues) then
			  :xbar=evaluate (递归);
			  repeat
			  :i++;
			  :correction += values - xbar;
			  repeat while( i<begin + length)
			  :return xbar+(correction/simplezSize);
			  else 
			  :return NaN;
			  endif
			  end
			  ```
	- Post-dominates and control dependence
	  collapsed:: true
		- Does node 7 post-dominate node 3?
		  Does node 8 post-dominate node 7?
		  What is the immediate post-dominator for node 7? 
		  Draw out the Control Dependence tree for this CFG.
		  ((63ea3b4f-b5d2-4338-8ae1-e737a60bdc23)) [[card]]
			- 从 3 到出口的每一条路径都经过了 7 
			  node 7 post-dominate node3
			- 从 node7 到 exit 不是一定会经过 node 8 
			  node 8 not post-dominate node7
			- 距离 node7 最近的 post-dominate 是 node 9
			- ((63ea3e06-d244-4f3b-bdb7-1cbd5bb98336))
				- 2 决定了 3 是否会被执行,
				  所以node 3 以及后面的所有节点,都有 control dependence
				- 2 对 3 有  control dependence
				- node2 同样对 node 10 有 control dependence
				- ~~node 1 是所有 node的 control dependence~~ 2 一定会被 1 执行,所以不是 control dependece
			-
	- Data Flow
	  collapsed:: true
		- A “define-use” relationship exists between statements $A$ and $B$ for variable $v$
		- 画出下图代码的 data flow [[card]]
		  ((63ea4204-282d-4ecb-974e-59576639ac29))
			- ((63ea422d-35fa-4da3-987d-237633cf2bc9))
			- put it all together , we can get  program dependence graph
				- ((63ea424b-3729-40a8-9afa-26e98523d969))
	- Code Slicing
	  collapsed:: true
		- A slice is a way of eliminating statements that are irrelevant to a slicing criterion(切片标准).
		- A slicing criterion consists of a statement and a set of variables at that statement.
		- A forward slice is computed by identifying all outgoing paths from the criterion node in the PDG.
		- 好像大概意思是,只把相关的代码留下来
		  collapsed:: true
			- ((63ea475c-938f-484e-98a3-d1dced9ab6a7))
	- The role of Intra-procedural Analysis
	  collapsed:: true
		- Detect code clones (by identifying patterns in the PDG).
		- Debug - find the code that might be responsible for a faulty variable value.
		- Check for vulnerabilities.
			- Could this variable possibly affect critical code?
		- Compute metrics from graph.
			- Overlap between slices for the same code indicates cohesion.
- ((63ea48c7-2865-441e-92e3-89825400da1f))
  collapsed:: true
	- Calls
	  collapsed:: true
		- When a method invokes another method.
	- ((63ea4cf7-6a5f-4e1f-9d10-d1248ca6804d))
	- Fan-in and Fan-out metrics
		- Can be computed at a method / function level, or at an entire class level
			- For a class, sum of number of incoming / outgoing edges for all methods
			- Call must come from (or go to) a different class.
		- Fan-in
			- ==Number of incoming calls== to a method or a class.
			- Provides an idea of ==how “critical” or “useful” a class or method is==.
		- Fan-out
			- Equivalent of fan-in with outgoing edges.
- ((63f372f7-5955-41f5-b788-b2c747612b1d))
	- TODO Reflection
		- The ability of a program to inspect itself at runtime.
		- Reverse-engineering a class diagram with Reflection
	- Decompilation
	- Static analysis is conservative
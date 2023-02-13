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
- Intra-procedural Analysis
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
		- Does node 7 post-dominate node 3?
		  Does node 8 post-dominate node 7?
		  What is the immediate post-dominator for node 7? 
		  Draw out the Control Dependence tree for this CFG.
		  ((63ea3b4f-b5d2-4338-8ae1-e737a60bdc23)) [[card]]
			-
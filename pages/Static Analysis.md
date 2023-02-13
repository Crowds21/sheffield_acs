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
		- <img src="https://www.plantuml.com/plantuml/png/JSon3e9048JXVfzYIyZ5s1_w2ZGczWSEiCbvaBq5bQSNATHcYZzVXZbRK2FfYWKgtUiQuenSiWr8v9zDq8eK4uAH5-SgykseYjPaJEpElEoU3_nF-J58HC5oQj3BvZWYzJQKv1KsQzgrAtvNnoptAMAzo8go8iGC_k8wr5jAD-a-Isy0" />
		  {{renderer :plantuml_rukfkaee}}
			- ```plantuml 
			  start
			  if(verifyValues) then
			  :xbar;
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
		-
-
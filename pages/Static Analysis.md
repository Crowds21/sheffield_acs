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
	- Post-dominates and control dependence
		-
	- Control Flow Graph
- <img src="https://www.plantuml.com/plantuml/png/DSan3eCm30NGtQVm2CeDad85HlP0VuYbo5IEQSljsmvTtlAOksTpaZ8yOLAk9RSJVMIlK8hlDLiYmmFPAKe8YU9sc65pEPJ3z4z-LMaOM6uhTlaED-ZkTIIq3gPeyDEKvpmdWjwb_AGF" />
  {{renderer :plantuml_rukfkaee}}
	- ```plantuml 
	  start
	  if(verifyValues) then
	  :xbar;
	  repeat
	  :i++;
	  :correction +=;
	  repeat while( i<begin + length)
	  else 
	  :return NaN;
	  endif
	  end
	  ```
-
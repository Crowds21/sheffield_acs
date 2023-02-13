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
- <img src="https://www.plantuml.com/plantuml/png/5SWn3eCm30NGtQVm2EeDGdi5nkw6_X1BaQaS0-tjWUKDZxc5U93cReTh_h-bRcWzHu5H-atY0pc-aE2ZQ4N7-fomgF63Aso9qbEQLtVCeUkrhu5G6vYI8pOt7cMyoZwQR-a4" />
  {{renderer :plantuml_rukfkaee}}
	- ```plantuml 
	  start
	  if(verifyValues) then
	  :xbar;
	  repeat  ( i<begin + length) 
	  :correction +=;
	  else 
	  :return NaN;
	  endif
	  end
	  ```
-
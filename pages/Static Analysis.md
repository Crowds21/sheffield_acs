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
- <img src="https://www.plantuml.com/plantuml/png/Kr0eBaaiAk7AJDCeIotAJAiCIymfJItML2Z9ICtZigf8IYoovahDAKvLuB8gIYqfBSfJy4lq0mhbfMIcWKWk0000" />
  {{renderer :plantuml_rukfkaee}}
	- ```plantuml 
	  start
	  if(verifyValues) then
	  :xbar;
	  repeat
	  else 
	  :return NaN;
	  endif
	  end
	  ```
-
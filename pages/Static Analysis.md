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
- <img src="https://www.plantuml.com/plantuml/png/Kr0eBaaiAk6oChJcoapJCD9KACb8pGDo3QovKdEAKxciZAsvYalo2xW0" />
  {{renderer :plantuml_rukfkaee}}
	- ```plantuml 
	  start
	  :1;
	  if(2) then
	  :10;
	  else
	  :3;
	  endif
	  stop
	  ```
-
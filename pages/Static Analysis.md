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
- <img src="https://www.plantuml.com/plantuml/png/Kr3GqD9KqDMrKr1ooomgBb5mJ2x9BCiigLJYGXS0gmAgvW80" />
  {{renderer :plantuml_rukfkaee}}
	- ```plantuml 
	  (*) --> "First Activity"
	  "First Activity" --> (*)
	  ```
-
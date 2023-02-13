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
- <img src="https://www.plantuml.com/plantuml/png/5SWn3eCm30NGtQVu8uWRG7i5nkw6_e2bA237LEtjIPStFA26UeYbxaEtz7jflbXxnCuYutTHdyHvKWFeO8-5cnKCo2nRx3raN0zthc57w-Sap9LjdN5vmQnpg_Asz5Tk" />
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
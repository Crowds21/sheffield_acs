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
- <img src="https://www.plantuml.com/plantuml/png/HOon4e8m44Jx-uehoQIm3_eBDCxO1rpWPc9WBWSgNoyKQhF5lhVBN2ogaVJL2fN-VOjfGN5i8pA5Lnkr9iMCQ1J4-vf2DwcYCvao-yiNydEKX8hbt6AGdN127cnq51IsQERZobV_yQd8OqxOhhB1rOHKm3-vYSrUvRlqHz87" />
  collapsed:: true
  {{renderer :plantuml_rukfkaee}}
	- ```plantuml 
	  start
	  if(verifyValues) then
	  :xbar;
	  repeat
	  :i++;
	  :correction +=;
	  repeat while( i<begin + length)
	  :return xbar+(correction/simplezSize);
	  else 
	  :return NaN;
	  endif
	  end
	  ```
-
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
- <img src="https://www.plantuml.com/plantuml/png/DSax3eD034NHtgjm2SeEXcGBbEaDUSDO6XdaCVdi7YZItE9SvXRYGPgxDrppxobrH-iv2epITn8VoB51WjAykcCENOrlZp_pfsX5ntgViEXvkCAMA3sXDZ0bH-nkFCeu4Eob-IeT" />
  {{renderer :plantuml_rukfkaee}}
	- ```plantuml 
	  start
	  if(verifyValues) then
	  :xbar;
	  repeat
	  :correction +=;
	  repeat while( i<begin + length)
	  else 
	  :return NaN;
	  endif
	  end
	  ```
-
- Dynamic Analysis
	- 简介
		- Limitations of  static analysis
		- 目的
			- Run the code. Extracting information from program executions.
		- 常用方法
			- Testing
			- Profiling
			- Logging
			- Debugging
	- Execution Traces
	  ref:: ((63f3788b-f092-4cbc-a971-db6fb086a39c))
		- A Trace is a “record” of an execution.
	- Loggers
		- automate the collection of runtime data
	- Precision
		- The size of a trace file is impossible to predict in general.
		- Large traces are harder to analyse and manage.
		- 所以需要挑选有用的信息来收集
	- The Heisenbug
	  ref:: ((63f37da1-718b-48f2-a9c5-3e8abb63b419))
		- A bug that disappears / alters its behaviour when you attempt to observe it. (量子bug)
	- Sound but imprecise - unsound but precise
	  健全但不精确与不健全但精确的对比
	  ref:: ((63f37e65-7486-4834-80e4-02ddd42ea51c))
- Automatically Instrumenting Java Code
	- Aspects (切片)
		- A way to modularise software (模块化软件) in terms of “==cross-cutting concerns==”.
		- Capture code that deals with a particular ‘aspect’ (known as an “==advice==”).
		- Advice is “==woven==” into software execution via “==join points==”
		- A specification that links advice to a join-point is known as a “==point cut==”.
-
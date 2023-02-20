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
	  collapsed:: true
		- A way to modularise software (模块化软件) in terms of “==cross-cutting concerns==”.
			- Motivated by the high amount of duplicate code in systems.
		- Capture code that deals with a particular ‘aspect’ (known as an “==advice==”).
			- E.g. File-handling, data-base management, logging...
		- Advice is “==woven==” into software execution via “==join points==”
			- E.g. method entry or exit points, field accesses, etc.
		- A specification that links advice to a join-point is known as a “==point cut==”.
	- Aspects in Java
		- Aspect-Oriented Programming Libraries
			- AspectJ
		- Write “Transformers”
			- modify classes during execution.
		- Deployed as “agents”
			- “Attached” to a Java program when it is run, have the ability to alter a class when it is loaded.
	- Aspects 的工作方式
	  collapsed:: true
		- ((63f3818b-fe18-4efb-981a-391a73bdf9d4))
		- 好像有通过字节码和反射两种aop的方式??
- Answering Questions with Dynamic Analysis
  ref:: ((63f38565-b677-4dc1-8459-6a947f5612c2))
	- Gauging Importance
	  collapsed:: true
		- Count the number of occurrences of a class or a method in a trace.
		- 可以绘制的图形
			- Name of method / class versus number of occurrences in the trace.
	- Identifying bottlenecks
	  collapsed:: true
		- Which methods might be inefficient CPU / Memory hoggers?
		  哪些方法可能是低效的CPU/内存占用者？
		- 可绘制的图像
			- Method vs. average resource consumption.
	- Phase analysis
		- Identify distinctive “phases” of execution.
	- Feature Identification
	- Key Takeaways
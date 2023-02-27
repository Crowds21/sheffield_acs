- 为什么需要 Async programming
	- 因为一个JS程序只有一个线程,因此需要异步来执行一些任务
-
- callbacks
	- What is callbacks [[card]]
		- Callbacks can be used to perform an action at the end of an asynchronous action
		- 当使用一个函数作为回调时,只需要传入函数的名字,而不需要`()`
- Time events
  collapsed:: true
	- js 中,允许在指定的时间范围内执行函数
	- setTimeout(functionName, time) 指定时间后运行函数
	- setInterval()在指定的时间间隔中调用函数或表达式
		- It is a method of the window object
		- It is repeatedly executed until stopped
			- clearInterval()
			- Window is closed
- JS函数修改一个}外部已经定义的变量,不需要 return
- JAVASCRIPT PROMISES
  collapsed:: true
	- Promises are a way to create asynchronous code that allows easy sequencing of async processes
	- A Promise can be:
	  collapsed:: true
		- pending: initial state
		- fulfilled: the operation was completed successfully.
			- Returns a value
		- rejected: the operation failed.
			- Returns an error
	- How promises work
	  collapsed:: true
		- Declaration
			- it declares a long running computation
			- it declares placeholders for the behaviour to adopt in case of success and in case of error(resolve and reject represent functions passed as parameters
		- Consumption
			- it declares the functions actual functions to be used for success/error
		- Execution
			- it runs the promise code and calls the actual success/reject function
	- Promises methods
	  collapsed:: true
		- `promise.then()`
			- takes two arguments
			- callback for success and failure
		- Promise.catch()
			- deal with the rejected promise
		- chain promises
- ES6
- Async and await
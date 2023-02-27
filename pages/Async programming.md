- Real-time communication
	- What is Real-time communication
		- Ability to get resources when they are available and add new ones when we want to
	- To build a real-time web application it is important to consider
		- Scalability
		- Security
		- Async programming
		- Data Format
		- Bi-directional communication
- Async programming
  collapsed:: true
	- 为什么需要 Async programming
		- 因为一个JS程序只有一个线程,因此需要异步来执行一些任务
	- JS 中实现 Async programming 的方式 [[card]]
		- Callbacks (classic)
		- Timeouts and Intervals (delayed and repeated execution)
		- Promises (new)
		- Await/async (newer)
- callbacks
	- What is callbacks [[card]]
	  collapsed:: true
		- A callback is a function that is called only when another function is performed AND  finished
	- How can we use callbacks [[card]]
	  collapsed:: true
		- Callbacks can be used to perform an action at the end of an asynchronous action
		- 当使用一个函数作为回调时,只需要传入函数的名字,而不需要`()`
	- Example of using callbacks
	  collapsed:: true
		- ```js
		  var myVar;
		  function myFunction() {
		  	myVar = setTimeout(alertFunc, 3000);
		  }
		  function alertFunc() {
		  	alert("Hello!");
		  }
		  ```
- Time events
	- js 中,允许在指定的时间范围内执行函数
	- Time events 中常用函数
		- `setTimeout(functionName, time)`
			- 指定时间后运行函数
		- `setInterval()`
			-
	- setTimeout(functionName, time)
	- 在指定的时间间隔中调用函数或表达式
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
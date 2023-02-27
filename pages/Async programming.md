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
	- Time events 中常用函数 [[card]]
	  collapsed:: true
		- `setTimeout(functionName, time)`
			- 指定时间后运行函数
		- `setInterval()`
			- 在指定的时间间隔中调用函数或表达式
			- calls a function or evaluates an expression at 
			  specified intervals (in milliseconds)
			- 它会重复执行,直到停止,停止的方式有
				- `clearInterval()`
				- 关闭网页窗口
	- JS函数修改一个外部已经定义的变量,不需要 return
- Javascript Promises
	- What is Promises [[card]]
	  collapsed:: true
		- Promises are a way to create asynchronous code that allows easy sequencing of async processes
		- Promises 是创建异步代码的一种方式，可以轻松地对异步进程进行排序
	- Status of Promises [[card]]
	  collapsed:: true
		- pending
			- initial state
		- fulfilled
			- the operation was completed successfully.
			- Returns a value
		- rejected
			- the operation failed.
			- Returns an error
	- How promises work [[card]]
	  collapsed:: true
		- Declaration
			- it declares a long running computation
			- it declares placeholders for the behaviour to adopt in case of success and in case of error(resolve and reject represent functions passed as parameters
			- 它声明了在成功和错误情况下所采取的行为的占位符（解析和拒绝代表作为参数传递的函数）
		- Consumption
			- it declares the functions actual functions to be used for success/error
			- 它声明了将用于成功/错误的实际函数
		- Execution
			- it runs the promise code and calls the actual success/reject function
			- 它运行 promise code  并调用实际的成功/拒绝函数
	- Promises 中的函数 [[card]]
		- `promise.then()` 接收两个参数
			- callback for success and failure
		- Promise.catch() 处理被拒绝的 promies
			- deal with the rejected promise
		- chain promises
	-
- ES6
- Async and await
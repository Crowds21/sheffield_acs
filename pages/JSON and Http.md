title:: JSON and Http

- Json
	- Json 的两种数据结构
	  collapsed:: true
		- k-v 对
		- array [1,2,3]
	- nodejs 解析 json 对象 [[card]]
	  collapsed:: true
		- `JSON.parse(jsonText)`
	- nodejs 将一个对象转换为 json 对象 [[card]]
	  collapsed:: true
		- `JSON.stringify(object)`
- Http
	- Three main popular methods for reusing old data and  only receiving the missing data [[card]]
		- Ajax
			- Ajax is a concept
			- You do not have to reload a whole HTML page to update its content
			- First Ajax implementation was using `XMLHttpRequest`
			- • Ajax uses a combination of
			  • A browser built-in XMLHttpRequest object (to request data)
			  • Javascript + HTML DOM to display the data
		- Axios
			- Axios is not a replacement of Ajax, it facilitates the way to build “Ajaxbased” web applications
		- Fetch
	- Ajax
		- 图示
		  collapsed:: true
			- ((63ee055e-4eb3-495f-899f-45ab46f26e53))
		- 使用浏览器内建的 XMLHttpRequest 以及 JS  HTML DOM
		- 实现不刷新网页的情况下更新网页内容
	- Axios
	- Fetch
-
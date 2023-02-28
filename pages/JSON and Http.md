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
		  collapsed:: true
			- Ajax is a concept
			- You do not have to reload a whole HTML page to update its content
			- First Ajax implementation was using `XMLHttpRequest`
		- Axios
		  collapsed:: true
			- Axios is not a replacement of Ajax, it facilitates the way to build “Ajaxbased” web applications
		- Fetch
	- Ajax
	  collapsed:: true
		- 图示
			- ((63ee055e-4eb3-495f-899f-45ab46f26e53))
		- 使用浏览器内建的 XMLHttpRequest 以及 JS  HTML DOM
		- 实现不刷新网页的情况下更新网页内容
	- Axios
	  collapsed:: true
		- Axios get call [[card]]
			- ```js
			  axios.get(url) 
			  	.then((response) => { 
			  		displayOutput(response) 
			  	}) 
			  	.catch((err) => console.log(err)); // 处理被拒绝的请求
			  ```
		- Axios POST [[card]]
			- ```js
			  axios.post(url,jsonObject)
			    .then((response) => displayOutput(response))
			    .catch((err) => console.log(err));
			  ```
	- Fetch
		- [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)
		- 简介
			- Promise-based HTTP client
			- Has a broader scope than Axios
			- No need to import if you are using node >18
				- Otherwise
					- `const fetch = require("node-fetch")`
					- `import fetch from "node-fetch"`
			- It’s lower level, so might be more difficult to use
		- Fetch Get [[card]]
		  collapsed:: true
			- ```js
			  fetch(URL)
			  .then((response) => response.text()) // extracts the text from the response
			  .then((body) => { 
			    res.send(body); // send back the response HTML
			  });
			  
			  fetch(URL,{
			    	method: "POST",
			  	headers: customHeaders
			  })
			  .then((response) => response.text()) // extracts the text from the response
			  .then((body) => { 
			    res.send(body); // send back the response HTML
			  });
			  
			  ```
		- Fetch 定义 Header [[card]]
		  collapsed:: true
			- 可以使用fetch 中的第二个参数中,设定 `headers`来发送带有自定义请求头信息
			- 响应对象中的`response.headers` 包含了所有的响应 header 信息
		- Fetch Post [[card]]
		  card-last-interval:: -1
		  card-repeats:: 1
		  card-ease-factor:: 2.5
		  card-next-schedule:: 2023-03-01T00:00:00.000Z
		  card-last-reviewed:: 2023-02-28T20:17:49.676Z
		  card-last-score:: 1
		  collapsed:: true
			- ```js
			  fetch(url, {
			  	method: "POST",
			  	headers: customHeaders,
			  	body: JSON.stringify(data),
			  })
			  ```
- JQuery
	- jQuery Ajax Methods: ajax()
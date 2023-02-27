title:: Socket.io

- BI- directional server communication
	- Advantages of  directional server communication [[card]]
		- This enables the server to send real-time updates asynchronously
		- without requiring the client to submit a request each time
		- Allows to push data from the server to the client
	- Websockets 与 Ajax / Http 之间的区别 [[card]]
		- Ajax和HTTP请求允许模拟双向通信
			- Polling 轮询
				- 客户端定期发送AJAX请求（例如，每隔几秒钟）
				- 如果有新的数据，服务器会在响应中发送
			- Streaming 流式传输
				- 各种技术（多部分/分块响应），允许服务器对单个客户端请求发送一个以上的响应
				- 客户端向服务器打开一个HTTP
				- 服务器发送HTTP头信息，不关闭连接
				- 当新的数据到达时，服务器在响应体中发送它
		- Websockets是一种通过TCP的全双工通信协议
			- 与HTTP兼容
			- 设计用于在HTTP端口80和443上运行
			- WebSocket 握手使用HTTP Upgrade header, 从HTTP协议切换到WebSocket协议.
	- Websockets 工作原理 [[card]]
	  collapsed:: true
		- A socket is a channel of communication between processes (on the  same or different computers)
		- 它们在客户端和服务器之间建立一个持久的连接，双方可以在任何时候开始发送数据
		- Websocket通过TCP协议在不同网络连接的机器上的两个进程之间建立通信
		- 在初始握手请求/响应之后
			- 客户端和服务器可以在任何时候发送消息，必须异步处理消息的接收
- Socket.io
	- 什么是 socket.io
		- 基于 WebSocket 协议的一个库
		- There are [alternatives](https://github.com/websockets/ws)
	- Socket.io的组成
		- a client-side library that runs in the browser
		- a server-side library
		- Both components have a nearly identical API
		- It is possible to send any data
	- How to use socket.io (Server)
		- ```js
		  //Server 
		  
		  //create socket.io instance
		  const io = require('socket.io')(server);
		  // create a server that listens to socket.io connections
		  io.on("connection", (socket) => {
		    console.log("New Client is Connected!");
		  });
		  // `io.on` event handler handles connection, disconnection, etc. , 
		  //  events in it,  using the socket object.
		  
		  // send messages 
		  io.sockets.emit("welcome", {
		    description: "Hello and Welcome to the Server"
		  });
		  //  the server can send other messages to all clients by using the broadcast event
		  ```
	- How to use socket.io (Clien)
		- ```html
		  <script src="https://cdn.socket.io/4.5.4/socket.io.min.js"></script>
		  ```
		- ```js
		  var socket = io()
		  // create an event listener that write into an element of my  `index.ejs` page
		  socket.on('welcome',function(data){
		  	document.getElementById('Welcome').innerHTML = data.description;
		  });
		  ```
	- Broadcasting
		- Create rooms
			- 一个房间就是一个子通道,套接字可以加入或者离开
			- 信息只能够发送给连接到该房间的客户端
			- 加入一个房间
				- ```js
				  io.on("connection", socket => {
				    socket.join("some room");
				  });
				  ```
			-
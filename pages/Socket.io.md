title:: Socket.io

- BI- directional server communication
	- Advantages of  directional server communication [[card]]
		- This enables the server to send real-time updates asynchronously
		- without requiring the client to submit a request each time
		- Allows to push data from the server to the client
	- 简介
		- Websockets是TCP上的全双工通信协议，与HTTP兼容，设计用于在HTTP端口80和443上运行，WebSocket握手使用HTTP升级头，从HTTP协议切换到WebSocket协议
	- 与 Ajax / Http 之间的区别
		- Ajax和HTTP请求允许模拟双向通信
		- Polling 轮询
		- Streaming
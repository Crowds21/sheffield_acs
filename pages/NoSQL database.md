- NoSQL database
	- NoSQL databases are characterised by
		- Dynamic schemas动态模式
			- to allow the insertion of data without a predefined schema
		- easy to make significant application changes in real- time
		- Relational databases require schemas to be defined before you can add data
			- Changes require downtime
	- TODO NoSQL 的优点和缺点
	  collapsed:: true
		- NoSQL数据库的问题
			- 没有标准化的数据关系
				- 自由，但如果过度使用也是一个有害的特征
			- 查询能力有限
			- 没有自动的一致性检查
				- 例如，当多个交易同时进行时
			- 最终的一致性并不适合每个应用
	- Document stores
	  collapsed:: true
		- 数据存储在列中(SQL 数据库存储在行)
		- 可以对数据进行
		- 对存储的数据进行快速读/写访问
		- 实现有效的压缩，因为列一般都是统一的
		- 专注于查询数据的一个方面（如一段时间内的价格），而不是整个记录（两个时期内x公司的价格）。
		- 例如Cassandra和HBase
			- 对大型数据集的查询进行了优化
	- Graph Store
- MongonDB
	- MongonDB 的结构
		- 每个数据库都包含集合
			- 其中反过来又包含文件
		- 每个文件可以有不同的字段数量
			- 每个文档的大小和内容可以彼此不同
		- 每个文档的大小和内容可以彼此不同
		- 文档的结构与开发人员构建类和对象的方式相一致
		- 数据模型允许你表示层次关系，存储数组等
	- Documents
		- MongoDB中的记录是一个document，它是一个由K-V对 组成的数据结构
		- MongoDB文档类似于JSON对象
		- 字段的值可以包括其他文档、数组和文档的数组
	- BSON
		- 最终保存的是二进制的json字符串
- Commands of MongonDB
	- Create a database [[card]]
	  collapsed:: true
		- ```js
		  // 创建一个 MongoClient 对象
		  var MongoClient = require( 'mongodb').MongoClient;
		  // 指定链接 URL IP,端口,数据库名称
		  var url = "mongodb://localhost:27017/mydb";
		  // 只有数据库得到数据之后,他才会真正创建他!!!
		  MongoClient. connect(url, function(err, db) {
		  	if (err) throw err;
		  	console.log ("Database created!");
		  	db.close();
		  });
		  
		  ```
	- Create a collection [[card]]
	  collapsed:: true
		- ```js
		  var MongoClient = require('mongodb').MongoClient;
		  var url = "mongodb://localhost:27017/mydb";
		  MongoClient.connect(url, function(err, db) {
		  	if (err) throw err;
		  	var dbo = db.db("mydb");
		    
		    	// 创建 collection
		  	dbo.createCollection("cats", function(err, res) { 
		        if (err) throw err;
		        console.log("Collection created!"); 
		        db.close();
		  	});
		  })
		  ```
	- Inserting a document [[card]]
	  collapsed:: true
		- ```js
		  var MongoClient = require('mongodb').MongoClient;
		  var url ="mongodb://localhost:27017/";
		  MongoClient.connect(url, function(err, db) {
		    if (err) throw err;
		    var dbo = db.db("mydb");
		    var myobj = { name: "Neve", breed: "Angora" };
		    
		    // Inser Document
		    dbo.collection("cats").insertOne(myobj, function(err, res) {
		      if (err) throw err;
		      console.log("1 document inserted"); 
		      db.close();
		    });
		  })
		  ```
	- Finding a document [[card]]
	  collapsed:: true
		- ```js
		  var MongoClient =
		  require('mongodb').MongoClient;
		  var url = "mongodb://localhost:27017/";
		  MongoClient.connect(url, function(err, db) {
		    if (err) throw err;
		    var dbo = db.db("mydb");
		    
		    
		    // Finding a document
		    dbo.collection("cats").findOne({}, function(err, result) {
		      if (err) throw err; 
		      console.log(result.name); 
		      console.log(result.breed); 
		      db.close();
		    });
		  });
		  ```
	- Querying a document [[card]]
	  collapsed:: true
		- ```js
		  var MongoClient = require('mongodb').MongoClient;
		  var url ="mongodb://localhost:27017/";
		  MongoClient.connect(url, function(err, db) {
		    if (err) throw err;
		    var dbo = db.db("mydb");
		    var query = { breed: "Angora" };
		    
		    // Query
		    // query - an object containing the query
		    // Can use regular expressions
		    // And a callback function, to work with the result
		    dbo.collection("cats").find(query).toArray(function(err, result) {
		      if (err) throw err; 
		      console.log(result); 
		      db.close();
		    });
		  });
		  ```
	- Other commands
		- Sort() [[card]]
		  collapsed:: true
			- ```js
			  var mysort = { name: 1 };
			  dbo.collection("customers").find().sort(mysort).toArray(function(e rr, result)
			  ```
		- deleteOne() [[card]]
			- defining which document to delete.
			- ```js
			  ```
		- drop()
		- updateOne() [[card]]
			- ```js
			  MongoClient.connect(url, function(err, db) {
			    if (err) throw err;
			    var dbo = db.db("mydb");
			    var myquery = { name: "Neve" };
			    var newvalues = { $set: {name: "Neve", breed: "Turkish Van" } }; 
			    dbo.collection("cats").updateOne(myquery, newvalues, function(err, res) {
			      if (err) throw err;
			      console.log("1 document updated"); 
			      db.close();
			    });
			  });
			  	
			  ```
	- Connect MongoDB
		- MongoDB
		- Driver
		- Mongoose (类似用 js 模拟 mongodb 模型?)
	- TODO Compiling a schema into a model
	- Validation
	- Instances
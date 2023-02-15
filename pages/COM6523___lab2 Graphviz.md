- [DOT Language | Graphviz](https://graphviz.org/doc/info/lang.html)
- Maven
	- ```
	  mvn package -DskipTests -Drat.skip=true
	  ```
	- 跳过 test 和 checking, 直接打包
-
- 通过 [UOS-Reengineering/cfg-and-dot-lab-Crowds21](https://github.com/UOS-Reengineering/cfg-and-dot-lab-Crowds21) 来生成 dot 代码
- 引入依赖的时候可以直接通过 intellij , 从而避免修改
- 使用`dot -Tpdf gr.dot > gr.pdf`生成文件
-
-
-
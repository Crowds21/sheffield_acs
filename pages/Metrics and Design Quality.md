- Good Design
	- Make your design is easy to understand
	  collapsed:: true
		- Research found
			- Developers spend ~60% of their time on “program comprehension”.
			- A further ~25% of their time is spent on navigation.
		- ((6405ed49-b8dd-424e-adee-684137fb6217))
			- Save time to understanding what is already there
			- Reduces risk of misunderstandings
		- Modularity 模块化
	- Good Modularity
	  collapsed:: true
		- Coupling 耦合
			- “Tightly coupled” if there are lots of calls or data-accesses across file / module boundaries.
			- Loose coupling encouraged by encapsulation - good use of public interfaces.
		- Cohesion 内聚
			- A single file or module is “cohesive” if the code within it is highly interdependent.
		- 目标: 高内聚,低耦合
	- Class / Module Size
	  collapsed:: true
		- Single Responsibility Principle.
			- 一个的类应该只负责一个功能
		- Do Not Repeat Yourself (DRY)
			- 应该减少重复代码
		- Big classes ( lots of methods, high lines of code)  suggest that these principles have been violated.
		  一个很庞大的类可能违反了以下原则
			- Tend to lack cohesion, and incur high coupling.
			- Hard for developers to fully understand - difficult to maintain.
			- Defect prone
			- “God classes”.
	- ((6405f07a-ca4e-4fad-8fcc-37bef5be3853))
	  collapsed:: true
		- Do not repeat yourself (DRY)
		- Single Responsibility Principle (SRP)
		- Open-Closed Principle
			- Objects should be open for extension, but closed for modification.
		- Liskov Substitution Principle
			- 对象应该可以用其子类型的实例替换，而不影响程序的正确性。
		- Interface Segregation Principle
			- 许多针对客户的接口比一个通用的接口要好。
		- Dependency Inversion Principle
			- 依靠抽象的东西，而不是具体的东西。
- ((6405f14d-a2f3-4f21-8ce2-ba4703573d16))
	- **You can not control what you can not measure**
		- TODO Measuring Coupling and Cohesion
		  collapsed:: true
			- Fan-in
			- Fan-out
			- Response set For a Class (RFC)
			- Lack of Cohesion of Methods (LCOM)
		- TODO Measuring Size
		  collapsed:: true
			- Lines of code
			- Number of Methods
			- Number of Data Members
		- TODO ((6405f782-4c3f-4149-bef9-8dd294b743e2))
		  collapsed:: true
			- Weighted Methods per Class
			- Depth of Inheritance
			- Number of Children
			- Coupling between Object Classes
			- Response for Class
			- Lack of Cohesion in Methods (LCOM)
				- 访问至少一个相同的实例变量的方法对的数量
		- TODO ((6405f788-0d9e-469c-8f76-06de48d39698))
		  collapsed:: true
			- 随着时间推移发生的变化量.  对于每个新版本，"流失 "是指在一定时期内增加或改变的代码行的总数
			-
		- ((6405f804-14bc-4603-a4ba-dbf6210c655d))
		  collapsed:: true
			- "一旦一项措施成为目标，它就不再是一个好的措施。就不再是一个好的措施"
			- 谨慎对待衡量标准, 不要作为目标使用, 只用来作为大局的一部分提供信息
- ((6405faaa-eb33-4733-bf5a-fa4fbeb9990e))
	- ((6405fab9-16f6-48c0-b97f-367f1f35411d))
		-
		- ((6405fad0-fc5f-47e8-9dbc-872eae444a55))
	- ((6405fafb-7c7d-4b11-9a43-de2eebd7fd60))
	-
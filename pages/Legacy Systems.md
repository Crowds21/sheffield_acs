-
-
- View points
	- What is view points
	  collapsed:: true
		- Collection of patterns, templates, and conventions for constructing one type of view.
		- Defines the relevant stakeholders, and the relevant guidelines, principles and template models for constructing the views.
	- Consist of View points
	  collapsed:: true
		- Context
		  collapsed:: true
			- Describes the relationships, dependencies, and interactions between the system and its environment.
		- Functional
		  collapsed:: true
			- Functional elements, their responsibilities and interactions. Traditionally the starting point for an architectural description.
		- Information
		  collapsed:: true
			- How the architecture stores, manipulates, manages and distributes information. Content, structure, ownership, latency,  etc.
		- Concurrency
		  collapsed:: true
			- Maps functional elements to concurrency units to clearly identify which parts of the system are synchronous or asynchronous.
		- Development
		  collapsed:: true
			- How does the architecture support development - building, testing, maintaining, and enhancing the system.
		- Deployment
		  collapsed:: true
			- What environment will the system be deployed to? Dependencies on the runtime environment, network connections, etc.
		- Operational
		  collapsed:: true
			- How the system will be operated, administered, et
- Perspectives
  collapsed:: true
	- Accessibility
	  collapsed:: true
		- The ability of the system to be used by people with disabilities
	- Availability & Resilience
	  collapsed:: true
		- Ability to be operational as and when required, and to handle failures that could affect availability.
	- Development Resource
	  collapsed:: true
		- Ability to be designed, build, deployed, and operated within constraints around people, budget,  time, materials.
	- Evolution
	  collapsed:: true
		- Ability to be flexible in the face of inevitable change, balanced against costs of providing this  flexibility.
	- Internationalisation
	  collapsed:: true
		- Ability to be independent from any particular language, country or cultural group.
	- Location
	  collapsed:: true
		- Ability to overcome problems brought about by the location of its elements and distances between  them.
	- Performance & Scalability
	  collapsed:: true
		- Ability to predictably execute within mandated performance profile, and handle increasing volumes.
	- Regulation
	  collapsed:: true
		- Ability to conform to local and international laws, quasi-legal regulations, company policies, etc.
	- Security
	  collapsed:: true
		- Ability to reliably control, monitor, and audit who can perform what mechanisms on what resources.
	- Usability
	  collapsed:: true
		- Ease with which people can interact with the system and work effectively.
- TODO Why is reengineering  hard
	- Scale
	- Continuous change
	- Complexity
	- Dynamism 动态性
- Why not start from  scratch
	- It’s extremely risky
	- A lack of requirements and specification
	- Difficult to anticipate cost and ensure reliability.
	- Difficult to ensure that the replacement is able to replace the old system.
	- High stakes for business critical systems
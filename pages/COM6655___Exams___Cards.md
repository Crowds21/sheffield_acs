- 背景
	- 背景一 : 学校 SCH 找 Microsoft 开发软件检测学生作弊, Microsoft自己写不了找三哥写软件,最后好多学生没分.
	  id:: 63d58d08-c3d6-4edd-aa41-570b2388df9a
	- 背景二: 学校通过 Microsoft收集到了学生的信息,让合作伙伴 Rain 给学生发送折扣优惠信息
	  id:: 63d59a67-d84d-42f3-a329-8e3910ff5525
	- 背景三: 公司 Math 生产电子表格 SHEET, WordSoft 希望生产一种新的文字处理程序 Word.  WordSoft 希望 Word 能和 SHEET 兼容. WordSoft 反编译了 SHEET.
	  id:: 63d59eac-bdf4-45af-9eb0-6ea9e2dff6ff
	- 背景四: WordSoft完成程序. Math 拿到了 WordSoft 的复制品, 认为 UI很相似
	  id:: 63d5a0fd-8986-4a9d-8bc1-da1b0256380c
	- 背景五: Math 怀疑 Word 抄袭,对他们的代码进行了反编译.发现相似代码, 包含读取 sheet 文件, 快速排序,识别鼠标点积和移动
	  id:: 63d5a5bb-6f95-4066-aed1-44ad7891c364
- ### Intelligence Law
	- ((63d59eac-bdf4-45af-9eb0-6ea9e2dff6ff)) [[card]]
	  collapsed:: true
		- Related Laws [[The Copyright (Computer Programs) Regulations]]
		- Related Laws [[Copyright, Designs and Patents Act]]
		- ((63d52842-af57-437f-9bb5-74819021458f))
		  collapsed:: true
			- There is a competitive relationship between these two software
			- Decompiling is not allowed when creating competing products
		- ((63d52842-b13a-4e84-9893-648f2307f5a9))
		  collapsed:: true
			- decompilation and rewrite are both effectively translation, which is a restricted right
	- ((63d5a0fd-8986-4a9d-8bc1-da1b0256380c)). 能否以外观和感觉为由,认为 Word 侵犯了 Math 的版权 [[card]]
		- Relevant Legislation is [[Copyright, Designs and Patents Act]]
		- Screen design and icons are be protected by copyright
		- ((63d52842-66ec-4cd0-94ed-5b757a9d33e2))
			- but it does not protect "look and feel".
		- Case Law
			- ((63d52842-6c9b-4e6f-aee6-7d36c54cccfd))
			- ((63d52841-303f-4a0c-b4b0-6327b0ed1846))
				- ((63d52841-34d4-4c16-8345-9dad923f2651))
	- ((63d5a5bb-6f95-4066-aed1-44ad7891c364)), 双方在 [[Copyright, Designs and Patents Act]] 下的责任
		- ((63d52842-0a56-4399-be8f-3b1dcb4a0280))
			- Is Math a legitimate user of Word, Only legal users can decompile the sofware  if necessary
		- 程序的 substantial part
			- ((63d52842-cea3-444a-ad14-35a17223f1cb))
			-
		- [[The Law of Confidence]]
- ### Contract Law
  collapsed:: true
	- ((63d58d08-c3d6-4edd-aa41-570b2388df9a))
	  collapsed:: true
	  案例中和 Contract Law 相关的内容 [[card]]
		- Contracts between SCH and Microsoft, Microsoft and 三哥
		- [[Consumer Rights Act]]
		- Software is digital product, the software should have satisfactory quality.
		- The company provides services to schools, Microsoft should be carried out with a reasonable degree of care and  skill
		- ~~Bench of contract~~
		  collapsed:: true
			- warranties
			- conditions
		- Computer aided mistake.  As a result of using this system, many students' grades are 0
		- ~~Repair and Replace~~
		  collapsed:: true
			- ((63d52842-c4e5-4ba7-83ff-9e10bba6b7fb))
- ### Liability
  collapsed:: true
	- ((63d58d08-c3d6-4edd-aa41-570b2388df9a))
	  collapsed:: true
	  案例中Negligence 相关内容 [[card]]
		- The school own a duty of call to the student. It is predictable that there will be bugs in the software. And the student had a loss. 
		  memo:: negligence的条件
		- 阿三 did not find possible problems with the results of the algorithm, a competent professional should be able to find these problems
		- The software company's testing of the system may not have been adequate
		- ((635e8778-ea88-4539-b14d-952b2931ea1a))
			- This may be due to problems with the training data provided by the school, the school also contributed to the negligence
		- ((635e91fa-73c4-40b7-8835-f23da74cf541))
		-
	- ((63d58d08-c3d6-4edd-aa41-570b2388df9a))
	  collapsed:: true
	  案例中Negligence 相关内容
	  ((63d52843-ed39-4327-a1da-b453587d78ee)) [[card]]
		- If the advice given by the decision support system is wrong, the developer of the system may be liable to the recipient for Negligent misstatement
		- Reduced liability
			- little control over the way the system is used or interpreted
		-
	- ((63d58d08-c3d6-4edd-aa41-570b2388df9a))
	  collapsed:: true
	  ((635e96c3-4ac9-4867-89e9-f0a153125524)) [[card]]
		- The software company is vicariously liable to the school for any damages suffered by the student.
		- 阿三 is vicariously liable to the software company
- ### Computer Misuse
	-
-
- ### Data Protection
	- ((63d59a67-d84d-42f3-a329-8e3910ff5525))
	  collapsed:: true
	  结合 [[Data Protection Act]] 分析该案例 [[card]]
		- 相关定义
			- Email is ((63d52842-cd42-4ff6-bf4c-ff2dcf94ecad))
			- Controller - School
			  collapsed:: true
				- The school has the student's email information and can decide how to use it.(purpose and manner)
			- Processor - Rain
			  collapsed:: true
				- Rain Company sends advertising emails to students on behalf of the school
		- ((63d59cd6-f605-46c9-b558-61d69c808b61))
			- Purpose Limitation
				- Rain sent unsolicited emails
			- ((63d52842-e610-45cf-8c47-9de7513388ce))
				- The school may not have recorded and reported unsolicited emails sent by Rain
			- ((63d52842-1341-4712-a569-c2013f5cd8d8))
				- The school collected the emotional features of students through Microsoft, information that was irrelevant for their purposes
-
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
	- 背景六: A 在未经授权的情况下在B 的电脑上查找了一些文件并复制到 USB 中,以便牟利
	  id:: 63d5a9d6-b303-4f67-9677-b67fb4860022
	- 背景六: Lus收集的数据违反了之后才新出的伦理政策,但是他主动向相关人员进行了汇报
	  id:: 63d666e1-f2f9-4a42-b72e-5a91bf67c1e5
- ### Legal Concept
	- TODO ((63d5a9d6-b303-4f67-9677-b67fb4860022))相关的 civil law [[card]]
	  id:: 63d5aa63-d7f3-4140-b43a-c3d9d3baf1c7
	  collapsed:: true
		-
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
	  collapsed:: true
		- Relevant Legislation is [[Copyright, Designs and Patents Act]]
		- Screen design and icons are be protected by copyright
		- ((63d52842-66ec-4cd0-94ed-5b757a9d33e2))
			- but it does not protect "look and feel".
		- Case Law
			- ((63d52842-6c9b-4e6f-aee6-7d36c54cccfd))
			- ((63d52841-303f-4a0c-b4b0-6327b0ed1846))
				- ((63d52841-34d4-4c16-8345-9dad923f2651))
	- ((63d5a5bb-6f95-4066-aed1-44ad7891c364)), 双方在 [[Copyright, Designs and Patents Act]] 下的责任 [[card]]
	  collapsed:: true
		- ((63d52842-0a56-4399-be8f-3b1dcb4a0280))
			- Is Math a legitimate user of Word, Only legal users can decompile the sofware  if necessary
		- 程序的 substantial part
			- ((63d52842-cea3-444a-ad14-35a17223f1cb))
			- Even if a very small part of the program is copied, it is an infringement if that part is material in terms of the function of the program
			- So the code for this function may have been copied
		- The other two parts are standard algorithms, so no expressions are copied
		- ((63d52842-b3fe-416f-bb71-2ed79c499a35))
			- Math needs to determine if the code is a copy
			- If the algorithm for part1 "input sheet file" is rewritten by WORD,  they may not be infringing under the law of the case.
- ### Contract Law
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
	- ((63d5a9d6-b303-4f67-9677-b67fb4860022)), 从 Criminal law 的角度分析 [[card]]
	  collapsed:: true
		- Guilty Action
			- Accessed someone else's computer and copied material
		- Guilty Mind
			- Want to use these materials for further legal action
		- [[Computer Misuse Act]]
		  ref:: ((63d52842-4392-49b9-9c4a-7e88531a13b2))
			- ((63623b75-9c19-4b4a-97fb-e86d4ca93557))
			- ((639df376-8804-4e7d-a2a8-a324052718a7))
		- Case law
			- ((63d52842-7bbf-4067-8f05-da302d682a4a))
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
- ### Social Context
	- ((63d666e1-f2f9-4a42-b72e-5a91bf67c1e5)) 提供三个例子,证明社会和技术之间的相互作用
	  collapsed:: true
		- ~~The relationship between supply and demand~~
		- The development of computer technology can bring positive impact to society
			- 结合一下材料
		- Potential negative impact of technology on society
			- 集合材料
		- ((635e91fa-73c4-40b7-8835-f23da74cf541))
		  id:: 63d66859-dc78-48af-8810-f410ab72de7b
		- Evidence suggests that huge investments in computer technology may not pay off
		- Technology and social change evolve together
			- The ethical policies in the case have changed and data are more difficult to collect, which may have implications for technical studies
		- ~~Technology may cause unemployment, but it can be solved in other ways~~
		- ~~Women and work from home~~
- ### Ethics
	- ((63d666e1-f2f9-4a42-b72e-5a91bf67c1e5)), 从实用主义和康德伦理学的角度分析 Lus 的行为
		- ((63d52843-0382-45a6-8933-2f0a65b32641))
			- Utilitarianism – the action is right that promotes the greatest good [5]
			- 结合案例说明他的哪些行为符合这一伦理理论  [5]
		- ((63d52843-5c89-4b0f-89c5-7c9834b0a61e))
			- The categorical imperative, treating people as ends (respecting their rights)
			  and not merely as means  [5]
			- 集合案例说明他的什么行为将人作为 目的和过程 [5]
- ### Professional Issues
	- ((63d666e1-f2f9-4a42-b72e-5a91bf67c1e5)) BCS Code中的那些内容和这一情景相关
		- ((63d52843-21d4-4c89-8e92-74d29d1c2b94))
			- 公共利益 Public interest
			  collapsed:: true
				- Should consider the public interest and not discriminate against others
			- 专业能力和诚信 Professional competence and integrity
			  collapsed:: true
				- As a professional, you should comply with the relevant professional requirements and no harm to others
			- 对有关当局的责任 Duty to relevant authority
			  collapsed:: true
				- Not to conflict with the relevant institutions and comply with the relevant requirements of the authorities
			- 对专业的责任 Duty to the profession
			  collapsed:: true
				-
		- Public interest
			- The algorithms he is working on are of public interest(结合例子)
		- Professional competence and integrity
			- He says he doesn't have a proper data management plan, which is not a professional's fault
		- Duty to relevant authority
			- When he discovered that the data he had collected did not comply with ethical policies, he reported it to the appropriate people.
		- Duty to the profession
			- He cooperated well with the technician
			- Maintained the reputation of the association
	-
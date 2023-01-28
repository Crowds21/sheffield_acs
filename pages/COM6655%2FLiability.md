public:: true
title:: COM6655/Liability

- 计算机辅助错误 Computer-aided mistakes
	- Ariane 5 explosion
	  collapsed:: true
		- 问题原因
			- Ariane 5 使用了为 Ariane4 设计的软件
			- 但是 Ariane 5 速度比 Ariane4 的速度更快,所以计算产生的数字比程序能够处理的要大
			- 导致数字溢出,进而导致程序停止
	- 放弃治疗 Radiotherapy treatment
	  collapsed:: true
		- 对6名病人进行了大量的过量辐射
		- 有时重复过量辐射，因为机器的显示屏上显示没有给出剂量
		- 经常发生故障 - 操作人员习惯于看到剂量不足的错误信息
		- 为什么有这么多的过量？
			- 制造商坚持认为错误不可能是由机器造成的。
			- 第一个病人告诉操作员她被 "烧伤 "了，但被告知这是不可能的。
		- 对软件的过度自信
	- 软件和道德方面的失败 Software and ethical failures
	  collapsed:: true
		- 大众汽车公司 2015 排放测试丑闻 
		  Volkswagen September 2015 Emissions testing scandal
			- 大众公司才有车排放的有毒气体比允许的多 40 倍
			- 柴油车的设计是为了在测试中作弊
				- 发动机软件中的程序让汽车感知到是否在测试条件下行驶
				- 如果是这样，它就会减少排放, 在全球11,000,000辆汽车中部署
			- 丑闻已使大众公司在罚款、诉讼和其他费用方面损失了333亿美元。
- 对计算机辅助错误的责任 Liability for computer aided mistakes
	- 负责任 与 责任 Accountable vs. responsible
	  collapsed:: true
		- Accountability
			- 个人或集体中,谁是合适的代理人
				- 响应
				- 提供报告
				- 入狱或支付赔偿
				- 承担内疚和悔恨(to bear guilt and remorse)
		- Responsibility
			- 角色职责
			- 社会期望
			- 因果责任 Causal responsibility
				- John failed to stop at a  stop sign and caused a car accident
			- 应受指责 Blameworthy
				- Worker who didn’t display a  “slippery road”(道路湿滑)  sign
	- Liability 责任
	  collapsed:: true
		- 责任通常是关于如何合法处理情况
		- 当某些事情发生时,谁有责任支付赔偿.
		- 法律责任(Legal liability) 通常与责任感有关(the senses of responsibility.)
		- 示例
			- 软件供应商向客户X出售软件，但在软件的功能上撒谎。X安装了软件包，但它崩溃了，并使X的业务中断了几个星期，造成收入损失。
			- 软件供应商(vendor)可能要承担责任。但X需要证明
				- 供应商不诚实，没有履行角色责任
				- 供应商对收入的损失负有因果关系
	- 计算机辅助错误责任  Liability for computer aided mistakes
	  id:: 635e612e-1446-4b8f-8f68-fe830a0c2f21
	  collapsed:: true
		- 对计算机辅助错误的责任取决于几个因素
		  collapsed:: true
			- 是否有合同
			- 软件性质
			- 该结果是否是由于计算机中的 error 引起的
			  id:: 635e6159-280f-4772-abcd-37fc9bf2bcdb
			- 使用软件的人员是否经受过充分的培训
		- 如果一个人因为计算机产品(软硬件)的缺陷而遭受损失,这些法律领域可能适用
			- 合同法 Contract law
			- 过失法[[Law of negligence]]
			- 疏忽陈述  [[Negligent misstatement]]
				- 由过失(疏忽)引起的不实陈述
			- 产品责任 Product liability ([[Consumer Protection Act]] 1987)
			  id:: 635e61cd-e40a-4a59-bb8e-23191cd405b0
	- 合同法 Contract law
		- 合同往往是最简单的补救措施.
		- 然而,由于合同的私密性( ((6358eea4-96fd-4bab-b5cc-689c35317b54)) )，只有合同的双方可以根据合同起诉
		- 如果软件是为客户编写的，这就构成了软件开发商和客户之间的服务供应合同
		- 这样的合同受 [[Consumer Rights Act]]  [2015消费者权益保护法](((6358f284-57e5-4c84-b21b-1d45cd7480b7)))（CRA）保护
			- 提供咨询的人工智能也可能属于该法案的管辖范围,因为这种软件可以被视为是提供一种服务
			  id:: 635e63e8-5d6a-4ec2-b2df-f0a10015e881
			- CRA对数字内容做出了具体规定
	- [CRA](((6358f284-57e5-4c84-b21b-1d45cd7480b7))) 和合同责任 The CRA and contractual liability
	  collapsed:: true
		- TODO 你是否记得CRA在提供服务的合同中隐含了哪些条款？
			- ((6358f985-305d-434f-82dc-64d36032a440))
		- CRA 在提供服务的合同中隐含了一个条款,即供应商必须以合理的谨慎和技能进行服务
			- 如果工银上没有采取合理的照顾,他们就违反了合同
			- "合理"(reasonable) 的定义是主观的
		- Consumer Rights Act 第 49 条规定了该内容
	- 豁免的范围 Scope of exemptions
	  id:: 635e65e7-6f1f-4d20-9621-80ae8b910a5d
		- 合同可能包括豁免条款，这些条款排除或限制了违反合同的一方的责任
		- 豁免的范围受到1977年 [[Unfair Contract Terms Act]]( [不公平合同条款法](((63594a08-1518-4ca1-ba0f-5ffa407b440c))))的限制
		  id:: 635e6625-fb4b-4fb7-b03a-c9b2d524b019
			- 因过失导致的死亡或人身伤害的商业责任不能被排除或限制
			- 在其他损害的情况下，只有在意图这样做的条款满足 "合理性 "测试的情况下，才可以排除或限制责任
			  the term purporting to do this satisfied a test of ‘reasonableness’.
			- [[Consumer Protection Act]] 规定有缺陷铲平的责任不能被排除或限制
- 疏忽 Negligence
	- Negligence imposes liability on a person who has acted carelessly.
	- 起诉"疏忽",必须具备三个基本要素
	  id:: 635e6725-b37d-4a10-a456-705ab495e4be
		- 对受害方负有注意义务
		- 违反该注意的责任(duty)
		- 间接损失,即因为违反注意责任而直接造成的损失
		  id:: 635e842f-a147-46b4-8618-331738f24ebe
	- 间接损失(consequential loss ),可能是人身或财产损失
		- 软件中的 Error 可能会造成间接损失
		  id:: 635e845f-1d6c-4e78-b7d2-6cf05c308e27
		- 硬件中的 Error 可能会直接造成损失(如触电)
		  id:: 635e846f-f25f-4b90-ac67-6b7181211b6a
		- 回忆Donoghue v. Stevenson (1932)案
	- 疏忽的影响 Negligence: implications
	  collapsed:: true
		- negligence 诉讼(action)==并不取决于合同==,这一事实具有重要影响
			- 如果一个程序是由出版商许可的,那么即使程序作者不是许可协议的一方,它也可能要承担过失责任.
			- 由于硬件制造商的疏忽而遭受损失的人,即使与经销商签订了销售合同,也可以对制造商提出疏忽索赔(have a claim in negligence against ).
	- 疏忽中的限制 Negligence: limitations
		- 必须对受害方承担注意责任(a duty of care )
		  collapsed:: true
			- 软件开发者只对那些他有理由相信可能受到任何因疏忽行为或不作为而受到不利影响的人负责.
		- 索赔人必须证明被告有疏忽 
		  The claimant must show that the defendant was negligent
		- 共同过失Contributory negligence
		  id:: 635e8778-ea88-4539-b14d-952b2931ea1a
		  collapsed:: true
			- 如果索赔人也是促成过失的因素之一,则被告人可以减少赔偿.
			- TODO 举个例子
				- 一台做工很差的电脑可能会有电气危险,但如果买房对其进行了操作,比如试图修复他,则可以根据他们对事故贡献的比例而减少损失.
	- 疏忽误报 [[Negligent misstatement]]
	  collapsed:: true
		- 就对软件提供建议而言,疏忽的责任是很严重的.
		  background-color:: #793e3e
		- 因疏忽的建议而造成的侵权行为被称作 [[Negligent misstatement]]
		- 如果决策支持系统给出的建议是错误的,那么系统的开发者可能要对接收方承担Negligent misstatement 的责任
		- 这些需要承担责任的人可能包括
			- 提供知识的专家
			- 使知识正规化的知识工程师
			- 程序员和分析员
		- 两种因素可能会导致减少甚至免受责任
			- 系统开发人对系统的使用或解释几乎没有控制权
			  (little control over the way the system is used or interpreted)
			- 可以通过加入免责声明而避免责任,该免责声明排除了咨询的法律责任
		- 注意:责任的排除受 Unfair Contract Terms Act 1977 的限制
	- 影响 decision support或人工智能系统错误 责任的因素
		- 根据合同法(contract law)和过失法(negligence law)，使用系统向客户提供建议的人可能负有责任
		- 与普通软件一样，不能仅仅因为程序有故障就避免责任
		- 为了确定是否存在疏忽，重要的是考虑使用系统的人是否合理，以建议他人依赖系统的输出
		- 是否由一个具有 对应领域且足够技能的competent professional 造成的
	- 1987 年消费者保护法 [[Consumer Protection Act]] 1987
		- 产品责任对有缺陷产品的生产者规定了责任, 具体内容在[[Consumer Protection Act]] 1987 (CPA)
		- [[Consumer Protection Act]] 保护消费者免收有问题的产品影响,导致人员或财产损失
		- 制造商和供应商有义(are obliged to)确保货物符合合同描述,适合预期目的,并且具有合理的质量,
		- ==软件不符合该法中使用的产品定义,但是他确实适用于包含软件的有缺陷的产品==.
		- [[CPA]]适用于计算机硬件
	- CPA中对于 最先进 的辩捷CPA: state-of-the-art defence
	  id:: 635e91fa-73c4-40b7-8835-f23da74cf541
		- TODO 制造商可以声称,他们不能为反应"最新设计水平"的设计或产品承担责任
		- 相关时间的科学和技术知识水平并没有达到产品生产者可能会发现缺陷的程度
		- 例如
			- 新的显示器制造商可能根据 CPA 承担责任,如果所称呼的计算机显示器的使用与 illness 之间的联系被证明
			- 旧显示器的制造商可能有一个最先进的辩护
			- 个人理解: 显示器制造商用当时该显示器处于先进水平,很多可能问题都没有被了解的理由辩护.
	- 1974年 健康与安全法案[[Health and Safety Act]] 1974
		- 涉及到工作场合的健康和安全预防措施的责任 -大部分由雇主承担
		- 违反该法是一种刑事犯罪
		- 该法还规定了设计者和制造商有责任确保设备的安全
		- 对安全关键型软件的影响
			- 如果人因为计算机控制的机器的软件错误而受伤,如果软件开发商不能证明在设计上和开发中足够谨慎,他们可能会被起诉(developers could be liable for prosecution )
	- 替代责任 Vicarious liability
	  id:: 635e96c3-4ac9-4867-89e9-f0a153125524
		- 这指的是"次要"责任
			- 雇主可能对雇员的行为负责
			- 父母可能对子女的行为负责
			- 主人可能对动物的行为负责
		- TODO 人工智能系统如何?
			- 他们本身并不"负责"或有能力支付赔偿
			- 如果系统背后有第三方,他们是否有替代责任(who? 供应商?开发者?)
	- 免除条款 [[Exemption clauses]]
	  collapsed:: true
		- disclaimer免责声明
		- 有两种类型: 免责和限制
		- 免除责任受到 1977 年的[[Unfair Contract Terms Act]]的限制. 但软件在这方面并不明确
			- 本法第2至第4条不延伸至......。任何合同，只要它涉及到创造或转让任何专利、商标、版权、注册设计、技术或商业信息或其他知识产权的权利或利益......
			- UCTA的第2至4条涵盖了违约责任、疏忽和不合理的赔偿条款( liability for breach, negligence and unreasonable indemnity clauses)
			- 回顾一下 ((635946c4-1fdb-4fc4-928d-7a467870b1bf)). 法官裁定免责条款是不合理的.
		- (Software contracts are covered by the Unfair Contract Terms Act 1977. 但是不清晰)
-
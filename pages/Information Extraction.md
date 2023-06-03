- What is Information Extraction (IE)? [[card]]
	- a practically-motivated engineering discipline (models not necessarily inspired by nature)
	- the extraction of structured information from unstructured (= textual) sources.
	- its significance is connected to the growing amount of information in text and its potential use in systems (e.g. question answering)
- ((647a24a3-f1d3-42b5-8062-f45a029c40e4)) [[card]]
	- ((647a24b2-eb4b-416a-9c73-843672998864))
- ((647a24c5-956b-4830-8bd6-79e5d0ded39c))
	- > Text Classification Example
	- Feature extraction/engineering:
		- using domain knowledge to extract features from data.
	- Feature:
		- a piece of evidence intended to help the classifier map the input to the right target class
	- Feature vector:
		- a vector $\vec{F}$ , the components $F_j=\phi_j\left(d_j\right)$ , of which are
		  results applying a feature function to the data point $d_j$.
	- Example: “Spam vrs Ham” email? (垃圾邮件和正常邮件)
		- number of “!” included in email body
		- length of the email in characters
		- occurrence of the word “cash” in the title or body.
- ((647a2548-13be-4dcb-b210-d0ef1cd491e6))
  collapsed:: true
	- Feature learning
		- automatically extract features from data - replaces manual feature engineering that is prone to human errors.
		- The use of Supervised and Unsupervised learning techniques for feature learning.
- ((647a262a-1308-4f05-b93c-49681fc48b2b))
  collapsed:: true
	- Rule-based: [[card]]
	  collapsed:: true
		- Human experts (computational linguists) write general linguistic rules and task-specific extraction rules.
		- Example, trigger keywords, regular expressions and patterns.
		- Rule-based rules are language dependent, suffer from human ingenuity, time consuming, difficult to adapt to changes.
	- ((647a2940-87ab-478d-ac24-71f2a551480c)) [[card]]
	  collapsed:: true
		- Humans (domain experts) manually annotate text spans indicating entities, relations, facts, etc. in a training corpus;
		  人类（领域专家）在训练语料库中手动注释文本片段，指示实体、关系、事实等；
		- features are manually or automatically engineered (or a mixture of the two, e.g. using neural networks and dependency trees);
		  特征可以手动或自动进行工程化（或两者的混合，例如使用神经网络和依存树）；
		- these are used to extract information that statistically correlates with classes of entities,relations, etc.
		  这些特征用于提取与实体、关系等类别统计相关的信息
- ((647a2948-85ec-4f60-8954-0127f6fedc26))
  collapsed:: true
	- 创建一个带有标注的参考语料库的黄金数据集:
	- 将黄金数据集分为三个部分:
		- 开发/训练集: 用于研究数据、训练机器学习过程，可以检查。
		- 开发测试（"devtest"）集: 不能被检查，不能用于训练；反复使用以通过将系统输出与标注进行比较来衡量系统质量的改进。
		- 测试集: 不能被检查；只在项目结束时用于最终评估运行。对于系统和开发人员来说是完全未知的数据。
	- 黄金数据集分割比例: 例如80%用于训练，10%用于开发测试，10%用于测试。
- ((647a294e-e5ed-463f-8c69-5dd7aa933314))
	- 命名实体识别（NER）通过为文本中的块分配标签来识别实体（如人物（PER）、组织（ORG）、位置（LOC）、国家（COUNTRY）、日期（DATE）和其他杂项（MISC））。
	  BIOES编码：
	- 文本：“约翰·菲茨杰拉德·肯尼迪（1917年5月29日 - 1963年11月22日），常被称为JFK和绰号Jack，是一位美国政治家，从1961年至1963年担任第35任美国总统，直到遇刺身亡。”
	- 使用类别信息的开始（B）、内部（I）、外部（O）、结束（E）和单个（S）来标注单词：
	- John（B-PER）Fitzgerald（I-PER）Kennedy（E-PER）
		- Jack（S-PER）
		- United（B-COUNTRY）States（E-COUNTRY）
		- 1963（S-DATE）
		- until（O）
	- 其他简单的方案包括BIO编码。
- ((647a295e-b734-4ff4-8c32-cec02073c71e))
- ((647a2966-f29c-4216-8a9a-00df89fd4036))
- ((647a296e-cff3-45c4-aa80-d1e3e68fc848))
- ((647a2978-b225-4234-8317-fe70e5d05946))
- ((647a380e-40ef-4218-a7d9-989e65998251))
	-
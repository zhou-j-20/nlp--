# nlp--
学习交流-根据用户的年龄、性别、学历、以及搜索的问题对用户的
1.1  项目背景
"物以类聚，人以群分"这句古语不仅揭示了物与人的自组织趋向，更隐含了“聚类”和“人群”之间的内在联系。在现代搜索引擎的个性化排序与推荐(广告)中，以物拟人，以物窥人，才是比任何大数据都要更大的前提。如何把内容精准给到需要的人，是大数据在推荐和精准营销中最核心的问题。本项目以搜索引擎中的基于行为和内容的用户画像为例，希望应用NLP技术来更细致精准地刻画用户属性。

1.2  项目简介
在现代搜索引擎的个性化排序与推荐(广告)系统中，多层级成体系的用户画像构建算法是实现精准广告投放的基础技术之一。其中，基于人口属性的广告定向技术是普遍适用于品牌展示广告和精准竞价广告的关键性技术。人口属性包括自然人的性别、年龄、学历等基本属性。

在搜索引擎中，用户通过输入具体的查询词来获取相关信息。因此，用户的历史查询词与用户的基本属性及潜在需求有密切的关系。

举例如下：

年龄在19岁至23岁区间的自然人会有较多的搜索行为与大学生活、社交等主题有关
男性相比女性会在军事、汽车等主题有更多的搜索行为
高学历人群会更加倾向于获取社会、经济等主题的信息
本题目提供用户历史一个月的查询词与用户的人口属性标签（包括性别、年龄、学历）做为训练数据，要求大家通过机器学习、数据挖掘技术构建分类算法来对新增用户的人口属性进行判定。

1.3  数据描述
1.3.1  数据集：
数据文件	备注
train.csv	带标注的训练集
test.csv	测试集
1.3.2  数据介绍
本数据来源于真实搜索引擎数据，ID经过加密，训练集中人口属性数据存在部分未知的情况。数据所有字段如下表所示：

字段说明
ID	加密后的ID
Age	0：未知年龄; 1：0-18岁; 2：19-23岁; 3：24-30岁; 4：31-40岁; 5：41-50岁; 6： 51-999岁
Gender	0：未知1：男性2：女性
Education	0：未知学历; 1：博士; 2：硕士; 3：大学生; 4：高中; 5：初中; 6：小学
Query List	搜索词列表
1.3.3  数据示例
对于train.csv中的数据记录：

ID	Age	Gender	Education	Query_List
00627779E16E7C09B975B2CE13C088CB	4	2	0	钢琴曲欣赏100首 一个月的宝宝眼睫毛那么是黄色 宝宝右眼有眼屎 小儿抽搐怎么办 剖腹产后刀口上有线头 属羊和属鸡的配吗
1.4  任务描述
本项目提供用户历史一个月的查询词与用户的人口属性标签（包括性别、年龄、学历）做为训练数据，要求大家通过机器学习、数据挖掘技术构建分类算法来对新增用户的人口属性进行判定。即对test.csv文件中的每条记录进行年龄、性别、学历的判断。

1.5  评估准则
本项目采用分类准确率进行评价。

对提供的结果文件，全部与标准结果匹配计算准确率。其中，性别、年龄、学历分别计算准确率，最终以平均准确率作为评判依据。

具体如下：

准确率计算：
其中， 表示算法对第i个样本预测类别，表示第i个样本的真实类别。函数为Indicator Function，当预测结果与真实结果完全相同时输出为1，否则为零。

𝑃=1𝑁∑𝑁𝑖=0𝕀(𝑦̂ 𝑖=𝑦𝑖)
 
平均准确率计算：
𝑃⎯⎯⎯⎯=𝑃𝑔𝑒𝑛𝑑𝑒𝑟+𝑃𝑎𝑔𝑒+𝑃education3
 
模型的判定结果不允许出现0，即只有明确的标签才为有效结果。
预设指标：平均准确率50%以上为有效成绩。

# 决策树
## 本章内容
+ 决策树简介
+ 在数据集中度量一致性
+ 使用递归构造决策树
+ 使用Matplotlib绘制树形图

__前一章所介绍的K-最近邻法可以完成很多分类任务，但是他有一个非常突出的缺点的是无法给出数据的内在含义，而决策树的主要优点就是所给出的数据形式非常容易理解。__
---
## 1. 决策树的构造
决策树：

>优点：计算复杂度不高，输出结果易于理解，对中间值的确实不>敏感，可以处理不相关特征数据。  
>缺点：可能会产生过度匹配的问题。  
>适用数据类型：数值型和标称型

>第一个问题就是，我们得决定哪个或者哪些特征在划分数据分类的时候起着决定性作用，为了找到决定性的特征，划分出最好的结果，我们必须评估每个特征。完成测试之后，原始数据集就被划分为几个数据子集。如果某个分支下的数据属于同一类型，则当前无需阅读的垃圾邮件已经正确地划分数据分类，无需进一步对数据集对数据集进行分割。如果数据子集内的数据不属于同一类型，则需要重复划分数据子集的过程。

决策树的一般流程：

> (1) 收集数据：可以使用任何方法。  
> (2) 准备数据：树构造算法只适用于标称型数据，因此数值型数据必须离散化。  
> (3) 分析数据：可以使用任何方法，构造树完成之后，我们应该检查图形是否符合预期。  
> (4) 训练算法：构造树的数据结构。  
> (5) 测试算法：使用经验树计算错误率。  
> (6) 使用算法：此步骤可以适用于任何监督学习算法，而使用决策树可以更好地理解数据的内在含义。  

一些决策树算法采用二分法划分数据，但是本书并不采用这种方法，将采用ID3算法划分数据集。划分数据集的大原则是：将无序的数据变得更加有序。我们可以使用多种方法划分数据集，但是每种方法都有各自的优缺点。在划分数据集之前之后信息发生的变化称为*信息增益*，获得信息增益最高的特征就是最好的选择。


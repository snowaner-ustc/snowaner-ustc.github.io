---
layout: post
title: 结构化
short_description: 什么是结构化，从认知理论出发人类为什么要结构化，以及LLM为什么要结构化，该如何结构化、
---

![画板](https://intranetproxy.alipay.com/skylark/lark/0/2025/jpeg/166856602/1744891733959-5118131d-404d-4949-a555-4706a9ea6a09.jpeg)







# 1. 什么是结构化
![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/166856602/1744892811943-f9b5b1db-09bd-45c7-9c15-680ff2bead7d.png)

## 1.1 什么是结构
在**《数据结构》**书中直接给出了关于结构的定义：

<font style="color:#FE0300;">数据</font>**<font style="color:#FE0300;">元素</font>**<font style="color:#FE0300;">相互之间的</font>**<font style="color:#FE0300;">关系</font>**<font style="color:#FE0300;">被称为结构</font>

关键点：“**元素**” ，“**关系**”



**不同领域中的结构的类型千差万别：**

化学领域有分子结构、晶体结构......

生物领域有细胞结构、骨架结构......

文学领域有叙事结构、逻辑结构......



并且，《数据结构》书中同时也说：“对于数据结构这个概念，至今尚未有一个被一致公认的定义，不同的人在使用这个词时所表达的意思有所不同。” 



为了在**大模型相关领域**更清晰的展示“结构”这个概念，列举一些在**大模型的输入输出**中常见的基本结构：

其中的定义不是特别严谨，仅仅是给大家一个示例

| 结构名称 | 表格 | 图 | 树 |
| :---: | :---: | :---: | :---: |
| 示例 | ![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/120256386/1744785635123-6dc2ef51-210e-407c-926d-07b17d18a611.png) | ![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/120256386/1744786806671-11a97ed2-cf46-421a-8e3c-30fdf50dec86.png) | ![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/120256386/1744786857313-c6a3ff16-9db5-4af2-852d-5b57a442504e.png) |
| 元素 | key 和 value | 节点 | 节点 |
| 关系 | key-value对应关系<br/>行列的关联 | 节点之间的连接关系 | 节点之间的父子关系（分支关系） |
| 说明 | 最常见的结构 | 不太方便用文本表述 | 可以认为是图的特例；可以用二元组的方式文本表达 |


| 结构名称 | 列表（List） | 块（chunk） | 目录 |
| :---: | --- | :---: | :---: |
| 示例 | + AAAAA<br/>+ BBBBB<br/>+ CCCCC<br/>+ ..... | ![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/120256386/1744787205824-6993666a-7710-4d7d-a84c-8aa8f2d13f59.png) | ![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/120256386/1744787222201-06e59153-c131-477f-8b99-326f0450a695.png) |
| 元素 | 数据项 | 数据块 | 目录标题，目录内容 |
| 关系 | 项之间的顺序关系 | 块之间的顺序关系 | 目录之间的隶属关系；<br/>同层级目录之间的顺序关系 |
| 说明 | 常见；简单 | 最基本的文字组织结构 | 在书等材料中常见；树的特例 |


| 结构名称 | 算法/流程 | 思维导图 |  |
| :---: | :---: | :---: | :---: |
| 示例 | ![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/120256386/1744787317364-20c401a2-2294-4a6a-9591-2050b308c03a.png) | ![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/120256386/1744787354929-0550e346-f2d9-4976-aa4b-094fee68cb8f.png) |  |
| 元素 | 输入，输出，判断.... | 中心主题、分支节点 |  |
| 关系 | 按具体算法/流程组织起来 | 节点之间的隶属关系 |  |
| 说明 | 较复杂的表达形式 | 树的特例 |  |




通过这些例子可以总结出一些**关于大模型的输入输出中常见的基本结构**的特点：

+ 目前我们研究的大模型的输入输出的重点还是文本，所以这些结构**本质上都是文本的组织结构**；
+ **各种结构之间会有很强的联系**，比如目录可以看作是树的特例等等；
+ **结构之间可以嵌套**；复杂的新结构大概率都可以分解为多个基本结构组合



## 1.2 什么是结构化
相比于“结构”的概念，“结构化”的概念则会模糊很多，也没有一个比较官方的定义。

为了更清晰地定义“结构化”，我们来通过列举来研究一下这个操作的常见输入和输出：



**“结构化”过程中常见的输入：**

+ 各种形式的长文档（比如公司的报告，新闻稿等等）
+ 书本中的内容
+ 百科（比如Wiki的一个页面）
+ 博客
+ 各种形式的对话记录（比如聊天记录，论坛帖子）
+ 大模型对生成问题的回复（Reward模型的目标）
+ 网页
+ 等等

**“结构化”过程中常见的输出：**

+ 表格（将输入的信息变为一个表格或多个表格）
+ 图（比如知识图谱）
+ 树（比如知识点构成的树，上下层是包含关系）
+ 列表（比如当知识点之间比较难聚类的时候，不如一一列出）
+ 目录（比起树，兄弟节点之间会强调顺序关系）
+ 算法（伪代码或者可以直接运行的代码，有时候也可以是流程图的描述）
+ 思维导图（视作图的特例）
+ 等等

这里可以观察到，**这些输入并不是没有“结构”**，比如书本中的内容就一定会有“目录”结构。并且哪怕是一个最简单的单个文本段落，我们也可以视其为最简单的“chunk”结构。**因此，“结构化”不能狭义的理解为让没有结构的文本变的有结构。**



同时可以看到，**输出一般都是比较简单基础的结构，很少出现如输入一般复杂的结构**（思维导图已经算是比较复杂的了）。**并且，这里说的“简单”指的是结构的定义本身，而不是具体材料内容的复杂程度**：比如，列表形式的物理公式集合的理解难度 会高于 使用思维导图的公园购票指引，尽管列表会是一种更简单的结构。**因此，“结构化”也不能狭义的理解为让输入从复杂到简单。**



综上，我们给出一个关于“结构化”的初步定义：

**选择一种结构，以这种结构来重新表述输入****中所蕴含的信息**



显然，结构化的核心要点就在于选择的“结构”：

+ **恰当的结构**也许能排除冗余信息，排除噪声，让人/模型更高效的获得目标信息
+ **不适当的结构**也许反而会增加获得目标信息的难度，甚至会丢弃关键信息

但这些只是我们直觉的猜测，我们需要实际的理论来支撑这些说法

# 2. 为什么要结构化
## 2.1 人为什么要做结构化
![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/166856602/1744892842920-c7c5b4d7-acce-489f-a1b6-32a0f426662d.png)

本节将从哲学角度的思考和对人类认知过程存在的挑战分析两个角度，说明人类为什么需要结构化，即结构化对于人类认知和信息处理的重要性。同时提供了三个认知理论作为理论支撑。

### **2.1.1 哲学角度的思考与启发**
+ <u>观点1：知识的结构化有助于 处理复杂存在实体和关系。</u>
    - 本体论<font style="color:#81BBF8;">[1]</font>强调了存在（多种类型的实体构成，如物质、精神、性质和关系）的复杂性和多样性，为认知带来了巨大挑战，要求人类识别和理解不同存在形式及其相互关系。<u>世界存在的复杂性需要简化。</u>
    - 例如，哲学家如亚里士多德和康德分别为自然界现象和知识结构提供了分类体系<font style="color:#81BBF8;">[2]</font>，但这种分类的复杂性和细节要求认知任务进行深度处理。
    - 例如，柏拉图的《理想国》及其提倡的“阶梯”<font style="color:#81BBF8;">[5]</font>强调了知识层级与系统性的重要性，认为知识应具备完整性和层次性，以便后代能够有效地继承和传播。
+ <u>观点2：知识结构化有助于 优化认知资源和知识获取方式</u>
    - 认知论<font style="color:#81BBF8;">[1]</font>揭示了知识获取的困难和限度，即人类认知资源如注意力、记忆容量和处理速度是有限的。<u>人类认知资源需要优化。</u>
    - 例如，赫伯特·西蒙的有限理性理论<font style="color:#81BBF8;">[3]</font>提到人类在复杂决策中适应性有限，影响知识处理的效率和准确性。
    - 例如，康德提出人的认知能力受到时间和空间等先验结构的限制<font style="color:#81BBF8;">[4]</font>。

人类在理解和解释世界时，基于对秩序与理解的需求和知识传递与积累的需要，结构化知识能够帮助人在这个局限内更好地组织和理解信息，使得复杂的信息变得有条理和可理解，促进人类解决复杂问题和进行创新思考。



### **<font style="color:rgb(13, 18, 57);">2.1.2 人类认知进程中存在的挑战</font>**
<font style="color:rgb(13, 18, 57);">面对海量且持续更新的信息环境，人类需要整合来自不同来源和形式的知识。这一过程不仅耗费时间和认知资源，还容易导致信息过载和认知失衡。在处理复杂的认知任务时，个体常常会出现认知偏差和误判。通过分析这一现象，我们可以看到，人类在认知世界时，持续面临着复杂信息环境带来的挑战以及自身认知资源的局限性。具体而言，人类认知世界的挑战主要体现在以下三个方面：</font>

1. **认知资源有限：**<font style="color:rgb(13, 18, 57);">人类的认知资源，如注意力、工作记忆和处理能力，都是有限的。这意味着在面对大量信息和复杂任务时，容易产生认知过载，难以有效地处理和储存所有相关数据。</font>

<font style="color:rgb(13, 18, 57);">哈佛大学心理学家乔治·米勒的研究表明</font><font style="color:#81BBF8;">[6]</font><font style="color:rgb(13, 18, 57);">：人类短期记忆的容量有限，大多数人一次能够处理的有效信息项目（被称为记忆单位/记忆组块）大约在7±2个之间。</font>

> <font style="color:rgb(13, 18, 57);">记忆单位/组块：组块是将多个信息元素组合成更大整体以简化记忆和处理的心理策略。比如对于初次接触和记忆的信息，一次最多处理5～9个汉字/词语/阿拉伯字母。</font><font style="color:rgb(25, 25, 25);">超过这个范围就可能会记不牢。</font>
>

2. **信息理解能力有限**：<font style="color:rgb(13, 18, 57);">尽管人类有较强的感知能力和经验知识，面对并处理具有多样性和复杂性的信息或新知识时，全面理解依然显得困难。</font>
3. **逻辑整合能力有限**：<font style="color:rgb(13, 18, 57);">面对多维信息和复杂问题时，人类的逻辑剖析和整合能力是有限的，进行系统化分析和综合判断是具有难度的。</font>

> **<font style="color:rgb(102, 102, 102);">References: </font>**
>
> <font style="color:rgb(102, 102, 102);">[1] 谢丽娜,韩正彪,李赞梅.情报学对信息的理解与运用:本体论和认识论视角[J].情报资料工作,2011,(04):30-35.</font>
>
> <font style="color:rgb(102, 102, 102);">[2] 朱光亚.从形而上学到现象学:哲学为科学奠基[J].电子科技大学学报(社科版),2013,15(05):58-63.DOI:10.14071/j.1008-81052013.05.009.</font>
>
> <font style="color:rgb(102, 102, 102);">[3]李莉.赫伯特·西蒙“有限理性”理论探析[D].苏州大学,2007.</font>
>
> <font style="color:rgb(102, 102, 102);">[4]杨斯斐.时间与空间的主观性:康德二律背反的基础[J].大理学院学报,2015,14(07):54-57.</font>
>
> <font style="color:rgb(102, 102, 102);">[5]何怀宏.人性结构问题：对《理想国》439E-440A的分析与引申[J].道德与文明,2024,(05):47-56.DOI:10.13904/j.cnki.1007-1539.2024.05.010.</font>
>
> <font style="color:rgb(102, 102, 102);">[6] Miller A G ,陆冰章 ,陆丙甫 .神奇的数字7±2:人类信息加工能力的某些局限[J].心理学动态,1983,(04):53-65.</font>
>



基于上述挑战和思考分析，我们不由得提出一个问题，**<u>应如何整合或处理多样复杂的知识或信息，促进人类的认知限度提升和对信息的全面理解和分析？</u>**

**<u></u>**

知识的结构化处理为我们提供了一种解决途径。结构化知识让信息更易于搜索、理解和应用，帮助个体识别和抽取关键信息，过滤冗余数据，并清晰地展示信息间的关系。这种方法不仅增强了信息的可操作性和记忆性，还促进了知识的建构和应用，最大化利用有限资源，促进更全面的理解，从而改善了决策过程及创新能力。

同时，幸运的是，已有相关研究理论为 知识结构化解决这些认知挑战的可行性和必要性 提供了有力支撑：

+ **认知负荷理论（Cognitive Load Theory）**<font style="color:#81BBF8;">[7-8]</font>**：**适当知识结构化**减少过多的信息负担**，提高信息处理效率。
    - 例子：小明解数学题时，过于复杂的题干信息或冗余的解题步骤，会阻碍小明完成正确作答。
+ **认知匹配理论（Cognitive Fit Theory）**<font style="color:#81BBF8;">[9-10]</font>**：**知识结构化可以**优化信息呈现形式，使之与任务类型的匹配**，方便快速理解。
    - 例子：小明在做科学实验时，会用图表记录数据。图表与实验数据的匹配能帮助他快速判断趋势，减少理解和使用信息的混乱。
+ **元认知理论（Metacognition Theory）**<font style="color:#81BBF8;">[11]</font>**：**知识结构化有助于**分解信息逻辑**，识别任务所需知识和应用知识所需的方法论，提高解决或决策效能
    - 例子：小明学习蛋炒饭的制作，需要将教程信息识别两方面内容：准备蛋炒饭的主要原料（任务所需知识）和复制蛋炒饭制作步骤（应用知识的方法论）。

> **<font style="color:rgb(102, 102, 102);">References: </font>**
>
> <font style="color:rgb(102, 102, 102);">[7] John Sweller. Cognitive load during problem solving: Effects on learning.</font>
>
> <font style="color:rgb(102, 102, 102);">[8] Paul Chandler and John Sweller. Cognitive load theory and the format of instruction.</font>
>
> <font style="color:rgb(102, 102, 102);">[9] Iris Vessey. Cognitive fit: A theory-based analysis of the graphs versus tables literature.</font>
>
> <font style="color:rgb(102, 102, 102);">[10] Narayan S. Umanath and Iris Vessey. Multiattribute data presentation and human judgment: A cognitive fit perspective.</font>
>
> <font style="color:rgb(102, 102, 102);">[11] Zhuoqun Li, Hongyu Lin, Yaojie Lu, Hao Xiang, Xianpei Han, and Le Sun. Meta-cognitive analysis: Evaluating declarative and procedural knowledge in datasets and large language models.</font>
>



接下来提供对上述三个认知理论的具体分析。

### 2.1.3 认知理论
#### 1）认知负荷理论
**理论背景**：认知负荷理论（Cognitive Load Theory）<font style="color:#81BBF8;">[7-8]</font>是心理学和教育学中的一个重要理论，研究人类在任务执行过程中所承受的认知负载。

**核心内容**：理论强调人类认知资源总量是有限的。越多的认知资源消耗在整理材料/知识之间的逻辑关系上，那么用于学习或者解题的认知资源越少。

**负荷类型**：该理论区分了三种类型的认知负荷：内在负荷、外在负荷和相关负荷。

1. **内在负荷（Intrinsic Load）**：*任务本身的复杂性决定的认知负担
    - 例子：比如解数学题任务的难度，复杂的思考步骤本身就是挑战，需要深度专注和努力。
2. **外在负荷（Extraneous Load）**：由信息呈现和材料组织方式带来的额外负担
    - 例子：比如混乱的教材排版<font style="color:rgb(139, 139, 139);">，</font>可能分散学习者的注意力。
    - 同时，原论文提供了一个实验作为辅助理解的例子 --【辅助理解外部认知负荷的实验】
3. **相关负荷（Germane Load）**：帮助构建知识结构的有效认知努力。这种负荷有助于学习并应得到强化。
    - 例子：比如总结知识点和经验的过程，通过对知识图式的构建和整合。



【辅助理解外部认知负荷的实验】<font style="color:#81BBF8;">[7]</font>

在工业培训场景下（入厂培训），选择两组刚刚加入的电子厂学徒（有基本的能力和一定的经验），给他们内容相同但结构不同的学习材料自学，同样的时间后通过考试分析他们的学习情况

+ 传统组（Conventional）：使用传统的教学材料，很多时候图片和对应解读是分开的
+ 修改组（Modified）：修改后的教学材料（**所有文字和图片相同**，但整体结构经过整合和调整，图片和对应的文本会在物理上整合在一起）

原始的材料示例：

![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/120256386/1744084992693-853a8f49-a2f9-4a66-8281-b5810f76751f.png)

修改后的教学材料示例：

![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/120256386/1744085005612-d4715364-1160-4940-8350-d0c0c25d58c9.png)

**结果：**可以看到，在各项测试中，包括笔试和实操测试，<u>修改组的分数显著高于传统组（笔试组约提升68.3%～69.3%，实操组约提升58.3%～157.1%）</u>。其中M指代分数均值（画框），SD为方差。



![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/166856602/1744961600918-ed00b67a-5d52-44b0-badd-06c9c7dcd8e8.png)

**和认知负荷理论匹配**：修改后的材料大大降低了学习的外在负荷，为学习留下了更多的认知能力。

**结论：**合理的知识结构化和呈现方式可以优化认知负荷，支持更有效的信息吸收和应用。



**知识结构化对于缓解认知负荷的重要性分析：**

1. **简化内在负荷：**将复杂问题分解为更易处理的小任务
    - 例子：将复杂的乐高模型分解成几个小部分，逐步完成，降低难度。
    - 例子：按逻辑或主题对知识进行分类和组织，可使原来复杂的内容更易于消化和学习。
2. **减少外在负荷：**优化信息呈现方式，使学习者集中精力于核心内容
    - 例子：使用清晰的乐高说明书，步骤分明，孩子不需要费心整理步骤，专注拼装。
3. **增强相关负荷：**图式知识体系的构建，帮助学习者提升解决问题的模式识别能力
    - 例子：孩子学会按颜色或形状分类积木，形成系统的方法，提高效率。
    - 例子：专家与新手处理问题的方式（见下方）

**缓解认知负荷的有效方案--知识的结构化：**

**（提供一个例子说明 -- 专家与新手的差异）**

+ 一个实例：国际象棋，摆出一个真实棋局中的棋盘状态，让专家/新手看5秒，然后要求他们尽可能回忆看到的棋盘状态。
    - 专家的表现会明显优于新手
    - 但如果棋盘状态不是真实棋局中的状态，而是完全随机乱摆的状态，专家和新手的表现之间没有显著区别
    - 这表明<u>专家的优势不是由于一般的短期记忆因素</u>
+ 专家与新手的差异在处理问题的方式中的体现<font style="color:#81BBF8;">[7]</font>。
    - 专家的做法：往往根据问题涉及的具体知识点进行分组。
        * 比如，专业物理学家会将所有能够通过基本物理原理（如能量守恒定律）解决的问题归入同一类别。
        * 反映了他们归纳和运用图式知识的能力。图式作为一种认知结构，可以有效地帮助问题解决者识别问题状态及其相关步骤，从而优化问题解决流程。
    - 新手的做法：通常依据问题的表面特征对问题进行分类。
        * 例如，所有提到斜面的问题可能被归入一组。
        * 依赖于易于观察的表面关系，而不是深层次的概念或原理。
+ **分析差异背后的原因**
    - 专家：通过积累复杂的图式知识体系来优化认知过程，将问题解决简化为识别和应用已知模式，从而降低了信息处理的复杂性和认知负荷。
    - 新手：缺乏这种图式知识，更多依赖直观关系，增加了信息处理复杂性和认知负荷，未能利用深层知识结构简化解决过程。
    - 同时，米勒<font style="color:#81BBF8;">[6]</font>通过组块的概念阐释<u>新手和专家的差别</u>：
        * 人类的短期记忆可以处理的信息容量为5-9个组块之间。
        * 例如，一个人可能需要100个组块存储某信息，而另一人可能仅需一个组块。组块中包含的信息量取决于个体对信息的接触时间
        * 如果在某个领域达到专精的程度，那么就可以把更多的信息整合成一个组块。

**总结：知识结构化不是仅仅对信息的整理，更是对复杂认知任务的处理简化和资源优化。**



#### 2）认知匹配理论
**核心内容**：信息的呈现方式和结构应与人类认知过程或决策任务类型相匹配<font style="color:#81BBF8;">[9-10]</font>。

**为什么需要认知匹配**：由于人脑是能力有限的信息处理器，当任务环境中复杂度降低时，会导致问题更有效地被解决。针对不同的任务类型使用匹配的知识呈现形式（图形或表格），有助于降低任务和问题的理解难度。

**认知匹配理论的具体应用和场景**：基于graph和table的特定决策场景

+ **insight**
    - 人类认知任务的类型可划分为<u>空间任务</u>和<u>符号任务</u>。
        * 空间任务：强调感知数据之间的关系
        * 符号任务：强调提取离散的数据值。
    - 信息的不同呈现方式
        * graph表示强调<u>空间信息</u>，适合整体评估数据的关系。
        * table表示强调<u>符号信息</u>，适合精确数据提取。
    - 当信息的呈现形式与人类认知任务类型相匹配时，会<u>导致更快、更准确的问题解决</u>。
+ **具体例子**：图形更适合空间任务，而表格更适合符号任务。

| **任务** | **任务类型** | **数据呈现形式** |
| --- | --- | --- |
| 构建学术论文引用链 | 空间任务 | graph |
| 绘制财务报表 | 符号任务 | table |
| 描述社交实体关系 | 空间任务 | graph |
| 整理家庭收支记录 | 符号任务 | table |


+ （Limitation）对复杂任务的讨论：对于更复杂的决策任务，认知匹配理论可能不完全适用，因为这些复杂任务可能涉及多层级子任务和多策略。



**基于认知匹配理论的问题解决通用范式的分析**<font style="color:#81BBF8;">[9-10]</font>**：**

+ 模型将<u>问题解决的过程</u>视为<u>知识呈现形式</u>与<u>待解决任务表示</u>之间关系的结果。
+ <u>心理表征</u>：人类利用先验经验，将呈现的信息与任务需求相匹配，认知信息和任务解决相整合的过程，主观能动地思考和决策。

![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/166856602/1744804682879-1724b416-1560-428c-a4c8-43d78ce28f0b.png)（原论文提供图中文字叙述需要加强理解和拓展，见下方修改图）



![画板](https://intranetproxy.alipay.com/skylark/lark/0/2025/jpeg/166856602/1744970417761-cf66afc6-2d1d-4cce-9efb-cc3aa2a54bde.jpeg)

+ 理解认知匹配：当信息呈现形式和任务表示相匹配，决策者会形成与此信息类型相匹配的信息处理流程/心理表示，实现有效且高效的解决问题表现。
+ **拓展思考**：<u>认知匹配</u>与<u>认知负荷</u>理论建立联系（图中虚线标明）。
    - 实际上知识呈现对应外在负荷，待解决任务表示对应内在负荷，人类认知到解决的处理流程对应相关负荷。
    - 当知识呈现与任务表示相匹配时，问题解决的复杂度大大降低，（心理表征处）人类保留了更多的认知资源用于解决任务。【（外在负荷+内在负荷）⬇️，相关负荷⬆️】



#### 3）元认知理论
**核心内容**：人类认知中起关键作用的两种知识：陈述性知识（declarative knowledge）& 程序性知识（procedural knowledge）。前者用于解决“知道是什么”的问题，后者用于解决“知道如何做”的问题。<font style="color:#81BBF8;">[11]</font>

+ **<font style="color:rgb(13, 18, 57);">陈述性知识（Declarative Knowledge）</font>**<font style="color:rgb(13, 18, 57);">：</font>关注于对事实、概念和事物的识别和界定。
    - <u>“知道是什么”</u>
    - 例如，知道法国的首都是巴黎或理解重力概念，都是陈述性知识的体现。
+ **<font style="color:rgb(13, 18, 57);">程序性知识（Procedural Knowledge）</font>**<font style="color:rgb(13, 18, 57);">：</font>涉及如何执行操作、解决问题的步骤和技术。
    - <u>“知道如何做”</u>
    - 例如，知道<u>如何</u>演奏乐器或游泳，或是其他需要按步骤指示完成的任务，都是程序性知识的体现。

**为什么需要元认知理论支撑知识的呈现：**

个体需要具有对自己的认知过程的认知。元认知理论可以帮助学习者根据“知道是什么”和“知道怎么做”两条逻辑，有效识别和调整自己的学习策略，运用和优化知识体系。

+ “知道是什么”使学习者掌握完成任务所需的全部事实知识
+ “知道怎么做”帮助学习者掌握应用知识的方法论。

决策任务<u>需要区分任务所需的基本信息，和应用该信息所需的方法论</u>。从逻辑层面对知识进行剖析和解构，确保知识不仅被识别，还能被有效转化为决策效能。



**总结：基于上述思考分析和三大理论支撑，不难发现，知识的结构化对于人类认知尤为重要。不仅可以优化认知资源的利用，减少信息处理负担，还能促进信息理解和逻辑整合能力的提升。**

> **<font style="color:rgb(102, 102, 102);">References: </font>**
>
> <font style="color:rgb(102, 102, 102);">[7] John Sweller. Cognitive load during problem solving: Effects on learning.</font>
>
> <font style="color:rgb(102, 102, 102);">[8] Paul Chandler and John Sweller. Cognitive load theory and the format of instruction.</font>
>
> <font style="color:rgb(102, 102, 102);">[9] Iris Vessey. Cognitive fit: A theory-based analysis of the graphs versus tables literature.</font>
>
> <font style="color:rgb(102, 102, 102);">[10] Narayan S. Umanath and Iris Vessey. Multiattribute data presentation and human judgment: A cognitive fit perspective.</font>
>
> <font style="color:rgb(102, 102, 102);">[11] Zhuoqun Li, Hongyu Lin, Yaojie Lu, Hao Xiang, Xianpei Han, and Le Sun. Meta-cognitive analysis: Evaluating declarative and procedural knowledge in datasets and large language models.</font>
>
> <font style="color:rgb(102, 102, 102);">[12] Parag Jain, Andreea Marzoca, and Francesco Piccinno. STRUCTSUM generation for faster text comprehension.</font>
>
> <font style="color:rgb(102, 102, 102);">[13] Li Z, Chen X, Yu H, et al. Structrag: Boosting knowledge intensive reasoning of llms via inference-time hybrid information structurization[J]. arXiv preprint arXiv:2410.08815, 2024.</font>
>
> <font style="color:rgb(102, 102, 102);">[14] Wang, Jinyu, et al. "PIKE-RAG: sPecIalized KnowledgE and Rationale Augmented Generation." arXiv preprint arXiv:2501.11551 (2025).</font>
>
> <font style="color:rgb(102, 102, 102);">[15] Wu, Shirley, et al. "Stark: Benchmarking llm retrieval on textual and relational knowledge bases." Advances in Neural Information Processing Systems 37 (2024): 127129-127153.</font>
>
> <font style="color:rgb(102, 102, 102);">[16] Guo, Zirui, et al. "Lightrag: Simple and fast retrieval-augmented generation." (2024).</font>
>
> <font style="color:rgb(102, 102, 102);">[17] Huang, Chensen, et al. "Recurrent context compression: Efficiently expanding the context window of llm." arXiv preprint arXiv:2406.06110 (2024).</font>
>
> <font style="color:rgb(102, 102, 102);">[18] Liu, Kai, et al. "Educating llms like human students: Structure-aware injection of domain knowledge." arXiv e-prints (2024): arXiv-2407.</font>
>
> <font style="color:rgb(102, 102, 102);">[19] Jain, Parag, Andreea Marzoca, and Francesco Piccinno. "Structsum generation for faster text comprehension." arxiv preprint arxiv:2401.06837 (2024).</font>
>

## 2.2 LLM为什么要做结构化
![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/166856602/1744892874828-8ad2ae6f-75b9-42b0-a931-0d661f989ea0.png)

**人类认知进程对LLMs发展的启发**<font style="color:#74B602;"></font>

1. **知识获取能力和语言能力**：人类认知的过程通过感知、选择、记忆和推理来掌握并处理信息。

> LLMs虽然不具备人类的感知能力，但通过在大规模语料库进行预训练，学习语言表示和深层语义结构，具备了广泛的世界知识、强大的上下文理解和生成能力。
>

2. **知识整合和聚焦的能力**：人类通过将先验经验和获取的知识转化为图式结构，可实现根据任务要求快速地聚焦重要的知识内容并拓展应用。

> 例如，GraphRAG<font style="color:#81BBF8;">[13][16]</font>范式面向查询聚焦摘要任务或知识密集型推理任务，通过构建图式知识体系并检索最相关的部分，用于回复需要整合多个知识来源类型的问题。
>

3. **逻辑推理与决策能力**：人类基于自身的先验经验和知识处理能力，在面对复杂问题或决策任务时，通过信息整合和逻辑推理做出合理决策。

> 例如，现有LLMs基于思维链推理实现模仿人类的step-by-step地思考和问题分析，面对复杂决策问题，通过任务分解、自我反思和multi-agent协作推理来提升表现
>



### 2.2.1 知识结构化对于LLMs的重要性分析
主要从LLMs的以下几点现存挑战进行分析。受认知理论（认知负荷理论、认知匹配理论、元认知理论）启发，知识结构化同样为以下问题提供了可行的解决思路。

+ **缓解长文本理解能力不足**
    - 关键问题：LLM的上下文窗口受计算资源限制，难以有效整合和利用分散在多段落中的关联信息<font style="color:#81BBF8;">[17]</font>。
    - 解决思路：对外部检索文档内容或长文本内容进行结构化组织，优化知识资源并强调语义关联性，减少冗余并加强理解。【对应认知负荷理论--降低外在负荷】
    - 例子：STRUCTSUM<font style="color:#81BBF8;">[19]</font>利用大语言模型将长文本语料转化为知识结构。
+ **突破领域知识瓶颈**
    - 关键问题：LLM的通用预训练数据难以覆盖动态、专业的领域知识（如医学、法律、金融），且参数化知识更新成本高<font style="color:#81BBF8;">[13-14][18]</font>。
    - 解决思路：结构化知识增强的领域推理，为此提供了可行的解决方案。【对应认知负荷理论--降低外在负荷】
    - 例子：StructRAG<font style="color:#81BBF8;">[13]</font>将外部语料文档构建为结构化知识，促进知识密集型推理任务；StructTuning<font style="color:#81BBF8;">[18]</font>通过结构感知的知识注入策略构建特定域专家LLM，显著减少了训练语料的需求。
+ **优化任务适配能力**
    - 关键问题：LLM对任务需求与知识类型的匹配缺乏理解和判断，导致通用模型在特定场景表现欠佳<font style="color:#81BBF8;">[13]</font>。
    - 解决思路：构建任务-结构映射【对应认知匹配理论】；简化或分解任务需求【对应认知负荷理论--降低内在负荷】
    - 例子：StructRAG<font style="color:#81BBF8;">[13]</font>提出应当根据查询任务类型和知识文档所属场景匹配最适合的知识呈现结构。
+ **实现动态知识更新**
    - 关键问题：LLM参数化知识更新需全模型微调，成本高且易引发灾难性遗忘。
    - 解决思路：构建结构化知识库，支持知识检索和动态更新<font style="color:#81BBF8;">[15][16]</font>。【对应认知负荷理论--降低外在负荷】
    - 例子：LightRAG<font style="color:#81BBF8;">[16]</font>将外部知识文档构建为可检索的结构化知识库，能快速适应数据并动态更新。



### 2.2.2 实验佐证知识结构化对于LLM的重要性
【认知负荷实验】

#### 1）长文本+QA任务中常见的问题：当输入的材料过长或过于复杂，较弱的模型（可以认为整体认知能力较差）无法识别到关键信息
实验：同一组材料和问题，gpt4o成功识别到了关键信息，而Phi-3.5-mini失败了。

与认知负荷理论对应：输入的材料过长或过于复杂代表其认知负荷（外部负荷）较高，当模型较弱时（认知能力）无法承担这样的负荷。

![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/166856602/1744873978192-551cf058-ee3f-434f-a756-d76dd9c2b0cc.png)



#### 2）来自STRUCTSUM<font style="color:#81BBF8;">[12]</font>：结构化信息降低了认知负荷，提高了人类的解题速度
实验操作统计人类来在给定不同的内容时（结构化内容、结构化内容+原材料、仅有原材料）回答问题的平均消耗时间（题目比较简单，acc都是100）

结果：回答问题的速度在这些结构化信息的加入下提高了，尤其是在只有结构化内容时会更快。

![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/120256386/1744103636355-781d20ce-27ec-489c-ba2a-94c1e91af6e0.png)

与认知负荷理论对应：结构化信息降低了认知负荷，提高了人类的解题速度。并且在进一步的只有结构化信息的情况下，进一步减小了认知负荷（排除冗余信息），进一步加快速度



【认知匹配实验】

#### 3）来自StructRAG<font style="color:#81BBF8;">[13]</font>：不同材料/任务具有不同的最适合结构，使用单一固定类型的结构无法同时在各个不同任务上取得良好的性能。
消融实验：相比于使用路由模型（即根据具体材料内容选择一个最适合的目标结构），使用一种固定结构进行知识构造，会带来巨大的性能下降。

![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/166856602/1744964156812-ef725536-aa79-41b7-bd4d-e72c6e37d092.png)

与认知匹配理论对应：不同的任务/材料有不同的适宜结构



【元认知理论实验】

#### 4）来自MCA<font style="color:#81BBF8;">[11]</font>：程序性知识/陈述性知识/综合知识分别作为提示进行测试，综合知识情况下任务完成最好。
在32个公开可用的大语言模型和13个涵盖不同类型任务（包括数学、常识和推理）的评估数据集上进行了实验。

> 这里的得分是指：
>
> 在给定的数据集-模型pair中，定义$e_o$是原始（无知识情况）的错误率，$e_p$是给定程序性知识后的错误率，则程序性知识得分为$score_p=\frac{e_o-e_p}{e_o}$；陈述性知识得分$score_d$和综合知识得分$score_c$同理
>

结论：回答的得分情况，在大多数任务中，同时利用两种知识，在大多数任务中会带来明显的收益提升【整体比较，黄色框】。陈述性知识的收益大于程序性知识的收益【蓝色框】。程序性知识的收益仅在与简单逻辑推理任务相关的任务中大于陈述性知识。【红色框】。

![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/166856602/1744278764121-b6613687-e74a-4ebd-9de7-22a34bbd527c.png)

这与元认知理论相符：令LLM同时具有任务所需事实信息（陈述性知识），并掌握应用知识所需的方法论（程序性知识），会提升决策效果。



**总结：三大认知理论在LLM发展中的支撑作用，以及结构化知识的价值体现**

| **认知理论支撑** | **LLM现存挑战** | **结构化知识价值体现** |
| --- | --- | --- |
| 认知负荷理论 | 长文本信息过载 | 压缩冗余信息，降低处理复杂度 |
| 认知匹配理论 | 信息呈现形式与任务场景不匹配 | 定义或学习 任务-适配结构的映射 |
| 元认知理论 | 对知识与任务的逻辑关系感知不足 | 掌握"知道是什么"和“知道怎么做” |




> **<font style="color:rgb(102, 102, 102);">References: </font>**
>
> <font style="color:rgb(102, 102, 102);">[7] John Sweller. Cognitive load during problem solving: Effects on learning.</font>
>
> <font style="color:rgb(102, 102, 102);">[8] Paul Chandler and John Sweller. Cognitive load theory and the format of instruction.</font>
>
> <font style="color:rgb(102, 102, 102);">[9] Iris Vessey. Cognitive fit: A theory-based analysis of the graphs versus tables literature.</font>
>
> <font style="color:rgb(102, 102, 102);">[10] Narayan S. Umanath and Iris Vessey. Multiattribute data presentation and human judgment: A cognitive fit perspective.</font>
>
> <font style="color:rgb(102, 102, 102);">[11] Zhuoqun Li, Hongyu Lin, Yaojie Lu, Hao Xiang, Xianpei Han, and Le Sun. Meta-cognitive analysis: Evaluating declarative and procedural knowledge in datasets and large language models.</font>
>
> <font style="color:rgb(102, 102, 102);">[12] Jain, Parag, Andreea Marzoca, and Francesco Piccinno. "Structsum generation for faster text comprehension." arxiv preprint arxiv:2401.06837 (2024).</font>
>
> <font style="color:rgb(102, 102, 102);">[13] Li Z, Chen X, Yu H, et al. Structrag: Boosting knowledge intensive reasoning of llms via inference-time hybrid information structurization[J]. arXiv preprint arXiv:2410.08815, 2024.</font>
>
> <font style="color:rgb(102, 102, 102);">[14] Wang, Jinyu, et al. "PIKE-RAG: sPecIalized KnowledgE and Rationale Augmented Generation." arXiv preprint arXiv:2501.11551 (2025).</font>
>
> <font style="color:rgb(102, 102, 102);">[15] Wu, Shirley, et al. "Stark: Benchmarking llm retrieval on textual and relational knowledge bases." Advances in Neural Information Processing Systems 37 (2024): 127129-127153.</font>
>
> <font style="color:rgb(102, 102, 102);">[16] Guo, Zirui, et al. "Lightrag: Simple and fast retrieval-augmented generation." (2024).</font>
>
> <font style="color:rgb(102, 102, 102);">[17] Huang, Chensen, et al. "Recurrent context compression: Efficiently expanding the context window of llm." arXiv preprint arXiv:2406.06110 (2024).</font>
>
> <font style="color:rgb(102, 102, 102);">[18] Liu, Kai, et al. "Educating llms like human students: Structure-aware injection of domain knowledge." arXiv e-prints (2024): arXiv-2407.</font>
>
> <font style="color:rgb(102, 102, 102);">[19] Jain, Parag, Andreea Marzoca, and Francesco Piccinno. "Structsum generation for faster text comprehension." arxiv preprint arxiv:2401.06837 (2024).</font>
>



### 2.2.3 关于未来工作的见解
+ 大语言模型LLM的快速发展为高效构建各种知识结构奠定了基础
+ 知识结构化有助于帮助LLMs采用类似人类的思维过程，在推理过程中将零散信息转换为各种结构格式，从而更好地服务于各种知识密集型推理任务
+ LLMs在专业领域内knowledge-intensive问答时遇到知识不足的问题，有望通过外部输入结构化领域知识，实现可观的性能提升
+ 如何针对不同任务、不同应用场景，自适应地生成迎合知识类型和任务需求的结构化构造指令或规划，可能需要进一步研究。



# 3. 要如何结构化
![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/166856602/1744892895863-07c0bd58-fa35-4b6a-93ab-8994c334ade0.png)





接下来我们来看现有的一些相关工作都**选择了哪些“结构”（3.1）**，**如何进行“结构化**”（3.2），且“结构化”为自己的任务带来了多少增益（3.3）**。

## 3.1 现有的工作使用的“结构”
+ 结构化相关工作目前并不成体系，很多工作里可能都有类似的思路，这里只是给出部分简单的介绍以提供一些insight。

| 工作名称缩写 | 团队 | 具体任务 | 被结构化的输入的类型 | 目标“结构” |
| --- | :---: | --- | :---: | :---: |
| GraphRAG [1] | 微软 | 长文本+QA | 播客、各个领域的长知识文档 | Graph |
| <font style="color:rgb(25, 27, 31);">StructRAG [2]</font> | 国科大、阿里 | 长文本+QA | 播客、各个领域的长知识文档 | Table，Graph，Algorithm，Catalogue，Chunk |
| StruXGPT [3] | 浙大、阿里 | 长文本+QA | 各个领域的长知识文档/预训练文档 | 一个特定的3层目录结构：<br/>（1） Scope：概括主题<br/>（2） Aspect：进一步细分<br/>（3） Description：详细的描述 |
| STRUCTSUM [4] | 谷歌 | 长文本+QA | 各个领域的长知识文档（WIKI40B） | 表格、思维导图 |
| ToRA [5] | 清华、微软 | 数学推理解答 | 数学问题的解答过程 | 代码（算法） |
| CodePlan [6] | 清华、蚂蚁 | 推理问题解答 | 推理问题的解答过程 | 伪代码（算法） |
| LMUnit [7] | Contextual AI，斯坦福 | Reward Model 评分 | RL中policy模型的回答 | 一系列的不同角度的评估回答质量的问题（列表） |
| DeepSeek GRM [8] | DeepSeek | Reward Model 评分 | RL中policy模型的回答 | 一系列回答质量评分原则（列表） |


总结

+ 这里的结构化的输入类型大致可以分为3类：
    - **1，对长文本/文档进行结构化**
        * 主要特点：整体较长；回答问题需要的信息散落在文本的各个部分，混杂在其他无关信息中
        * 是最常见，<u>且最符合我们直觉的“结构化”操作应用场景</u>。
        * <u>表格和图</u>（包括类似的树/目录）是最常见的目标结构
    - **2，对推理问题的解答过程进行结构化**
        * 主要特点：	逻辑性强；但基本没有和问题无关的信息
        * <u>算法</u>是最常见的目标结构
        * Reasoning问题的回答的逻辑性和有序性<u>天生和算法结构的特性匹配</u>。
    - **3，对RL中policy模型的回答进行结构化（对普通问题的回答进行结构化）**
        * 主要特点：形式多种多样；但基本没有和问题无关的信息
        * 结构化目标是获得一系列能评估回答的问题/标准
        * 可以理解为“<u>有约束</u>”的结构化：<u>只重新表述与评估回答的角度相关的这部分信息</u>

Insight：

+ 如这里展示的一样，“结构化”的应用场景不局限于传统长文本结构化。
+ 目标结构要**适应具体任务和输入材料的特点**
    - 比如，对长文本/文档进行结构化时，主要目标是排除冗余信息，避免**信息过于离散**和**非标准化表达**对知识提取的影响，此时使用表格和图。
    - 对推理问题的解答过程进行结构化时，输入中没有多少冗余信息，核心目标是检查其中的解答逻辑，因此使用算法结构。
    - 而对普通问题的回答进行结构化时，由于其形式多种多样，并且当前目标是多角度评估回答质量，因此使用最通用的列表结构，且“<u>有约束</u>”的结构化，只结构化评估相关的信息。



> [1] From Local to Global: A GraphRAG Approach to Query-Focused Summarization
>
> [2] STRUCTRAG: BOOSTING KNOWLEDGE INTENSIVE REASONING OF LLMS VIA INFERENCE-TIME HYBRID INFORMATION STRUCTURIZATION
>
> [3] Enhancing LLM’s Cognition via Structurization
>
> [4] STRUCTSUM Generation for Faster Text Comprehension
>
> [5] ToRA A Tool-Integrated Reasoning Agent for Mathematical Problem Solving
>
> [6] CodePlan: Unlocking Reasoning Potential in Large Language Models by Scaling Code-form Planning
>
> [7] LMUnit: Fine-grained Evaluation with Natural Language Unit Tests
>
> [8] Inference-Time Scaling for Generalist Reward Modeling
>

## 3.2 现有的工作“结构化”的方式
| 名称缩写 | 具体任务 | 被结构化的输入的类型 | 为什么要“结构化” | “结构化”具体方法 |
| --- | --- | --- | --- | --- |
| GraphRAG | 长文本+QA | 播客、各个领域的长知识文档 | <font style="color:rgb(25, 27, 31);">传统RAG基于embedding（类似关键词搜索）的搜索精度差：</font><br/><font style="color:rgb(25, 27, 31);">“就像翻阅一本食谱书一样。使用关键字搜索“炒鸡蛋”或“西红柿鸡蛋面”并找到说明，它速度很快，对于简单的问题非常有效。</font><br/><font style="color:rgb(25, 27, 31);">但是，如果你对这些菜肴背后的文化背景或是想知道为什么某些成分能够协同作用增加风味感兴趣，仅仅关键字搜索可能就显得力不从心。例如，西红柿和鸡蛋为何能搭配得如此完美？这可能和一些化学原理有关。”</font> | 在任务开始前的索引阶段，提前处理现有文档成为一系列图谱（图结构）：1，先将文档切分为文本块，2，然后提取一系列实体关系（可以理解为一系列“主谓宾”陈述句，“主”“宾”以“谓”联系起来），3，根据这些关系构建<font style="color:rgb(25, 27, 31);">图结构的知识图谱。4，根据现有的图谱的语义信息，将有相似语义的图谱聚合起来，成为一个“社区” 5，最后，为每一个社区生成描述，方便接下来的查询</font><br/><font style="color:rgb(25, 27, 31);">实际使用的查询阶段会根据问题本身的语义信息和各个社区的描述进行匹配，一步步找到具体的图谱的某一部分，辅助最后的回答。</font><br/>![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/166856602/1744808475995-5372ba57-a4c8-4427-8ffb-0c1f77e860db.png) |
| <font style="color:rgb(25, 27, 31);">StructRAG</font> | 长文本+QA | 播客、各个领域的长知识文档 | “参考人类思考流程：人<font style="color:rgb(77, 77, 77);">类通常不会局限于简单阅读散乱的原始内容，而是会将这些信息信息汇总成结构化知识，再利用这些结构化信息进行思考推理。”</font> | 首先**使用一个路由模型从5个结构中选择出一个目标结构**，然后再使用Prompt + LLM对输入的文档进行结构化。结构化后内容辅助长文本+QA任务。（减少外在负荷）<br/>同时，还尝试对当前问题进行进一步拆解，变成一个个小问题来回答（减少内在负荷）<br/>路由模型可以是Prompt+大LLM，也可以是一个经过DPO训练的7b小模型。<br/>DPO数据构建方法：同时用5种结构化内容分别辅助来回答当前问题，使用LLM来判断哪种结构结果最好，最好的结构作为DPO数据的chosen response，其他结构作为rejected response。<br/>![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/120256386/1744795488662-d473e200-15e3-4ee5-9e06-2844e85ce604.png) |
| StruXGPT | 长文本+QA | 各个领域的长知识文档 | “模拟人类的认知过程，将简单的、连续的文本句子转化为有序的、层次化的知识结构。” | 使用Prompt+LLM或者一个专门训练的小模型，将输入的文档变为一个特别设置的3层目录结构。结构化后内容代替原材料辅助解决QA任务。<br/>![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/120256386/1744795472134-b0fd43cb-e643-4a98-b42c-0fcae1670255.png)<br/><br/>同作者的另一篇论文研究的就是在训练阶段引入结构化内容：<br/>![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/120256386/1744948420927-ae5af419-084b-49fb-bd09-c361aabee6d7.png)<br/>+ 模型会在训练的过程中时刻都在回顾整个知识结构，且建立了当前知识与结构的强联系<br/>+ 在提到相关知识时，模型可以快速回忆起结构，并根据结构快速的回忆更多的相关知识<br/>+ 还有一点可能是更好的“注入”：CPT使用的数据在知识点层面可能是不全面的，那么在CPT时以以上结构形式进行训练，比如结构中一半的结点是原有的知识点（但CPT数据集里没有），一半是CPT新加入的知识点，模型能很快的构建起新知识点和老知识点之间的联系 |
| STRUCTSUM | 长文本+QA | 各个领域的长知识文档（WIKI40B） | “输入信息过多，虽然能够基于文本响应用户查询，但往往无法以易于理解的方式充分构建和组织这些信息。这可能导致信息处理瓶颈，阻碍用户有效地从文本中提取有意义的洞察。” | 表格：（a）首先将输入文本根据语义和主题划分为多个文本段落（b）然后使用 Prompt + LLM，为每个小段落单独生成一个表格和标题。<br/>![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/120256386/1744097383543-31c5ea2c-ce3d-47c3-bf03-3a455fa5d558.png)<br/>思维导图：迭代式（a）生成一个中心概念作为根节点（b）在每次迭代中，使用few shots+LLM，决定是进一步扩展当前思维导图还是停止迭代。（c）如果选择扩展，使用few shots+Prompt，向选择的节点添加分支。<br/>![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/120256386/1744097597727-22b22dd9-9cae-4f0e-9104-f31322c6e589.png) |
| ToRA | 数学推理解答 | 数学问题的解答过程 | “自然语言适用于语义分析、规划和抽象推理（例如常识推理），但在精确计算、符号操作和算法处理方面存在困难。相反，代码擅长严谨的操作，可以将复杂的计算外包给方程求解器等专用工具。” | 结构化主要出现在训练数据构建过程中。使用fewshot+Prompt+LLM为现有数学问题先生成自然语言形式的rationale解答，然后再对应生成代码形式的回答。<br/>构建的数据会用来训练模型，让模型生成可以通过生成代码和rationle并调用工具运算来回答数学问题。<br/>![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/120256386/1744799951011-8453c814-b846-4c41-8f68-e268bdb8476b.png) |
| CodePlan | 推理问题解答 | 推理问题的解答过程 | “代码结构能有效地捕捉复杂推理所固有的丰富语义和流程步骤” | 结构化主要出现在训练数据构建过程中。Prompt+代码LLM 对现有的question-response pair 使用python代码形式来重新描述response的逻辑。<br/>构建的数据会用来训练模型，让训练后的模型可以通过先生成代码来辅助回答推理问题。<br/>![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/120256386/1744795526634-6b9d9e6a-e130-4d18-ac42-22dcd8588528.png) |
| LMUnit | Reward Model 评分 | RL中policy模型的回答 | “直接使用RM模型或prompt的 LLM 来评分将会把包含很多细节包含很多方面的评估压缩为不透明的粗粒度指标，难以解释或控制。” | 结构化主要出现在RM框架评估response质量时。使用Prompt+LLM为输入的question-response pair 生成一系列能从各个角度评估response质量的单元问题。<br/>![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/120256386/1742971238304-8bcede40-5e84-4be3-a4cd-fd0d69e85a9c.png) |
| DeepSeek GRM | Reward Model 评分 | RL中policy模型的回答 | “在一般的领域，奖励生成（指RL过程中为response给出reward）更具挑战性，因为奖励标准更加多样化和复杂，并且通常没有明确的参考或基本事实。” | 结构化主要出现在RM框架评估response质量时。使用Prompt+训练好的生成式RM为输入的question-response pair先生成一系列评分的原则和每个原则的权重。<br/>![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/120256386/1744191649394-1469d384-334e-4a95-8853-23ecd21cba5e.png) |




Insight：

+ 可以看到，**Prompt+LLM是最常见的结构化方法**，很多时候不需要微调就已经能有很好的效果，这代表实现有效的结构化的门槛不会很高
+ 整体来说，**结构化相关工作目前并不成体系**，结构化涉及的方法互相之间没有太多的继承和相关关系，大家都有自己的讲故事思路，有时候甚至不解释就直接引入结构化的思路。这也一定程度上有点“殊途同归”的意味，也代表进行结构化是符合人类的认知的正确目标。
+ 目前，除长文本+QA任务外，其他领域的涉及结构化的方法都**不是“直接”的结构化**，而是**结合在数据构建或推理过程等其他方面上**，这提示我们在自己的任务中应用结构化时不要局限自己的思路

## 3.3 现有的工作的“结构化”应用场景和效果
其中的提升具体数字有的是相对提升（baseline较多基本水平不一致）有的是绝对提升。

| 工作名称缩写 | 被结构化的输入的类型 | 目标“结构” | 具体任务 | “结构化”相比不结构化的实际提升效果 |
| --- | --- | --- | --- | --- |
| GraphRAG | 播客、各个领域的长知识文档 | Graph | 长文本+QA | 在Graph结构的RAG效果相比于传统RAG整体性能提升了26%-52%。<br/>![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/166856602/1744808227596-f0f75bb3-2c41-47f5-87d4-f7c0e9ce9e97.png) |
| <font style="color:rgb(25, 27, 31);">StructRAG</font> | 播客、各个领域的长知识文档 | Table，Graph，Algorithm，Catalogue，Chunk | 长文本+QA | 相比于不使用结构化，结构化后整体效果相对提升了5%-15%。<br/>而如果错误的使用了结构化（不使用router的结果而是随机指定一个结构来结构化，原始数据在最后QA时不会使用），效果反而会相对降低10%-25%<br/>![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/120256386/1744359929023-dd3703af-d2cf-4b8a-9b2a-00b18e97316c.png) |
| StruXGPT | 各个领域的长知识文档 | 一个特定的3层目录结构：<br/>（1） Scope：概括主题<br/>（2） Aspect：进一步细分<br/>（3） Description：详细的描述 | 长文本+QA | 加入结构化后，长文本+QA的性能整体提升了2%-4%（绝对提升）<br/>![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/120256386/1744800485893-ed32592b-e7bc-4f05-9bc3-fbd8b5dfa252.png) |
| STRUCTSUM | 各个领域的长知识文档（WIKI40B） | 表格、思维导图 | 长文本+QA | 相比于只使用原始输入材料，加入结构化后的知识人类解题的速度快了大概10%-20%，而如果只使用结构化后的知识，人类解题速度甚至会快30%-40%。<br/>![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/120256386/1744103636355-781d20ce-27ec-489c-ba2a-94c1e91af6e0.png) |
| ToRA | 数学问题的解答过程 | 代码（算法） | 数学推理解答 | 相比于只使用自然语言来回答，使用结构化的代码形式来辅助回答会有极大的增益（相对提升20%-30%，也包含post training带来的影响）<br/>![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/120256386/1744799593867-f8e118af-b52f-4d88-b65d-087240e25ab0.png) |
| CodePlan | 推理问题的解答过程 | 伪代码（算法） | 推理问题解答 | 相比于只使用自然语言来回答，使用结构化的代码形式来辅助推理回答会有极大的增益（相对提升10%-20%，也包含post training带来的影响）<br/>![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/120256386/1744799837970-708c6e08-ce96-47b7-ab22-72ff57b828f3.png) |
| LMUnit | RL中policy模型的回答 | 一系列的不同角度的评估回答质量的问题（列表） | Reward Model 评分 | 整体会有2%的增益（绝对提升），也包含post training带来的影响<br/>![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/120256386/1744799470632-b3994661-abe6-480e-911a-389bf5cbf91f.png) |
| DeepSeek GRM | RL中policy模型的回答 | 一系列回答质量评分原则（列表） | Reward Model 评分 | 训练前的LLM：加入“原则”生成大概会有2-6%的绝对增益<br/>![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/120256386/1744185549768-b3ed5066-9bdf-4da1-8802-65f84d0c6bd7.png)<br/>而对训练后的生成式RM：“原则”生成大概会有2%的绝对增益<br/>![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/120256386/1744266653819-f01d088f-089d-475f-9c60-b1503b690e33.png)<br/>![](https://intranetproxy.alipay.com/skylark/lark/0/2025/png/120256386/1744266653819-f01d088f-089d-475f-9c60-b1503b690e33.png) |


Insight：

+ “结构化”带来的增益还是普遍的
+ 哪怕同样是长文本+QA任务，**不同的材料/问题也会有不同的更适合的目标结构。自适应的结构选择很重要**
+ “结构化”可以成为一个与其他方法完全正交的方法，可以是额外带来的增益
    - 比如对自己的任务的某一个步骤的阶段性输出进行结构化，然后将结构化内容附回到输出上，当作一个额外的总结





# 4. 总结
+ 我们首先从“结构”和“结构化”的定义出发，列举了一些在我们现在的语言大模型相关任务中常见的输入输出种类
+ 然后，我们对人类为什么需要结构化和LLM为什么需要结构化进行了深刻分析，并提供了三大认知理论作为支撑。
    - 三大认知理论在LLM发展中的支撑作用，以及结构化知识的价值体现

| **认知理论支撑** | **LLM现存挑战** | **结构化知识价值体现** |
| --- | --- | --- |
| 认知负荷理论 | 长文本信息过载 | 压缩冗余信息，降低处理复杂度 |
| 认知匹配理论 | 信息呈现形式与任务场景不匹配 | 定义或学习 任务-适配结构的映射 |
| 元认知理论 | 对知识与任务的逻辑关系感知不足 | 掌握"知道是什么"和“知道怎么做” |


+ 最后，我们总结了一系列有关“结构化”的相关工作，提供了一些关于如何应用“结构化”到自己任务上的insight：
    - 目标结构的选择要依赖于当前的**任务种类/具体目标/数据类型**等等，**自适应的选择结构会是更好的方案**
    - “结构化”的应用场景并不局限，可以只是整体流程中的一个小的子目标，和已有方法有机结合
    - “结构化”应用的门槛并不高，大多数时候Prompt+LLM就能取到不错的效果
+ 不仅是结构化，在LLM越来越像人的当下，**研究人类的认知科学领域的相关工作成为了一个巨大的宝藏**
    - 理论的概念都并不晦涩
    - 相关的认知科学实验并不难理解，并且都很有意思（如工业培训的实验）


+ 从LLM的角度，预训练做信息压缩的过程就像是在做知识结构化，后训练是任务认知的匹配
    - **预训练**：将输入知识进行“结构化”，整体地组织成一个蕴含知识的结构
    - **后训练**：构建相关知识的“索引”方式
+ 对我们工作的启示：从人作为输出者的角度，先结构化信息，再匹配听众；讲不清楚一个东西，哪怕补充10句100句反而是在增加认知负荷
    - 一定要**为自己的输出提前做好结构化**，否则单独的补充说明不会起到效果
    - 结构化的具体方式要**依赖于“听众”**：判断我们是在给同行介绍还是小学生介绍，会有不同适宜的结构
+ 对我们工作的启示：从人作为输入者的角度，学习大佬、最前沿的知识观点，**结构化整个领域的先验知识作为语言**。
    - 在研究一个领域时多多调研，在自己心中构建一个关于该领域知识的结构
    - 此时如果有新idea，此时可以快速对应到结构上的位置，做到心里有底，快速理解
    - 在有一个比较完整的结构后，新方向或许也可以从结构中的特征意识到（比如意识到知识树上的某一个分支好像缺了一部分，或许就是未被重视的研究方向）
+ **警惕过度结构化**，结构化只是一个中间结果，做好结构化的目的是为了更快地拿到更好的结果
    - 当前我们是比较缺乏定义当前的结构化输出到底好不好的指标的
    - 结构化一定要为我们的目标服务，不能为了结构化而结构化
    - 动态结构化也是一个很好的方向：根据当前的情况来实时更新当前结构化内容，适用于agent等要和环境时刻交互的框架




# Open-Pass

👏College of Software and Microelectronics, Peking University final exam conference and materials collection.

**注意：以下内容仅供参考，抱佛脚不可取，好好学习才是王道！**



## 通识课

### 自然辩证法概论

- 考试30个选择题，背知识点就完了，特别是总结的地方多看看👇

- 知识点总结：✍[自然辩证法](https://github.com/JackHCC/PKU-Lessons-Summary/blob/master/Introduction_to_Dialectics_of_Nature/README.md)



## 集成电路专业

- 受众范围：集成电路，电子通信，集成电路实验班专业

- 资料与参考链接：👉[集成电路专业部分课程资料与汇总](https://github.com/JackHCC/PKU-Lessons-Summary)

### 嵌入式微处理系统

#### 21年考题回忆

- 选择30个，每个1分，
  - 一些容易忽视的点，程序优化，处理器各种模式（例如Sleep）等，其他的都是正常的题
- 填空30个，每个1分，给寄存器和内存，各种指令执行的结果填空
- 简答题，两个，每个10分，一个startup.s（作用？如何进到main函数？），一个SWI（判断程序对错？其中一条指令什么作用？）
- 代码题20分，改写函数，OpenMP十分，CUDA十分，这次考的二维数组sum求和，用reduction

#### 参考资料

- [往年参考](ICmbedded)
- [知识点](https://blog.creativecc.cn/posts/Embedded-Microprocessor-System.html)
- [复习总结](https://github.com/JackHCC/Embedded-Microprocessor-System-Homework/tree/master/Review)

### 集成电路设计

#### 21年考题回忆

参考链接：👉[带图片定位知识点](https://github.com/JackHCC/Digital-Integrated-Circuit-Design/blob/master/9.Practice/README.md)

- 名词解释（10分）

  - VCD：波形记录数据库、
  - RTL：寄存器传输级
  - SDF：标准延时格式
  - Strong：Verilog默认的信号强度
  - 设计规则约束

- 根据给定逻辑画电路图（8分）

  - 具体是高性能编码风格那一节的if分支语句的电路图.程序应该是下面这个样子

  ```verilog
  module mod(
  	input wire a,b,c,
  	input wire s1,s2,
  	output	o);
  	
  	always @(*) begin
  	if(s1)
  		o = a;
  	else if(s2)
  		o = b;
  	else 
  		o = c;
  	end
  endmodule
  ```

- 根据电路图写逻辑和时序specify，具体电路时一位的加法器（12分）

  - 题目给了每个输入到输出的延时，写specify延时语句

- Wire Load Model计算电阻电容（8分）

  - 很容易忽视！给定fanout，求解电阻R和电容C

- FIFO实现，基于一个给定的memory（20分）

  - 作业题，考试要写的时16\*4的FIFO，需要对给的32\*8memory参数重载

- 检测序列111（20分）

  - 状态机，课上练习那个，有一点稍微改动

- cmp判断大小器件实现，先写1位，再用generate写8位cmp（10分）

  - 具体就是比较A和B两个数大小，有三个端口G，E，L，分别表示A大于B，A等于B，A小于B，一位的模块需要输入一位Ai，Bi，和上一位传来的Gi，Ei，Li，输出这一位计算的Go，Eo，Lo。大概逻辑是：

  ```
  Go = Gi || (Ei & (Ai > Bi));
  Eo = Ei & (A == B);
  Lo = Li || (Ei & (Ai < Bi));
  ```

  - 其次根据一位的写8为的CMP来判断八位A和B大小

- 给电路图和d触发器代码，求输入输出延时和时钟最高频率（12分）

  - 很容易忽视！大概逻辑综合那一章

**总结：回归上课ppt很重要，时序考的很多，19年卷子仅是参考，光靠老师给的参考卷子肯定不行，不然就寄了，还是要看课本内容！**

#### 参考资料

- [往年参考](ICC_Design)
- [知识点](https://blog.creativecc.cn/posts/embedded-ic-design.html)
- [复习总结](https://github.com/JackHCC/Digital-Integrated-Circuit-Design/blob/master/9.Practice/README.md)

### 集成电路导论

- 课程不考试，交三次大作业就行

### 集成专业英语

#### 21年考题回忆

- 听力填空：一篇文章挖十个空，听力放三遍，填词（10分）
- 单词填空：共给出15个课本中的重点单词选择（25分）
  - 根据单词的释义选单词，十个题（10分）
  - 根据给出的单词以合适的形式填空，10个空（15分）
- 课本Task选择题，共15题，重点最后一单元的Critical Think内容，出了五题（15分）
- 课文句子翻译，四个英译汉，每个四分，一个汉译英，两分（18分）
- 阅读理解，阅读两页A4纸，一共1000词左右，六个问题（9分）
- 写作，都跟上面的阅读有关（23分）
  - Summary，对阅读理解内容总结，4到5句话（8分）
  - Critical Writing，批判性写作（15分）

#### 参考资料

- [单词例句](https://github.com/JackHCC/PKU-Lessons-Summary/blob/master/English/README.md)



## 软件工程专业

[ ] Todo



## 金融科技专业

### 金融工程概论

#### 21年考题回忆

一、请在1.1与1.2中选择一个问题进行回答（15

1.1 回忆期货与远期的定价过程，并尝试回答如下问题：

1. 是投资资产的远期合同价格（F2）满足BSM方程，还是投资资产远期合同的价值（f）满足BSM方程？为什么？（5
2. 在国债期货中，空头方可以选择具体的交割债券，因此，用于结算的资产并不唯一。那么，国债期货是否可以利用BSM方程定价？如果你认为可以，请给出定价思路；如果你认为不可以，请给出理由。（10

1.2 请回忆中航油陈久霖先生的故事，你认为可以从中学到什么？

二、请在2.1与2.2中选择一个问题进行回答（15

2.1 在一个标准利率互换交易中，请思考如下问题

1. 在课堂讲授中，此类互换交易可以用哪两种方法进行定价？这种定价所得到的互换合同价值是什么？（5
2. 此类互换交易是否可以利用BSM方程并定价？如果你认为可以，请给出定价策略，并讨论这种估值方法所得到的结果是否是一种合适的定价方法；如果你认为不可以，请说明理由（10

2.2 请回忆香港在97年金融危机中遇到的各种问题，回答你从中学到了什么？

三、请在3.1与3.2中选择一个问题进行回答（20

3.1 在一个二叉树模型中，请思考如下问题

1. 如何在单步二叉树中给出金融衍生品的定价（5
2. 如何利用二叉树模型给一个美式期权定价？如果用计算机实现这个定价过程，你能否给出一个简单的伪代码来说明你的思路？（10
3. 如何对上述定价过程中的误差进行修正？（5

3.2 回忆中信泰富荣智健先生的故事，回答你从中学到了什么？

四、请在4.1与4.2中选择一个问题进行回答

4.1 题面未知

1. 对于该种资产的某个衍生品f，其价格变动的模型Δf(s)应该是什么（7
2. 所有以该资产为标的资产的衍生品f，其价格应该满足某个类似BSM方程的偏微分方程，你能写出来吗？（6
3. 所有以该资产为标的资产的衍生品f是否也满足风险中性定价原理？请说明原因（6

4.2 让我们来看一些有趣的问题，看您能否给出解决问题的思路。

1. 如果有两个资产构成了一个资产组合，且知道两个资产在T时刻的价格S_1^T^和S_2^T^为随机变量，都服从标准正态分布，相关系数为μ。该资产组合有一种衍生品，在T时刻，当S_1^T^>1且S_2^T^<0时，衍生品价值为1；其他情况下，衍生品取值为S_1^T^-S_2^T^。请问，如果您有计算机的话，您将如何估算这个衍生品在T时刻的价值？（可写出您打算采用的算法的伪代码）（10

五、认真阅读《十四五规划》《中国制造2025》等规划类文件，请在此基础上判断什么产业有较大的发展空间。结合自身特点，阐述你应该如何从这些产业中获得价值。（30

**解答**：[一些练习](https://github.com/JackHCC/PKU-Lessons-Summary/blob/master/Financial_Engineering/README.md)

#### 参考资料

- [知识点](https://blog.creativecc.cn/posts/financial-engineering.html)
- [题目解答](FTE)



# Contributors

- [JackHCC](https://github.com/JackHCC)

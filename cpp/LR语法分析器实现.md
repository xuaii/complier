# 标准LR(1)语法分析器实现

## 1. 接口定义

1. LR语法分析程序(算法p160)
   - [x]  符号栈的弹出k个符号
   - [x]  符号栈压入一个符号
   - [x]  获取栈顶元素
   - [x]  访问LR语法分析表
2. 增广文法的LR(1)项集族算法(p167)
   - [x]  遍历（满足·右边第一个是终结符）的所有项
   - [x]  遍历G‘中每一个以某个符号的所有产生式
   - [x]  遍历FIRST（？？）的所有终结符号
   - [x]  为项集添加一个项
   - [x]  项集初始化为空集
   - [x]  遍历项集簇的每个项集
   - [x]  遍历每个文法符号
   - [x]  判断某个集合是否在项集簇中
   - [x]  判断项集是否为空
   - [x]  添加项到项集簇中
3. LR语法分析表构造算法(p169)
   - [x]  遍历项集簇的项集I_i和对相应的状态号i
   - [x]  遍历项集的每一个项
   - [x]  遍历是否为非终结符
   - [x]  获取·右边第一个符号（如果为空返回特殊标志）
   - [x]  判断符号是否为空
   - [x]  比较两个非终结符是否是同一个（比较ID即可）
   - [x]  GOTO表构造
4. FIRST、FELLOW集合计算（p140）
   - [x] 符号是否是开始符号
   - [x] 符号是否是结束符号
   - [x] 遍历一个产生式的所有非终结符位置
   - [x] 集合是否包含某个元素
   - [x] 获取产生式最后一个非终结符
   - [x] 计算两个集合的差，计算两个集合的并
   - [x] 初始化Fellow集合
   - [x] 预计算所有FIRSYT（a），a是单一符号



### 第二阶段目标（编译器任务目前就是这些了， 之后的东西不需要了！！）

1. 优化分析表构造性能（主要是项集簇的构造）
2. 实现语法树的绘制（使用现代UI）
3. 实现语法树节点的语义功能（自定义函数ID）通过注册函数的方式
4. 美化代码（保证语义不变的情况下删除冗余，调整格式，简化实现）

tips：其中2，3两点可以分为 树结构， 树遍历，Unity可视化树（分为结构和数据，使用json保存）

其中，树的结构和语义功能一起实现！为每个产生式添加一个语义函数ID， 然后做一个由ID到函数列表地址的映射， 函数在一个.h文件里单独实现， 需要处理的是函数参数德问题， 毕竟c++中函数参数是固定的！！




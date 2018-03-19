## 代码的编译和执行

以var a  = 1为例

* 编译
  * 编译器查找作用域中是否有一个a变量
  * 存在：忽略该声明，继续编译
  * 否：在作用域中定义一个a变量
  * 编译器将var a = 1，这个代码片段编译成用于执行的机器命令
* 执行
  * 检查作用域中是否有该变量
  * 存在：使用该变量
  * 否：继续查找该变量
  * 最终找到变量，则赋值
  * 没有找到，报错



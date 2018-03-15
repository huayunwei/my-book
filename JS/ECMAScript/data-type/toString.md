## toString方法

* ### undefined和null没有
* ### boolean类型返回对应的字符串形式，即true/false
* ### string类型，返回原值
* ### number类型

  * \(number\).toString：返回数值的字符串形式

  * \(number\).toString\(2/8/10/12/16\)：参数为进制，返回number对应进制的字符串形式
* ### function类型

  * ### 自定义函数：返回函数源码
  * ### 内置函数：函数代码以\[native code\]显示
* ### array类型：返回以逗号链接数组每一项的字符串
* ### date类型：表示当前时区的时间字符串
* ### RegExp类型：返回正则表达式字面量的字符串表示
* ### Error类型：同内置函数的返回




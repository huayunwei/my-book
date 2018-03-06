## 严格模式

### 作用

* 消除js语法的一些不合理、不严谨、不安全问题，减少怪异行为并保证代码运行安全
* 提高编译器效率，增加运行速度

### 使用

* 整个脚本启用严格模式，在顶部执行：use strict
* 在指定函数中执行严格模式，在函数第一行：use strict

* 不支持strict模式的浏览器把use strict当做一个字符串执行，支持的将开启严格模式

* 浏览器兼容性：IE10+,Firfox4+、safari12+、opera12+、chrome

### 规则

* 变量

  * 不允许不定义就直接赋值的变量
  * 不能对变量调用delete操作符

* 对象

  * 不能为只读属性赋值
  * 不能为不可配置的属性使用delete操作

* 函数

  * 参数不能重复

  * 修改形参不会反应到arguments中

  * 不允许使用arguments.callee和arguments.caller

* 不允许eval在包含上下文中创建变量或函数

* 不允许使用eval和arguments作为标识符，不允许读写他们的值
* 不允许this值为null或undefined
* 不允许使用with语句
* 不允许使用八进制字面量




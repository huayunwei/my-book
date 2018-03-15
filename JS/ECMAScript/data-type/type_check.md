## 类型判断

* ### typeof

  * 用法：typeof xxx

  * 返回：小写字符

  * 识别

    * 可以识别标准类型：Number，String，Boolean，undefined（null为object），Object

    * 不能识别除函数之外的具体对象类型
* ### instanceof

  * 用法：xx instanceof type

    * xx不是对象，返回false

    * type不是函数，返回TypeError

  * 返回：true/false

  * 识别

    * 可以识别内置对象类型，自定义类型及其父类型

    * 不能识别标准类型，返回false

    * 不能识别undefined、null
* ### constructor

  * 用法：xx.constructor

  * 返回：function 数据类型\(\){}

  * 识别

    * 可以识别标准类型、内置对象类型、自定义类型

    * 不能识别undefined、null，因为没有属性
* ### Object.prototype.toString

  * 用法：Object.prototype.toString.call\(xxx\)

  * 返回：字符串 \[object type\]

  * 识别

    * 所有标准类型和内置对象类型

    * 不能识别自定义类型




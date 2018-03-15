## 类型判断

* ### typeof

  * 用法：typeof xxx

  * 返回：小写的类型字符串

  * 识别：

    * 可以识别基本类型：undefined、number、string、boolean、object（null为object类型）

    * 不能识别具体的对象类型
* ### instanceof

  * 用法：xxx instanceof type

    * xxx如果不是对象，返回false

    * type如果不是函数，返回TypeError

  * 返回：true/false

  * 识别：

    * 不能识别标准类型，返回false

    * 不能识别undefined、null

    * 可以识别内置对象类型、自定义类型、及其父类型
* ### constructor

  * 用法：xxx.constructor

  * 返回：xxx的构造函数

  * 识别：

    * 不能识别undefined、null

    * 可以识别标准类型、内置对象类型、自定义类型
* ### Object.prototype.toString

  * 用法：Object.prototype.toString.call\( xxx \)

  * 返回：\[ object type  \] 字符串

  * 识别：

    * 可以识别所有标准类型和内置对象类型

    * 不能识别自定义类型

  * 为什么一定要用Object原型链上的toString方法，而不能直接调用

    * 其他对象上的该方法可能被重写
* ### inArray

  * 用法：Array.inArray\(xxx\)

  * 返回：true/false

  * 识别：只能识别数组




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

  * 
* ### Object.prototype.toString

  * ### 
* ### inArray

  * 用法：Array.inArray\(xxx\)

  * 返回：true/false

  * 识别：只能识别数组




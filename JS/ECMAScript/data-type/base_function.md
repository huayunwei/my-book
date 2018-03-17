## Function

* ### 定义

  * 函数声明语句

    * 函数的重复声明，后面的会覆盖前面的

    * 如果函数和变量的名一致，因为在提升中变量优先级高于函数，所以函数处于后面，会覆盖变量

  ```
  function funcname(){}
  ```

  * Function构造函数

    * 参数1到n-1都是函数的参数

    * 第n个参数作为函数的函数体

  ```
  var funcname = new Function(参数，函数体)
  ```

  * 函数定义表达式

    * name属性：紧跟在function后面的标识符，没有则为空，IE11-无效，为undefined

  ```
  var funcname = function(){}

  //fun只能在内部使用，而外部的调用需要使用funcname
  var funcname = function fun(){}
  ```

* ### 参数

  * arguments：保存所有传入的参数
    * arguments.length：传入参数的个数
    * arguments.callee：指向拥有该arguments对象的函数，严格模式下会报错
    * arguments.caller：始终为undefined
  * 参数传递
    * 基本类型值：将值赋值给一个局部变量，该局部变量的名字和参数名一致
* ## 内部属性

  * caller：保存调用当前函数的函数的引用，全局调用时，返回null，严格模式下报错




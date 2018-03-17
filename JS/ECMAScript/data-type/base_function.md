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






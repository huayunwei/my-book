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
    * 引用类型值：将内存地址赋值给局部变量，该局部变量值的改变会影响到外部传入的参数的值
* ## 属性

  * caller：保存调用当前函数的函数的引用，全局调用时，返回null，严格模式下报错
  * length：函数定义的形参的个数
  * name：总是获取function后面的标识符，如果没有则为空（ES5，ES6中会返回函数实际的名字）
  * prototype：原型属性，指向一个原型对象
* ## 方法

  * apply：

    * 作用：在特定上下文环境下执行函数

    * 使用：fn.apply\(context，arr\)

    * 参数：

      * 参数1：作用域

      * 参数2：参数数组，传入给fn函数的参数

  * call：

    * 作用：在特定上下文环境下执行函数

    * 使用：fn.call\(context，arg1，arg2，。。。。\)

    * 参数：

      * 参数1：作用域

      * 参数2-..：参数，传入给fn函数的参数

  * toString，toLocalString：返回函数代码的字符串

  * valueOf：返回函数本身

  * bind：IE8-不支持

    * 作用：将函数绑定到某个对象

    * 使用：fn.bind\(obj\)

    * 参数：

      * 参数1：对象

      * 参数2-...：调用函数传入的参数

    * 返回：一个新的函数，当调用这个函数时，会作为传入参数的属性来调用
* ## ES6的函数

  * 参数默认值
    * 函数.length：返回没有指定默认值的参数个数，不包括...reset参数

    ```
    function fn(x=3){console.log(x)};//3
    ```
  * reset参数：即...变量名，用于获取全部传入的 参数，保存在变量名中
  * 箭头函数：
    * 形式

  ```
  fn()=>{}
  ```






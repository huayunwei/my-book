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
* ## 高阶函数

  * 定义：

    * 操作函数的函数：函数作为参数被传递或函数作为返回值输出

  * 函数柯里化
* ## 函数节流（throttle）和函数防抖（debounce）

  * 函数节流：对于连续的函数执行，转变成固定时间执行一次

    * 1.使用时间戳

    ```
    //获取当前的时间 - 上一次执行的时间，如果小于设置的时间，则不执行，否则执行
    function throttle(fnc,wait){
        var context,args;
        var previous = 0;
        return function(){
            var now = +new Date();
            context = this;
            args = arguments;
            if(now - previous > wait){
                func.apply(context,args);
                previous = now;
            }
        }
    }
    ```

    * 2.设置定时器

    ```
    //设置定时器，如果定时器存在，则不执行，到时间后，执行函数，清空定时器
    function throttle(fnc,wait){
        var timeout,args,context;
        var previouse = 0;
        return function(){
            context = this;
            args = arguments;
            if(!timeout){
                timeout = setTimeout(function(){
                    timeout = null;
                    func.apply(contxt,args);
                },wait);
            }
        }
    }
    ```

  * 函数防抖：将被执行的函数使用setTimeout延迟一段时间执行

    * 1.只要当前函数没有执行完，任何新出发的函数都不会忽略

    ```
    function debounce(method,context){
        if(method.tId){
            return false;//不执行新函数
        }
        method.tId = setTimeout(()=>{
            method.call(context);
        },1000);
    }
    ```

    * 2.只要有新触发的函数，立即停止执行当前函数

    ```
    function debounce(method,context){
        clearTimeout(method.tId);
        method.tId = setTimeout(()=>{
            method.call(contxt);
        },1000);
    }
    ```
* ## 惰性函数

  * 作用：函数执行的分支只会在函数第一次调用的时候执行，第一次执行成功后，函数会被覆盖成另一个合适的方式执行函数
  * 本质：函数重写

  ```
  function a(){
      console.log('a');
      a = function(){//a在第一次被执行后会被覆盖成该函数
          console.log('a1')
      }
  }
  ```

  * 




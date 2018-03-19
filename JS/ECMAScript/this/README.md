## this

* 指向window
  * 函数独立调用
  * 全局下的this
  * 闭包
* 指向直接对象，即紧邻着方法的对象
  * 以方法来调用
  * 容易出现的问题
    * 函数别名：将函数赋给其他变量

    ```
    function foo(){console.log(this);}
    var obj = {foo:foo}

    obj.foo();//obj

    var bar = obj.foo;
    bar();//此时函数是在全局环境下执行的，即this是绑定为window的
    ```

    * 参数传递
    * 内置函数
    * 间接引用
    * 其他情况
* 间接调用
  * 使用call，apply，bind
* new 调用




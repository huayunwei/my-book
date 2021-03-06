## this

* 指向window
  * 函数独立调用
  * 全局下的this
  * 闭包
* 指向直接对象，即紧邻着方法的对象

  * 以方法来调用，使用方法直接调用时，即后面接（）时，才会指向对象，如果不执行就不一定了
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

    ```
    function foo(){console.log(this);}
    var obj = {foo:foo}

    function bar(fn){
        fn();
    }
    bar(obj.foo);//window
    ```

    * 内置函数

    ```
    var obj = {foo:foo}

    setTimeout(obj.foo,100);//window
    ```

    * 间接引用

    ```
    function foo(){console.log(this.a);}
    var obj = {foo:foo};
    var obj1 = {a:1};

    (obj1.foo = obj.foo)();//这个时指向window的！
    ```

* 间接调用

  * 使用call，apply，bind
  * map，filter，some，every，forEach

* new 调用

  * 没有返回值，this指向实例

  * 有返回值，this指向返回值

* 严格模式下，全局环境下this是指向undefined的

### this绑定优先级

new &gt; 间接调用 &gt; 方法调用 &gt; 全局



### 箭头函数

this始终指向外层函数的this指向




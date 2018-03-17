## 对象

* ### 对象定义

  * 一个复合值

  * 属性的无序集合

  * 每个属性为一个键值对

  * 可以通过访问键来获取键对应的值
* ### 对象创建

  * new：

  ```
  var obj = new Object();

  var o = {a:1};
  var obj = new Object(o);//此时obj和o是严格相等的
  ```

  * 字面量

  ```
  var obj = {
      a:1,
      b:2
  }
  ```

  * Object.create：本质将参数设置为原型
    * 参数：对象的属性描述

  ```
  var obj = Object.create({a:1});

  var obj = Object.create(null);//因为null没有原型，所以obj是没有任何方法的

  var obj = Object.create(Object.prototype);//空对象{}
  ```
* ### 对象属性
* ### 对象方法




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

  * 属性描述符：[https://www.xiaohuochai.site/JS/ECMA/types/objectPropertyDescriptor.html](https://www.xiaohuochai.site/JS/ECMA/types/objectPropertyDescriptor.html)

  * 属性的获取

    * for-in

    * Object.keys：返回所有可枚举的自有属性

    * Object.getOwnPrototypeNames\(\)：返回所有自有属性

  * 属性存在判断

    * in：判断属性是否在对象上，即使是继承的也会为true

    * hasOwnPrototype：判断属性是自有属性还是继承属性
* ### 对象方法

  * valueOf：返回当前对象

  * toString：返回当前对象对应的字符串形式

  * toLocaleString：同toString
* 对象的拷贝

  * 浅拷贝：只赋值一层对象属性，复制后的对象指向同一地址块

    * for..in

    * getOwnPrototypeNames

  * 深拷贝：复制多层属性

    * json

    ```
    JSON.parse(JSON.stringify(obj));
    ```




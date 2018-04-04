## 元素属性api

* setAttribute：根据名称和值修改元素的特性
  * name是特性名
  * value是特性值，如果不包含这个特性，则会创建，包含则会修改
  * 元素本身包含的属性可以直接用元素.属性名的方式设置

  ```
  element.setAttribute(name,value);
  element.name = value;
  ```




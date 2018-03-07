## Boolean -- 布尔类型

* 转换方法：Boolean\(\)

* 会转换成false的值

  * undefined
  * null
  * +0
  * -0
  * NaN
  * false
  * 空字符串

* 其他值都转换成true

```
Boolean([]);//true
Boolean({});//true
Boolean(new Boolean(false));//true，因为所有的对象都是转化为true的
```

* 方法
  * toString：返回字符串true或字符串false
  * valueOf：返回原始值true或false




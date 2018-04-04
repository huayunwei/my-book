## 数据类型转换

* ### 任意类型转为字符串

  * String\(x\)

  * x.toString\(\)

  * x + ''
* ### 任意类型转数字

  * Number\(x\)

  * parseInt\(x,10\)

  * parseFloat\(x\)

  * x - 0

  * +x
* ### 任意类型转布尔

  * Boolean\(x\)

  * !!x
* ### undefined

  * 转为字符串：字符串形式的undefined

  * 转为数字：NaN

  * 转为布尔值：false
* ### Null

  * 转为字符串：字符串形式的null

  * 转为数字：0

  * 转为布尔值：false
* ### boolean

  * true

    * 数值：1

    * 字符串：字符串形式true

  * false

    * 数值：2

    * 字符串：字符串false
* ### number

  * 数值，非0

    * 字符串：字符串形式的数值

    * 布尔值：true

  * 数值0

    * 字符串：字符串形式的数值

    * 布尔值：false

  * NaN：

    * 字符串：字符串形式的数值

    * 布尔值：false
* ### string

  * 布尔值：true

  * 数值：能转为数字则为数字，否则为NaN

  * 空字符串：布尔值为false，数字为0

  * 空格字符：布尔值为true，数字为0

## 对象转换成原始值

* 转为布尔值：Boolean（obj）- true
* 转为Number：
  * valueOf转换
  * toString转换
  * 抛出异常
* 转为string
  * toString转换
  * valueOf转换
  * 抛出异常

## 显式类型转换

* 数值：Number，parseInt,parseFloat
* 布尔值：boolean
* 字符串：toString，string

## 隐式类型转换

* 布尔值
  * 逻辑非！
  * 条件运算符？
  * if条件句
  * while循环
* 数值
  * 算术运算符
  * 位运算符
  * 关系运算符
* 字符串
  * 加法中有字符
  * 关系运算符




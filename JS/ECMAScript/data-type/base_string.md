## 转义字符

* \0 空字节
* \n 换行
* \t 制表
* \b 空格
* \r 回车
* 斜杠
* \' 单引号
* \" 双引号

## 转成字符串

* toString
  * null和undefined没有该方法
  * 其他都有，返回值的字符串形式
* String
  * null和undefined都可以转为字符串形式
  * 如果不是null和undefined，会调用toString方法
  * 如果还是对象，会调用valueOf方法
  * 还是对象，报错
* 空字符串 + 要转换的值

```markdown
"" + 2 ==> "2"
```

## 属性

* length：字符串中字符的个数，从0开始算起

## 方法

* 对象通用方法
  * toString：返回字符串本身
  * toLocaleString：返回字符串本身
  * valueOf：返回字符串本身
* 访问字符的方法
  * charAt\(num\)：接受num位置，返回该位置的字符
    * num为空或NaN时，num为0
    * num大于字符串长度，则返回空字符串
  * \[num\]：返回num位置的字符
    * num大于字符串长度，返回undefined
    * num为NaN，返回undefined
  * charCodeAt\(num\)：返回num位置字符的Unicode编码




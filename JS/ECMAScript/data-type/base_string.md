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

* ### 对象通用方法

  * toString：返回字符串本身
  * toLocaleString：返回字符串本身
  * valueOf：返回字符串本身
* ### 访问字符的方法

  * str.charAt\(num\)：接受num位置，返回该位置的字符
    * num为空或NaN时，num为0
    * num大于字符串长度，则返回空字符串
  * str\[num\]：返回num位置的字符
    * num大于字符串长度，返回undefined
    * num为NaN，返回undefined
  * str.charCodeAt\(num\)：返回num位置字符的Unicode编码
    * num为空或NaN，num为0
    * num大于字符串长度，返回NaN
  * String.fromCharCode（num）：num为字符编码，返回该编码对应的字符串
    * 可以有多个num，用逗号隔开
    * num为空或NaN，返回空字符串
* ### 字符串拼接

  * str.concat（str1）：将多个字符串拼接在一起，得到新的字符串

    * str必须是字符串

  * +：
* ### 字符串分割

  * str.slice\(start,end\)：返回从start到end\(不包括end\)的字符串

    * end没有定义，则返回从start到str末尾的字符串

    * start可以为负，为负时start = str.length + start，如果仍然为负，则为0，即start = max\(str.length + start,0\)

    * end可以为负，为负时end = str.length + end，如果仍然为负，则为0，即end = max\(str.length + end,0\)

    * start为NaN时，start = 0

    * end为NaN（undefined不包括，为undefined时参考第一点）时，返回空字符串

  * str.substr\(start,length\)：返回从start开始length长度的字符串

    * start为负，则start = max（length + start ，0）

    * start是NaN，则start = 0

    * end是负或NaN，则end = 0 ，返回空字符串

  * substring\(start,end\)：同slice

    * start,end是NaN或负数，则转换为0

    * start，end大于字符串长度，则转换为字符串长度

    * start大于end，则交换值他们的值
* ### 大小写转换

  * str.toUpperCase：转为大写

  * str.toLowerCase：转为小写

  * str.toLocaleUpperCase：转为地区大写

  * str.toLocaleLowerCase：转为地区小写
* ### 子字符串位置

  * str.indexOf（searchStr,start）：从start开始查找searchStr首次出现的位置，没有找到返回-1

    * start为undefined、NaN、负数时，start为0

  * str.lastIndexOf（searchStr,start）：从右向左查找

    * start为undefined、NaN时，start为length - 1

    * start为负，start = 0
* ### 正则匹配

  * str.match（reg）：接受字符串或正则，返回数组

  * str.search（reg）：接受字符串或正则，返回首次出现的位置，没有返回-1

    * 忽略全局标志g

    * 总是从0开始查找

  * str.replace\(reg,fn\)：替换一个或多个字符串

    * 参数1是正则表达式或字符串，想要被替换的字符串

    * 参数2为字符串或函数，替换成的字符串

    * 默认只替换第一个字符串，使用全局标志可以替换所有匹配的

  * str.split（reg，num）：将字符串根据指定的分隔符分割成多个字符串，保存在数组中

    * 参数1，可以是字符串或正则，代表分隔符

    * 参数2，表示返回的数组的长度，值如果大于最多的分割数，则返回全部的值




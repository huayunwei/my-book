## 转义字符

* \0 空字节
* \n 换行
* \t 制表
* \b 空格
* \r 回车
*  斜杠
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




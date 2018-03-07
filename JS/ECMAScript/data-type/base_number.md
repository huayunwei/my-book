## Number类型

数字字面量：直接出现在js程序中

Number对象：使用new Number\(\)构造函数构建出的

### 浮点数问题：

所有数字都用浮点数表示，由于浮点数需要内存多，所以如果小数点后没有值，则保存成整数

```
1.0 === 1 ==> true

//浮点数之间的运算时，要注意结果可能不是精确的值
0.1 + 0.2 === 0.3 ==> false

0.1 + 0.2 === 0.30000000000000004 ==> true(chrome下)

0.2/0.1 === 2 ==> true

0.3/0.1 === 3 ==> false
```

### 科学计数法

* 小于1且小数后有6个以上的浮点数值
* 整数位数多于21位



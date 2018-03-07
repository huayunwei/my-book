## Number类型

数字字面量：直接出现在js程序中

Number对象：使用new Number\(\)构造函数构建出的

数值范围：

* 最大值Number.MAX\_VALUE：2^1024 
* 最小值Number.MIN\_VALUE ：2^-1023
* 最大整数Number.MAX\_SAFE\_INTEGER ：2^53
* 最小整数 Number.MIN\_SAFE\_INTEGER ：-2^53
* 正无穷 Number.POSITIVE\_INFINITY ：Infinity\( Infinity 参与的运算结果只能是其本身，0，NaN\)
* 负无穷 Number.NEGATIVE\_INFINITY ： -Infinity

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

* 以下情况会使用到科学计数法，即加e的情况
  * 小于1且小数后有6个以上的浮点数值
  * 整数位数多于21位

### NaN：非数字

* 与任何值都不相等，包括自己
* 所有涉及NaN的操作都返回NaN
* 判断是否为NaN

  * isNaN：因为内部是调用Number所以像无法转换成数字的字符串也会返回true
  * 是否等于自身：只有NaN是不等于自身的

  ```
  function myIsNaN(val){
      return val !== val;
  }
  ```

### 正负0

* 是严格相等的，即+0 === -0为true
* 除了在做分母的时候，都是当做0看待的

```
1/+0;//Infinity
1/-0;//-Infinity
```

### 方法

* 转为数值
* 其他

  * isFinite：确定数值是否有穷，如果是正无穷或负无穷或NaN，则返回false，否则返回true






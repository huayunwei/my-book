## Math

用于存储数字常量和函数

### 对数

```
Math.E：自然对数的底数
Math.LN2：2的自然数
Math.LN10：10的自然对数
Math.LOG2E：以2为底e的对数
Math.LOG10E：以10为底e的对数
```

### 派

```
Math.PI
```

### 平方根

```
Math.SQRT2：2的平方根
Math.SQRT1_2：1/2的平方根
```

### 最值

```
Math.max()：参数中最大值，没有参数返回-infinity，如果任意一个参数是NaN或不可转为数字，则返回NaN
Math.min()：参数中最小值，没有参数返回infinity，如果任意一个参数是NaN或不转换为数字，则返回NaN

//使用最值的情况
1.找数组中最大或最小值
var maxValue = Math.max.apply(Math,arr);
var minValue = Math.min.apply(Math,arr);

2.合法的月份值
Math.min(Math.max(1,input),12);
```




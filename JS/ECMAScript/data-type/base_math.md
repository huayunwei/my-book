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

2.合法的月份值,1-12之间
Math.min(Math.max(1,input),12);
```

### 舍入

```
Math.ceil()：向上取整运算
Math.floor()：向下取整
Math.round()：四舍五入
```

### 随机数

```
Math.random()：返回大于或等于0小于1的一个随机数

//获取某个整数范围内随机的一个值
Math.floor(Math.random()*总+第一个值);
Math.floor(Math.randow()*(最大值-最小值+1)+最小值);

//数组中随机的一项
Math.floor(Math.random()*arr.length)

//随机的0,1值
Math.round(Math.random());
```

### 绝对值

```
Math.abs();
```

### 三角函数

```
Math.sin(x)：正弦，返回值在1到-1之间
Math.cos(x)：余弦，返回值在-1到1之间
Math.tan(x)：正切，x为弧度，弧度 = 角度*(2π/360)
Math.asin(x)：反正弦
Math.acos(x)：反余弦
Math.atan(x)：反正切
Math.atan2(y,x)：返回y/x的反正切值
```

### 乘方开方

```
Math.exp(num)：e的num次幂
Math.log(num)：返回num的自然对数
Math.sqrt(num)：返回num的平方根
Math.pow(num,power)：返回num的power次幂
```




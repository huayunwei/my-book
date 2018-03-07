## undefined

* 会出现的情况
  * 已声明但未赋值的的变量
  * 获取对象不存在的属性
  * 无返回值的函数的执行结果
  * 函数的参数没有传入
  * void\(\)的返回值
* 类型检查
  * typeof
  * Object.prototype.toString.call\(\)
* 类型转换
  ```
  Boolean(undefined);//false
  Number(undefined);//NaN
  String(undefined);//'undefined'
  ```

## null

* 表示一个空对象指针
* 类型判断
  * Object.prototype.toString.call\(\)
  * typeof判断为object的原因：
    > 不同对象在底层都表示为二进制，在js中二进制前三位都为0会被判断为object类型，null的二进制表示全为0，所以执行typeof时返回object
* 类型转换
  ```
  Boolean(null);//false
  Number(null);//0
  String(null);//'null'
  ```

## 关联

* 都没有属性和方法
* null == undefined ==&gt; true 
* null === undefined ==&gt;false
* 都表示值的空缺，null表示空值，undefined表示未定义




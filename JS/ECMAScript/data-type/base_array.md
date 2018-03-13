## 数组

* ### 创建数组

  * 字面量：var a = \[\]

  * 构造函数：new Array\(\)

    * 没有参数，创建一个空数组

    * 有一个数值参数，用于指定数组长度

    * 其他类型的一个参数，返回只包含该值的长度为1的数组

    * 多个参数，返回这些参数作为数组项的数组
* ### 稀疏数组

  * 从0开始的不连续索引的数组

  * 创建方法

    * 使用delete操作符

    * 用字面量创建数组时，省略元素值
* ### 属性

  * length：长度，不能为赋值，范围从0到2^32-2
* ### 数组乱序

  * sort方法

  ```markdown
  //sort方法传一个函数，随机返回1或-1
  array.sort(function(){return Math.random() - 0.5})
  ```

  * 遍历

  ```markdown
  //遍历数组，遍历到的值和随机位置的元素交换位置
  for(let i=0;i<arr.length;i++){
      var randomIndex = Math.floor(Math.random()*arr.length);
      [arr[i],arr[randomIndex]] = [arr[randomIndex],arr[i]];
      //或arr[i] ^= arr[randomIndex]; arr[randomIndex] ^= arr[i]; arr[i] ^= arr[randomIndex]
  }
  ```
* ### 数组方法

  * #### 对象继承方法

    * toString：返回数组中每个值用逗号拼接而成的字符串，对于null和undefined返回空字符串

    * toLocaleString：返回本地化版本，一般情况和toString相同，对于null和undefined返回空字符串

    * valueOf：返回数组对象本身
  * #### 转换方法
  * #### 栈和队列方法
  * #### 排序方法
  * #### 拼接方法
  * #### 截取方法
  * #### 位置方法
  * #### 归并方法
  * #### 迭代方法




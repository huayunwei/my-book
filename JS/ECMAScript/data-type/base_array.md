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
  }
  ```




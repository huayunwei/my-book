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

    * arr.join\(str\)：str为链接符，将arr中每一项以str作为链接形成一个字符串，默认str为逗号
  * #### 栈和队列方法

    * push：添加到数组末尾，参数可以是多个

    * pop：移除数组最后一项

    * shift：移除数组中第一项

    * unshift：添加到数组最前，多个值时是一次性插入，所以顺序不变
  * #### 排序方法

    * reverse：反序，改变原数组

    * sort：排序，改变原数组

      * 调用toString，然后比较每一项的字符串的排序

      * 可以接受一个函数，自定义排序规则

        * 返回负数，第一个参数应该在第二个参数之前

        * 返回0，参数1和参数2相等

        * 返回正数，第一个参数应该在第二个参数之后
  * #### 拼接方法

    * concat：创建一个新数组，返回合并后的新数组

      * 参数为单个值，则直接push到数组末尾

      * 参数为数组，只展开第一层，然后将每一项push到数组的末尾
  * #### 截取方法

    * #### slice
  * #### 位置方法
  * #### 归并方法
  * #### 迭代方法




## 数组

* ### 创建数组

  * 字面量：var a = \[\]

  * 构造函数：new Array\(\)，可以不加new，即Array和new Array一样

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

    * slice\(start,end\)：截取从start到end（不包含end）

      * start，end可以为负，为负时为0和length+该值的最大值

      * 不给参数，浅复制数组

      * start转为NaN时，start为0

      * end转为NaN，除undefined外，输出空数组

      * end为undefined时，代表截取到末尾
  * #### 位置方法

    * indexOf\(search,start\)：从start开始找，返回第一次出现的位置，没有找打返回-1

      * 进行严格相等比较的，即===

      * start转化为NaN时，start = 0

      * start可以为负

    * lastIndexOf\(\)：同上，只是反向查找
  * #### 删改方法

    * splice：

      * 参数1，指定插入或删除的起始位置，可以为负，如果转化为NaN，则等于0

      * 参数2，删除的个数，省略则删除从起点到末尾的值，为负或转化为NaN时，等于0

      * 参数3到无穷，插入的值
  * #### 归并方法

    * reduce

      * 参数1：函数

        * 函数参数1：默认为数组第一个元素值，执行后为上一次执行的返回值

        * 函数参数2：当前值，如果没有定义参数2，则为数组第第二个值，如果指定，则为数组第一个值

        * 函数参数3：索引，当前值的下标

        * 函数参数4：数组本身

      * 参数2：初始值

    * reduceRight：同上，反向

    * 应用

    ```
    //求和
    arr.reduce(function(pre,next){return prev + next},0)

    //乘积
    arr.reduce(function(pre,next){return prev * next },1)

    //最大值
    arr.reduce(fucntion(pre,next){return prev > next ? prev : next})
    ```
  * #### 迭代方法

    * map：给数组每一项执行函数，返回结果

      * 对数组中不存在的元素，不调用

      * 参数2为上下文环境

    * forEach：同map但无返回值

    * filter：过滤，返回结果为true的项组成的数组

      * 参数2为上下文环境

    * some：如果数组中任一一项在执行函数时返回true，则返回true，全部为false则返回false

    * every：如果数组所有项在执行函数时都返回true，则返回true，否则返回false




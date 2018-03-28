## 左右布局

* float + overflow![](/assets/left_right_float_overflow.gif)

  * 使用：

  ```
  //左侧可以不设定宽度，不设定，则为left内部的文字的宽度
  //如果不设置宽度，会导致文字过多是，覆盖右侧
  .left{
      float:left;
  }
  .right{
      overflow:hidden;//添加后
  }
  ```

* float + margin![](/assets/left_right_float_margin.gif)![](/assets/left_right_float_margin.png)

  * 使用

  ```
  //左侧可以不设定宽度，不设定，则为left内部文字的宽度,但是因为margin一般设置为left的宽度
  //如果不设置可能会导致超出设置margin值的情况
  .left{
      float:left;
  }
  .right{
      margin-left:left的宽度;//一般为left的宽度，但是具体大小可以自己定义
  }
  ```

* table![](/assets/left_right_table.gif)

  * 使用

  ```
  .parent{
      display:table;
  }
  .left{
      width:100px;
  }
  .left,.right{
      display:table-cell;
  }
  ```

* flex




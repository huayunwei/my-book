## 等分布局

* float + 百分比![](/assets/float_百分比.png)

  * 使用

  ```
  .parent{
      margin-left:等分的padding宽度;
  }
  .col{
      float:left;
      width:100/col的个数;
      padding-left:20px;//设置间距
      box-sizing:border-box;
  }
  ```

* table![](/assets/table.png)
  * 使用

  ```
  .parent{
      display:table;
      margin-left:-20px;
  }
  .col{
     display:table-cell;
     padding-left:20px;   
  }
  ```




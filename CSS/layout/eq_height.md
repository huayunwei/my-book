## 等高布局

* table![](/assets/eq_height_table.png)

  * 使用

  ```
  .parent{
      display:table;
  }
  .right,.left{
      display:table-cell;
  }
  ```

* flex![](/assets/eq_height_flex.png)

  * 使用

  ```
  .parent{
      display:flex;
  }
  ```

* position  
  ![](/assets/eq_height.gif)

  * 缺点：必须设置父元素的高度
  * 使用

  ```
  .parent{
      position:relative;
      height:;
      overflow:hidden;
  }
  .left{
      position:absolute;
      top:0;
      left:0;
      bottom:0;
  }
  .right{
      position:absolute;
      top:0;
      left:0;
      bottom:0;
  }
  ```




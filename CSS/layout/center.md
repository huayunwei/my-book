## 水平垂直居中

* 给定宽度和高度：position + margin![](/assets/both_position_margin.png)

  * 用法：

  ```css
  .parent{
      position:relative;
  }
  .child{
      position:absolute;
      top:50%;
      left:50%;
      margin-left:-宽度的一半;
      margin-top:-高度的一半;
      width:宽度;
      height:高度;
  }
  ```

* 给定宽度和高度：position + margin![](/assets/both_position_margin2.png)

  * 用法：

  ```css
  .parent{
      position:relative;
  }
  .child{
      position:absolute;
      top:0;
      bottom:0;
      left:0;
      right:0;
      margin:auto;

      width:xxx;
      height:xxx;
  }
  ```

* position + transform![](/assets/both_position_transfrom.png)

  * 用法

  ```css
  .parent{
      position:relative;
  }
  .child{
      position:absolute;
      top:50%;
      left:50%;
      transform:translate(-50%,-50%);
  }
  ```

* inline-block + text-align + table-cell + vertical-align![](/assets/both_inline-block_table-cell.png)

  * 用法

  ```
  .parent{
      display:table-cell;//加这个才能实现垂直居中
      text-align:center;//用于水平居中
      vertical-align:middle;//用于垂直居中
  }
  .child{
      display:inline-block;
  }
  ```

* flex + align-items + justify-content + align-items![](/assets/both_flex.png)

  * 用法

  ```css
  .parent{
      display:flex;
      align-items:center;
      justify-content:center;
  }
  ```




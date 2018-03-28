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

* 给定宽度和高度：position + margin

* position + transform

* inline-block + text-align + table-cell + vertical-align

* flex + align-items + justify-content + align-items




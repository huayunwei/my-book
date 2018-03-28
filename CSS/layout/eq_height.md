## 等高布局

* table
* flex
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




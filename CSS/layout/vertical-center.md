## 垂直居中

* 给定子元素的高度：position + margin![](/assets/position_margin.png)

  * 用法

  ```
  .parent{
      position:relative;
  }
  .child{
      position:absolute;
      top:0;
      bottom:0;
      left:0;
      margin:auto 0;
  }
  ```

* 给定子元素的高度：position + margin![](/assets/position_margin2.png)

  * 用法

  ```
  .parent{
      position:relative;
  }
  .child{
      position:absolute;
      top:50%;
      left:0;
      margin-top:-width/2;
  }
  ```

* tabel-cell + vertical![](/assets/table-call_vertical.png)

  * 用法

  ```
  .parent{
      display:table-cell;
      vertical-align:middle;
  }
  ```

* position + transform

  ![](/assets/position_transform.png)
  * 用法

  ```
  .parent{
      position:relative;
  }
  .child{
      position:absolute;
      top:50%;
      left:0;
      transform:translateY(-50%);
  }
  ```

* flex + align-items![](/assets/flex_align-items.png)

  * 用法

  ```
  .parent{
      display:flex;
      align-items:center;
  }
  ```




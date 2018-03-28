## 水平居中

* 子元素宽度指定：width+margin:0 auto;![](/assets/center_width_margin.png)

  * 用法

  ```
  .child{
      width:;
      margin:0 auto;
  }
  ```

* 子元素宽度指定：width+position+margin![](/assets/center_width_position.png)

  * 用法：子元素给定宽度，子元素postion:absolute;，子元素margin-left:宽度一半

  ```
  .child{
      position:absolute;
      top:0;
      left:50%;
      width:;
      margin:-width/2;
  }
  ```

* inline-block + text-align![](/assets/center_inline_block.png)

  * 用法

  ```
  .parent{
      text-align:center;
  }
  .child{
      display:inline-block;
  }
  ```

  * 缺点：child中的文字也会居中显示，可以子元素text-align:left恢复左侧显示

* table + margin![](/assets/center_table.png)

  * 用法

  ```
  .child{
      display:table;
      margin:0 auto;
  }
  ```

* position + transform![](/assets/center_position_transform.png)

  * 用法

  ```
  .parent{
      position:relative;
  }
  .child{
      position:absolute;
      top:0;
      left:50%;
      transform:translateX(-50%);
  }
  ```

* flex + margin![](/assets/flex_margin.png)

  * 用法：父元素display:flex，子元素margin:0 auto;
  * 注：子元素的高度会默认为父元素的高度

* flex + justify![](/assets/flex_justify.png)

  * 用法：父元素display:flex，justify-content:flex;




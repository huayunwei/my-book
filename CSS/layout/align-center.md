## 水平居中

* 子元素宽度指定：width+margin:0 auto;![](/assets/center_width_margin.png)

  * 原理：子元给定宽度，子元素margin:0 auto;

* 子元素宽度指定：width+position+margin![](/assets/center_width_position.png)

  * 原理：子元素给定宽度，子元素postion:absolute;，子元素margin-left:宽度一半

* inline-block + text-align![](/assets/center_inline_block.png)

  * 原理：子元素inline-block，父元素text-align：center

  * 缺点：child中的文字也会居中显示，可以子元素text-align:left恢复左侧显示

* table + margin![](/assets/center_table.png)

  * 原理：子元素table，加上margin:0 auto
  * 缺点：

* position + margin![](/assets/center_position_margin.png)




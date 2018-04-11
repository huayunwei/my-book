## 盒模型

元素大小的呈现方式

content-box：

```
元素的width = css中width
```

border-box：

```
元素的width = css中width - css中padding - css中border
```

## margin叠加

两个或多个垂直边距相遇时，两者之间的边距的高度等于两个重叠边距中高度较大的那个

只有普通文档的垂直边距才会出现

行内、浮动、绝对定位之间的外边距不会叠加

## CSS文档流

HTML中位置决定排布顺序

## CSS定位方式

* display：

  * block：可以设置盒模型相关属性，独占一行，宽度默认为父元素宽度

  ```
  div h1-h6 ul li p
  ```

  * inline：与其他元素共占一行，宽高由内容决定，只能设置水平的margin，padding有效

  ```
  span a i
  ```

  * inline-block：宽高可以设置，但是与其他元素共占一行，即对外类似inline，对内类似block

  * table-cell：以单元格形式呈现




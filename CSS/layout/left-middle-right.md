## 三列布局

### 两列定宽一列自适应

* 左中定宽，右自适应![](/assets/lmr_float.png)

  * 使用

  ```
  .left{
      width:100px;
      float:left;
  }
  .mid{
      width:100px;
      float:left;
  }
  .right{
      overflow:hidden;//不加，right的宽度为父元素的宽度
  }
  ```

* 左右定宽，中自适应




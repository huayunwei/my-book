## 三列布局

### 两列定宽一列自适应

* 左中定宽，右自适应

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

  * 绝对定位![](/assets/lrm_position.png)

    * 使用

    ```
    .parent{
        position:relative;
    }
    .left{
        position:absolute;
        top:0;
        left:0;
        width:100px;
    }
    .right{
        position:absolute;
        top:0;
        right:0;
        width:100px;
    }
    .middle{
        margin:0 100px;
    }
    ```

  * float + margin![](/assets/lrm_margin.gif)

    * 使用：注意html的写法

    ```
    .left{
        float：left;
        width:100px;
        margin-left:-100%;
    }
    .mid-parent{
        width:100%;
        float:left;
    }
    .middle{
        margin:0 100px;
    }
    .right{
        float:left;
        width:100px;
        margin-left:-100px;
    }
    ```

  * float + margin




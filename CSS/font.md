### 文本溢出省略号

* 单行
  ```
  white-space:nowrap;
  overflow:hidden;
  text-overflow:ellipsis;
  ```
* 多行：不兼容IE
  ```
  display:-webkit-box;
  -webkit-line-clamp:2;
  -webkit-box-orient:vertical;
  overflow:hidden;
  ```

### 垂直居中

* padding + line-height

```
//如果需要父元素为40px
line-height:24px;
padding:8px 0;
```

* 



文本省略号

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




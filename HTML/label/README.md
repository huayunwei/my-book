## HTML元素

### 标签和元素

* 标签：&lt;p&gt; -- 开始标签，&lt;p/&gt; -- 结束标签
  * 所有标签：[https://developer.mozilla.org/zh-CN/docs/Web/Guide/HTML/HTML5/HTML5\_element\_list](https://developer.mozilla.org/zh-CN/docs/Web/Guide/HTML/HTML5/HTML5_element_list)
  * 空标签：开始标签中关闭的
* 元素：从开始标签到结束标签的所有代码，元素内容为开始标签与结束标签之间的内容

### 元素分类

* 按display区分：

  * 块级元素 - block

    * 特点：

      1. 总是在新行上开始，占据一整行

      2. 盒模型相关属性都可以设置

      3. 宽度默认是他容器的100%

      4. 可以容纳内联元素和其他块元素

    * 常见元素

    ```
    div h1-h6 p table ul ol 等
    ```

  * 行内元素 - inline

    * 特点

      1. 和其他元素在同一行

      2. 可以设置padding，border，左右margin，但是width，height，上下margin，line-height设置后无效

      3. 宽度和高度只和内容有关

      4. 只能容纳文本或其他行内元素

    * 常见元素

    ```
    span i label strong small em br a
    ```

  * 行内块状元素 - inline-block

    * 特点

      1. 对内是块状元素

      2. 对外是行内元素

      3. 即可以设置宽，高等盒模型属性，但是和其他元素是在同一行的

    * 常见元素

    ```
    input img(谷歌浏览器默认display是inline,但是可以设置宽高) select textarea button
    ```

  * 转换

    1. 使用display转换

    2. 使用float后，元素转变成display：block

    3. 使用position:absolute，fixed后，元素转变成display：block

* 按内容模型区分 - [官网地址](https://www.w3.org/TR/html5/dom.html#content-models)

  * 元数据型：用于说明其他内容的表现或行为，或者在当前文档和其他文档之间建立联系的元素

  ```
  base link meta noscript script style template title
  ```

  * 区块型：用于定义标题及页脚范围的元素

  ```
  article aside nav section
  ```

  * 标题型：定义一个区块/章节的标题

  ```
  h1 h2 h3 h4 h5 h6
  ```

  * 文档流型：应用程序和文档的主体部分中使用的大部分元素

    包括除了元数据中base，link，meta，style，title之外的所有其他类型的元素

  * 语句型：标记段落级文本的元素

  * 内嵌型：引用或插入到文档中其他资源的元素

  ```
  audio canvas embed iframe img math object svg video
  ```

  * 交互型：用于与用户交互的元素

### 标签的嵌套规则

[参考网页](https://www.xiaohuochai.site/HTML/grammar/grammar_tagsNesting.html)


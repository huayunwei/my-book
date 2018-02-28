## 结构标签

### section

* 表示文档中的一个区域
* 一般包含一个标题（h1-h5）
* 如果内容可以分为几个部分，使用article

### article

* 表示文档、页面、应用或网站中的独立结构
* 一般包含一个标题

### aside

* 表示和页面其余内容几乎无关的部分，被拆分出来不会对整体造成影响

### nav

* 导航栏
* 含有多个超链接的区域
* 一般只用来将热门链接放入导航栏中

### header

* 页面头部或区块头部

### footer

* 根节点元素的页脚

### main

* 主体部分

### 基本结构

```markdown
<html>
    <head>
        <meta charset="UTF-8">
        <title></title>
    </head>
    <body>
        <nav>
            <ul>
                <li></li>
                <li></li>
            </ul>
        </nav>
        <article>
            <section></section>
        </article>
        <aside>
            <ul>
                <li></li>
            </ul>
        </aside>
    </body>
</html>
```




## HTML文档声明

### HTML5文档声明

```
<!DOCTYPE html>
```

### HTML4文档声明

* 严格型strict

```
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
```

* 过渡型transitional

```
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
```

* 框架frameset

```
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Frameset//EN" "http://www.w3.org/TR/html4/frameset.dtd">
```

### 为什么HTML5和HTML4的声明不同

* DTD：文档类型定义
* SGML：标准通用标记语言，是一种定义电子文档结构和描述其内容的国际标准语言
* doctype：标准通用标记语言的文档类型声明

HTML4基于SGML，需要引用DTD

HTML5不基于SGML，是结合SGML,HTML,XHTML1.X语法形成的有自己规则的合成语言

HTML5需要doctype来启用浏览器的标准渲染模式


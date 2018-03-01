## HTML条件注释

### 作用：识别IE9及以下

### 写法：

* 单一IE版本

```markdown
//IE7
<!--[if IE 7]><![endif]-->
//IE8
<!--[if IE 8]><![endif]-->
//IE9
<!--[if IE 7]><![endif]-->
```

* 范围

```markdown
//gt：大于
<!--[if gt IE 7]><![endif]-->

//gte：大于等于
<!--[if gte IE 7]><![endif]-->

//lt：小于
<!--[if lt IE 7]><![endif]-->

//lte：小于等于
<!--[if lte IE 7]><![endif]-->
```




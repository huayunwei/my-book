## HEAD下的子元素主要有以下几种

### meta -- 提供页面相关元数据

* charset：声明当前文档所使用的字符编码

```markdown
<meta charset="utf-8"/>
```

* name：搭配content使用，定义一些文档级的元数据

```markdown
//关键词
<meta name="keywords" content="前端 总结">

//描述
<meta name="description" content="前端知识总结">

//作者
<meta name="author" content="">

//版权
<meta name="copyright" content="">

//视口
<meta name="viewport" content="width=device-width,initial-scale=1.0,maximum-scale=1.0,minimum-scale=1.0,user-scalable=no">
```

* http-equiv：配合content使用

```markdown
//多少秒刷新一次页面
<meta http-equiv="refresh" content="5">

//多少秒跳转到其他页面
<meta http-equiv="refresh" content="5;url=www.baidu.com">

//禁止缓存
<meta http-equiv="Pragma" content="No-cach">

//默认使用IE高版本来渲染页面
<meta http-equiv="X-UA-Compatible" content="IE=Edge">
```

### title -- 定义文档标题

```markdown
<title>标题</titile>
```

### base -- 指定文档里所有相对URL地址的基础URL

### link -- 指定外部资源与当前文档的关系

* rel：指定资源类型

  * icon：浏览器标签上的图标

  ```
  <link rel="shortcut icon" href="1.ico"/>
  ```

  * stylesheet：样式表

  ```
  <link rel="stylesheet" href="xx.css" />
  ```

* href：指定外部资源地址

* media：媒体查询，指定在那种媒体下引入外部资源

```
<link rel="stylesheet" href="xx.css" media="screen and (max-width:980px)">
```

### style -- 嵌入内部样式

### script -- 嵌入内部脚本、引入外部脚本




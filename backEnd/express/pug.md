### 介绍 --- html模板引擎

### 安装 --- `npm install pug`

### 编译
* 安装编译工具 --- `npm install -g pug-cli`

* 压缩编译 - 没有空白符的

	`pug name.pug`

* 非压缩编译 - 有格式的

	`pug -P name.pug`

### 基本结构

```
// 注释1：解析为<!---->html注释
//- 注释2：不会生成到解析后的html文件中
<!---->：直接使用html的注释

doctype html --- <!DOCTYPE html>
html
	head
		title pug基本结构
		meta(charset="utf-8")
	body
		div
			p 字段
```

### 标签
* 标签内嵌子元素
	
	```
	a:img：<a><img/></a>
	```
* 自闭和标签

	```
	foo/ --- <foo/>
	```
* 标签的多行内容

	```
	script.
		const a = "xxx";
		console.log(a);
	```


### 变量 --- -：定义变量，并可以在pug中使用，是全局的
* 单变量

	```
	- const a = "123";
	```

* 多变量

	```
	-
		const a = "123";
		const b = "456";
	```

* 变量的使用
	* 作为文本

		```
		div ${a}
		或
		div= a
		```
	* 作为属性

		```
		div(class=a)
		```

### 属性 --- ()
	
* 基本形式

	```
	a(href="javascript;" class="23")
	等同于
	<a href="javascript;"></a>
	```
* 带表达式的属性

	```
	- const b = true;
	a(href=b ? "1" : "2")
	```
* 不转义的属性：!= --属性默认通过转义，用于防止跨域脚本攻击

	```
	div(name="<code>") ==> <div name="&lt;code$gt;"></div>

	div(name!="<code>") ==> <div name="<code>">
	```
* 样式属性：style={}

	```
	div(style={color:'red',background:'green'})
	```
* class属性：简写.xxx

	```
	div.text ==> <div class="text"></div>

	- const arr = ["text1","text2"];
	div(class=arr) ==> <div class="text1 text2"></div>

	div(class="text1") ==> <div class="text1"></div>
	```
* id属性：简写#xxx


### 条件
* if：

	```
	- const flag = true;
	if !flag  --- 等同于 unless flag
		div 1
	else if flag 
		div2
	else 
		div 3
	```
* case：分支条件 -- 类似js中的switch
	
	```
	- const a = 1;
	case a
		when 0
			div 0
		when 1
		when 2
			div 1  -- a为1或2的时候都输出<div>1</div>
		when 3
			- break  --- a为3时不输出任何东西
		default
			div xxx

	```


### 循环
* each -- 可以用for替代
	
	```
	//对于数组 和js中forEach一样，参数1-val为值，参数2-index为下标
	ul
	 each val,index in [1,2,3]
	 	li= val

	// 对于对象 参数1-val为值，参数2-key为键值
	 ul
	 	each val,key in {'key':'value'}
	 		li= val

	//对于数组和对象没有可迭代的值时
	- const arr = [];
	ul
		each val,index in arr
			li= val
		else 
			li 空

	```

* while

	```
	
	- var  n = 0;
	//必须用++,--这种修改n的值，以达到有限的循环
	ul
		while n < 4
			li= n++

	```

### 代码块模板 --- mixin
* 基本格式

	```
	// 代码块模板 minxin 模板名字
	minxin list
		ul
			li 1
			li 2

	//模板的使用 +模板名字
	+list ==> <ul><li>2</li><li>2</li></ul>
	+list ==> 同上

	```

* 传参

	```
	minxin list(con)
		ul
			li 1
			li= con

	+list("你好")

	minxin list(...items)
	//items = [1,2,3,4,5];
		ul
			each item in items
				li= item
	+list(1,2,3,4,5)
	```


### 引入其他文件 --- include
```					
//a.pug 			
div a  			
//b.pug 	
div.b 				
	include a.pug 	
```

b.pug转化为
```
<div class="b">
	<div>a</div>
</div>
```
* 如果不是pug文件而是静态文件，如.js文件，直接作为文本

### 继承 --- extend
* 模板a.pug文件，用于其他文件的继承
	```
	html
		head
			title 演示
			block 块名
				script(src="jquery.js")
		body
			block content
			block foot
	```

* b.pug文件继承自a.pug -- 没有在文件中定义的块，会使用父元素的，定义的会覆盖父元素的
	```
	extend a.pug
	block content
		div 我是b.pug中的内容

	```

* 扩展父元素，而不是覆盖父元素的c.pug
	```
	extend c.pug
	// append添加到块的尾部
	//prepend添加到块的头部
	block append content
		div 我是c.pug的内容
	```

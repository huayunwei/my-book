## HTML全局属性

### Class

* 作用：规定一个或多个类名，用空格隔开

* 注意：不能以数字开头

### dir

* 作用：文字的方向

* 值：

  * auto：默认从左到右  
  * ltr：从左到右  
  * rtl：从右到左

### id

* 作用：元素的唯一标识

* 注：如果有多个id,css是所有的都生效,而js只能获取到第一个匹配的

### style

* 作用：行间样式
* 格式：

```markdown
<div style="color:green;font-size:13px;">hello</div>
```

### tabindex

* 作用：获取焦点的顺序
* 值：Number，从1开始，1代表第一个获取焦点的值
* 格式：

```markdown
<div tabindex="1"></div>
<div tabindex="3"></div>
```




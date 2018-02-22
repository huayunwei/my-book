## HTML全局属性

### Class

* 作用：规定一个或多个类名，用空格隔开

* 注意：不能以数字开头

### dir

* 作用：文字的方向

* 兼容性：IE不支持，手机端不支持，兼容性不好

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
* 值：Number，从1开始，1代表第一个获取焦点
* 格式：

```markdown
<div tabindex="1"></div>
<div tabindex="3"></div>
```

### title

* 作用：规定元素的额外信息，鼠标悬停在元素上时会显示
* 格式：

```markdown
<div title="hello">悬停显示hello</div>
```

## HTML5新增全局属性

### contenteditable

* 作用：指定对于默认不可编辑的元素是否可以编辑
* 值：true / false ,不写值默认为true
* 兼容性：IOS Safari 5.1以后,Android 3以后支持
* 格式

```markdown
<div contenteditable>123</div>
<!-- 对于默认就可以编辑的元素，设置不可编辑是无效的 -->
<input type="text" contenteditable="false" />
```

### data-\*

* 作用：元素自定义属性的方法

* 兼容性：IE10以下不支持用dataset获取data-\*属性,但是可以设置data-\*属性并通过getAttribute获取

* 格式

```markdown
<!-- data-* 属性名不能有大写字母,且必须有一位字符 -->
<div data-name="div的名字">data-*</div>
```

* 获取：getAttribute / dataset

![](/assets/1.png)




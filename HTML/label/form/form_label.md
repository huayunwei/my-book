## label

### 作用：

为input元素定义标注，建立文字标签与表单控件的关联，选择该文本时浏览器会自动把焦点转到和标签相关的表单控件上

### 属性：

* for：规定label绑定到哪个表单元素（需要与表单元素的id相同）
* form：规定label字段所属的一个或多个表单

```markdown
//写法1：使用for
<label for="q1">q1</label>
<input type="radio" id="q1"/>

//写法2：不适用for，嵌套
<label>q1<input type="radio"/></label>
```




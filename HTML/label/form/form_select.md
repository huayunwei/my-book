## Select -- 下拉列表

```markdown
<select>
    <option></option>
</select>

<select>
    //定义一个选项组
    <optgroup>
        <option></option>
    </optgroup>
</select>
```

### 属性

* Select：

  * size：规定下拉列表中可见选项的数目

* option：

  * disabled：规定此选项应在首次加载时被禁用
  * label：定义当使用optgroup时所使用的标注，替代option元素内容
  * selected：首次显示在列表中时表现为选中状态
  * value：定义送往服务器的选项值，提交时默认为value的值，否则提交option元素的内容

* optgroup：

  * label：为选项组规定描述
  * disabled：禁用该选项组




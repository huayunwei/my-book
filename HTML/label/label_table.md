### Table

### 结构：

```markdown
<table>
    <!--caption可以设置margin和padding-->
    <caption>表格的标题</caption>
    
    <!--表头-->
    <thead>
        <tr>
            <th></th>
        </tr>
    </thead>
    
    <!--表体-->
    <tbody>
        
        <tr>
            <td></td>
        </tr>
    </tbody>
    
    <!--页脚-->
    <tfoot> </tfoot>
</table>
```

### 

### tr --行

### th -- 表头的单元格

* colspan：Number，跨越的列数，即该单元格占据的列数
* rowspan：Number，跨越的行数，即该单据格占据的行数
* padding设置有效

### td -- 表体的单元格

* colspan：Number，跨越的列数，即该单元格占据的列数

* rowspan：Number，跨越的行数，即该单据格占据的行数

* padding设置有效

### col -- 为表格中的列定义属性

* span：Number，默认只定义一列的属性值，添加该属性后可以指定多列的属性值

```
<table>
    <col span="2" style="background:red;">
</table>
```

### colgroup -- 和col一样

* span：Number，默认只定义一列的属性值，添加该属性后可以指定多列的属性值

```
<table>
    <colgroup span="2" style="background:red;"></colgroup>
</table>
```




## 图片

### img

* src：地址
* alt：图片无法显示时的文字说明
* height：图像高度
* width：图像宽度
* ismap：为图像定义为服务器端图像映像
* longdesc：与alt类似，提供多于1024字符的长文本描述
* usemap：为图像定义客户端图像映射
* srcset：指定图片的地址和对应的图片质量
* size：设置图片的尺寸临界点
* crossorigin：跨域

### figure -- 用来插入图片和figcaption配合使用

### figcaption -- figure的标题

```markdown
<figure>
    <img src="xx.jpg" alt="" />
    <figcaption>
        xxxx
    </figcaption>
</figure>
```

## 图像映射

### map

### area -- 定义图像热区

* alt：文本
* coords：定义点击区域的坐标
  * shape为圆形：x，y，r（圆心坐标x,y，半径r）
  * shape为多边形：x1，y1，x2，y2...（多边形每个顶点的坐标）
  * shape为矩形：x1，y1，x2，y2（x1,y1为左上角,x2,y2为右下角）
* href：此区域的链接地址

* shape：此区域的形状

  * circ/circle：圆形
  * poly/polygon：多边形
  * rect/rectangle：矩形
  * default：整体

```
<img src="xxx.jpg" alt="xxx" usemap="#mymap">
<map name="mymap">
    <area shape="react" coords="10,10,50,50" href="1.html" alt="xxx"></area>
</map>
```




## A标签

### 概念

通常用来表示一个锚点/链接

### 属性

---

#### href：地址，如果为空，点击时会刷新页面，使用javascript:;

* 链接地址

```
<a href="http://www.baidu.com">百度</a>
```

* 下载地址
  * 文本文件：.txt，.js，.html，.css直接显示
  * 媒体文件：.mp3，.mp4直接播放
  * 下载文件：.zip，.doc，.xls等会被下载

```
<a href="1.zip">下载</a>
```

* 锚点

  * 当前位置

    * 点击跳转

    ```
    <a href="#text">点我</a>
    ```

    * 修改链接地址跳转

    ```
    http://www.baidu.com#text
    ```

  * 目标处：匹配多个，跳转到第一个匹配的

    * 非a标签，必须用id属性

    ```
    <div id="text">跳转到我这里</div>
    ```

    * a标签，可以用name或id属性

    ```
    <a name="text">跳转到我这里</a>

    <a id="text">也会跳转到我这里</a>
    ```

* 显示手机拨号盘

```
<a href="tel:232323">232323</a>
```

#### target -- 链接打开的方式

* \_self：当前窗口（默认）
* \_blank：新窗口
* \_parent：父框架集
* \_top：整个窗口
* \_framename：指定框架



#### download -- 可以下载文件的下载名字




## A标签

### 概念

通常用来表示一个锚点/链接，发送的是一个GET请求

### 属性

---

#### href：地址，如果为空，点击时会刷新页面，使用javascript:;

* 链接地址
  * 如果连接地址为相对路径，则会以文件的形式进行打开
  * 如果打开链接地址，则需要写完整的链接地址，即需要有协议前缀
  * 如果只写//，则页面当前是什么协议就以什么协议打开这个文件

```
<a href="http://www.baidu.com">百度</a>//进入百度页面
<a href="www.baidu.com">百度</a>//会进入当前目录/www.baidu.com这个地址
<a href="//www.baidu.com">百度</a>//如果为file://协议，则会进入file://www.baidu.com
<a href="#"></a>//会自动滚到页面首部
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

* 伪协议：javascript：；这种形式

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

#### download -- 下载

* download="下载名字"
* 如何实现download
  * 如果请求里有Content-type：application/octet-stream则进行下载
  * 否则用a标签中加download

#### rel -- 链接间的关系

#### 




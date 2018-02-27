## 媒体格式

### 音频格式

* .mid/.midi：一种针对电子音乐设备的格式
* .rm/.ram：Real Media针对因特网开发的
* .wav：除Chrome都支持
* .wma：兼容大多数播放器，除了Ipod
* .mp3/.mpga：mp3实际为MPEG文件的声音部分

### 视频格式

* .avi：windows计算机都支持
* .wmv：需要安装windows media插件才可以播放
* .mpg/.mpeg：最流行的格式
* .mov：QuickTime格式，也需要额外的插件
* .rm/.ram：允许低带宽，质量会降低
* .swf/.flv：flash格式，需要额外的组件来播放
* .mp4：Mpeg-4格式

## 媒体标签

* embed：用来定义嵌入内容，比如flash插件

  * height：嵌入内容的高度
  * width：嵌入内容的宽度
  * src：嵌入内容的URL
  * type：嵌入内容的类型

* object：定义一个嵌入的对象

  * height：嵌入对象高度
  * width：嵌入对象的宽度
  * type：嵌入对象的类型
  * name：对象的名称，以便在脚本中使用
  * data：设置对象的URL
  * usemap：设置与对象一同使用的客户端图像映射的URL
  * form：规定对象所属的一个或多个表单
  * typemustmatch：检测资源类型和type属性是否相符

* param：给内嵌的插件传递参数

  * name：定义参数的名称
  * value：规定参数的值
  * type：规定参数的MIME类型
  * valuetype：规定值的MIME类型

* video：视频，IE8-不支持

* audio：音频，IE8-不支持

* source：为video和audio提供媒介资源

  * media：媒体资源的类型

  * src：媒体文件的URL

  * type：媒体资源的MIME类型

* track：允许指定计时字幕

```markdown
//音频
<audio>
    <source src="1.mp3" type="audio/mp3" />
    <embed height="" width="" src="1.mp3" />
</audio>

//视频
<video>
    <source src="1.mp4" type="video/mp4" />
    <object data="1.mp4" width="" height="">
        <embed src="1.mp4" width="" height="" />
    </object>
</video>
```

## video和audio元素的属性，方法，事件

### 属性

### 方法

* canplayType\(\)：检测浏览器是否能播放指定音频或视频
  * 返回值：
    * probable：浏览器很可能支持该类型
    * maybe：浏览器也许支持该类型
    * ：浏览器不支持该类型
* load\(\)：重新加载音频或视频元素
* play\(\)：播放音频或视频
* pause\(\)：暂停音频或视频

### 事件

* loadstart：浏览器开始寻找指定的音频或视频
* progress：浏览器正在下载指定的音频或视频
* durationchange：音频或视频的时长已改变
* loadedmetadata：音频或视频的元数据已加载
* loadeddata：音频或视频的当前帧已加载，但没有足够数据播放下一帧
* canplay：浏览器能够开始播放指定的音频或视频
* canplaythrough：音频或视频能够不停顿地一直播放
* progress：浏览器正在下载指定的音频或视频




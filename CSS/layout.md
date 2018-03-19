## 各种布局

* ### 静态布局

  * 传统布局，所有元素尺寸使用px作为单位

  * 设置min-width，如果小于这个宽度则显示滚动条

  * 使用情况：

    * PC端：居中布局，不随页面大小的改变而改变

    * 手机端：

      * viewport meta标签上设置width=320，然后通过JS设置缩放的大小，使宽度正好占满屏幕

      * viewport meta 标签设置width=640,user-scalable=no，640px超过手机宽度，浏览器会自动缩小页面到刚好全屏

  * 优缺点：

    * 优点：简单，没有兼容问题

    * 缺点：缩放后的显示
* ### 流式布局

  * 页面元素的宽度按照屏幕分辨率进行适配调整

  * 使用百分数，搭配min-\*,max-\*属性使用定义宽度，高度使用px固定

  * 缺点：宽度使用百分比，而字体和高度使用px固定，在宽屏会使比例不协调
* ### 自适应布局

  * 创建多个静态布局，每个静态布局对应一个屏幕分辨率范围

  * 使用@media，对不同的尺寸和设备切换不同的样式
* ### 响应式布局

  * 每个屏幕分辨率下一个布局样式

  * 媒体查询+流式布局，即@media+百分比布局
* ### rem、em布局

  * 定义

    * rem：相对于根元素html的字体大小

    * em：相对于父元素的字体大小

  * 详细见[rem](/CSS/rem.md)



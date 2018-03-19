## REM

* ### 定义

相对于根元素html的字体大小的单位

em：相对于父元素的字体大小的单位

* ### 实现手机端响应式布局的方法

  * 流式布局：宽度百分比+高度固定px

  * 固定宽度

  * 响应式

  * 设置viewport进行缩放

  ```
  <meta name="viewport" content="width=320,maximum-scale=1.3,user-scalable=no">
  ```

  * rem
* ### 实现方式

  * rem的设置方法

    * 根据设计稿配置匹配当前分辨率的样式

    * 对于其他的分辨率

      * font-size的大小：其他分辨率/设置稿匹配的分辨率\*目前设置的字体大小

      * 例：设计稿640px，字体大小20px

        * 对于320px的页面，字体大小=320/640 \* 20 = 10px

    * px和rem的转换

      * 对于根font-size:10px的情况

      * 100px的宽度 = 10rem的宽度，即100/10rem

  * 使用媒体查询的方式，对于每个屏幕分辨率定义不同的font-size

  ```
  html{
      font-size:20px;
  }
  @media only screen and (min-width:401px){
      html{
          font-size:25px;
      }
  }
  ```

  * 使用js，适配所有的屏幕




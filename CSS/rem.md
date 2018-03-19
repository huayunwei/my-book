## REM

* ### 定义

相对于根元素html的字体大小的单位

em：相对于父元素的字体大小的单位

* ### px和rem的转换

  * 首先给定html的font-size的大小：font-size:10px

    * html字体到底给多大？

      * 一般浏览器字体默认为16px，如果1rem = 16px;如果手动计算，会很麻烦

      * 为了方便计算，给定1rem = 10px

      * 但是一般会设置html的字体大小为62.5% ，即10/16 \*100%，因为有些浏览器默认不是16px的字体

      * 如果设置成62.5%对于那些不支持小于12px字体的浏览器，会默认取12px计算

      * 最后的方式：设置html为100px，body设置为16px，此时1rem = 100px，而body的字体仍是16px，不会影响浏览器默认字体大小

  * .css文件：手动计算或在网上搜索在线转换工具

    * 如p{width:20px;}，则20px/10px \* 1rem = 2rem

  * .sass文件

    * 首先设置一个常量：$root = 10px;

    * 设置html的font-size值：html{font-size:$root}

    * 使用@function：

      ```
      @function pxToRem($px){
          @return $px / $root * 1rem;
      }

      p{
          width:pxToRem(100px);//会自动转换
      }
      //缺点：对于padding:10px 10px;
      padding:pxToRem(10px 10px);//报错
      padding:pxToRem(10px) pxToRem(10px);
      ```

    * 使用@min：https://www.w3cplus.com/preprocessor/sass-px-to-rem-with-mixin-and-function.html

  * .less文件
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

  ```
  /*
      设置根节点font-size
      @params:designWidth - 设计稿的宽度
      @params:maxWidth - 制作稿的最大宽度
  */
  ```




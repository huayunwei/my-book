

### express

* 安装

  `npm install express`

* 使用

  `var express = require('express');`

* 启动

  `node xx.js//xx为引入express的文件`

* 生成器 -- 可以直接生成一个项目的框架

  * 安装

    `npm install express-generator -g`

  * 使用

    `express name`

### app - express的应用实例

* 创建

  `var app = express();`

* 路由

  * 基本形式

    `app.method(path,callback);`

    * method：HTTP请求的方式中的一个

    * path：路径,可以是字符串或正则或/:id的形式

    * callback：匹配到路径后的执行函数,函数有两个参数-下面介绍的request和response

  * app.get\(\)：http为get方法时

    `app.get('path',function(req,res){})`

  * app.post\(\)：http为post方法时

    `app.post('path',function(req,res){})`

  * app.all\(\)：所有类型的http请求都会进行处理

    `app.all('path',function(req,res){})`

  * app.router\(\)：定义一个路径的多个http请求类型的处理

    ```javascript
      app.router('path')
          .get(function(req,res){})
          .post(function(req,res){})
          ....
    ```

  * 多个callback的情况 -- 必须要有next，否则不执行后面的callback

    * 多函数

      ```javascript
        app.get('/',function(req,res){
            next();
        },function(req,res){});
      ```

    * 函数数组

      ```
        function e1(){next();}//如果没有next则不会执行e2
        function e2(){}
        app.get('/',[e1,e2]);
      ```

    * 多函数和函数数据的组合

      ```
        app.get('/',[e1,e2],function(){next()},function(){})
      ```

  * 对多个二级路由的处理

    ```javascript
      1. 可以直接定义多个二级路由
          app.get('p/child1',function(){})
          app.get('p/child2',function(){})
          ...
      2. 定义单独的文件
          //app.js中定义一级路由
          import child from 'xx.js'
          app.use(p,child);

          //xx.js中定义不同的二级路由执行的操作
          app.get('/',function(){});//就是一级路由
          app.get('/xx',function(){});//二级为xx的路由
    ```

* 监听 -- 还有其他参数

  * app.listen\(port,function\(\){
      //绑定并监听port端口
    }\)

* 管理静态文件

  * 不指定目录

    ```javascript
      //例：./path/img/1.jpg

      //其中path第一层必须是和node xx.js这个xx.js文件处于同一级的目录
      //path可以是多级的即xx/xx也可以
      app.use(express.static(path));

      //在html中的使用
      <img src="/img/1.jpg">
    ```

  * 指定目录

    ```javascript
      //例：./path/img/1.jpg

      app.use("/myPath",express.static(path));
      //在html中的使用
      <img src="/myPath/img/1.jpg">
    ```

  * 可以定义多个 --- 待更新

  * 参数的设置 --- 待更新

* app.use\(\) --- 使用中间件

  * 使用应用级中间件 --- 同app.method\(\)，作为路由

    ```javascript
      app.use('path',function(){})
    ```

  * 使用错误处理中间件 --- 见下面的错误处理

  * 使用内置中间件 --- static,使用方法见上面的管理静态文件

  * 使用第三方中间件

    * 安装

      `npm install xxx`

    * 引入

      `var a = require('xxx');`

    * 加载

      `app.use(xxx);`

* 模板引擎

  * 设置放置模板的位置

    `app.set('views','path')`

  * 设置解析模板的引擎

    `app.set('view engine','engine name');`

  * 注意点：

    1.如果不设置模板引擎，则在渲染时需要写出文件的后缀，即文件的类型

    2.如果不设置模板位置，则模板放置的位置必须为根目录下的views

* 模板渲染 -- 一直使用的res.render\(\)，推荐使用这个渲染

  ```javascript
    //参数：
    //    view：模板
    //    data：传入到模板的数据
    //     fn回调
    app.render(view,data,function(err,html){});
  ```

* 错误处理

  ```javascript
    //在所有路由的最后定义,表示没有匹配上上面的路由时，匹配这个
    app.use(function(err,req,res,next){
        res.status(500).render('err.html');
        res.status(404).render('404.html');//处理404状态
    })
  ```

### request\(req\) --- 请求

* req.query

* req.hostname --- hostname值无端口号

* req.ip --- hostname对应的ip地址

* req.params --- /:xx这种形式匹配到的值,例如/p/:id==&gt;/p/xx==&gt;req.params.id=xx

* req.path --- 路径

* req.protocol --- 协议类型

* req.query --- url?后的值

### response\(res\) --- 响应

* res.send\(data\) --- 向客户端发送data

* res.render\(view,data,fn\) --- 渲染模板

* res.status\(\) --- 设置http响应状态

* res.redirect\(\[status,\]path\) --- 重定向,默认status为302，重定向到path

* res.sendStatus\(status\) --- 等同于res.status\(\).send\(状态对应的英文含义\)

* res.download\(\) --- ?  下载？

* res.jsonp\({key:value}\) --- 给出返回函数，返回jsonp，否则返回json格式






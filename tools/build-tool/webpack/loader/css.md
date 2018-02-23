## CSS相关的loader

### style-loader - 用于将css加入到打包后的js文件中

* style-loader/useable

```
module:{
    rules:[
        {
            test:/\.css$/,
            use:[
                {loader:'style-loader/useable'},
                {loader:'css-loader'}
            ]
        }
    ]
}

//入口文件中
import index from 'index.css'
index.use();//使用index样式
index.unuse();//不使用index样式
```

* options

  1. insertAt：插入位置

  2. insertInto：插入到dom

  3. singleton：是否只使用一个style标签

  4. transform：转化

### css-loader - 允许css文件以import的形式添加到.js文件中

* options  
  1. alias：解析的别名  
  2. importLoader  
  3. minimize：是否压缩  
  4. modules：启用css-modules

  ```markdown
  module:{
      rules:[
          {
              test:/\.css$/,
              use:[
                  {loader:'style-loader'},
                  {
                      loader:'css-loader',
                      options:{
                          minimize:true//去掉空白
                      }
                  }
              ]
          }
      ]
  }
  ```

### css-loader和style-loader在配置中的写法

```markdown
module:{
    rules:[
        {
            test:/\.css$/,
            use:[
            //use的执行方式：从后开始执行，执行后的内容交给前面的进行处理
                {loader:'style-loader'},
                {loader:'css-loader'}
            ]
        }
    ]
}

//在html引入打包后的js文件，即可以使用css，css会被直接添加到head中
<script src="app.bundle.js"></script>
```

### sass-loader

* 安装

```
npm install less-loader less --save-dev
```

### lass-loader

* 安装

```
npm install sass-loader node-sass --save-dev
```

### sass-loader,lass-loader使用方法

```
module:{
    rules:[
        {
            test:/\.less$/,(sass则为/.\scss$/)
            use:['style-loader','css-loader','less-loader'(scss为sass-loader)]
        }
    ]
}
```

### 提取css文件 -- 使用[ExtractTextWebpackPlugin](/tools/build-tool/webpack/plugins/ExtractTextWebpackPlugin.md)插件

### PostCSS -- 对css的一些转化

* 相关插件  
  1. autoprefixer：添加浏览器前缀  
  2. postcss-cssnano：等同于css-loader的minimize选项，进行压缩  
  3. postcss-cssnext

* 安装




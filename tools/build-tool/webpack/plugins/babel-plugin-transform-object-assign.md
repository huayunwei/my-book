## babel-plugin-transform-object-assign

* ### 作用：用于处理babel对Object.assign不转换的问题
* ### 安装：

```
npm install --save-dev babel-plugin-transform-object-assign
```

* ### 使用：

  * .babelrc文件中

  ```
  plugins:[
      "transform-object-assign"
  ]
  ```

  * webpack.config.js文件中

  ```
  module:{
      rules:[
          {
              test:/\.js$/,
              loader:'babel-loader',
              query:{
                  plugins:['transform-object-assign']
              }
          }
      ]
  }
  ```






## UglifyJsPlugin

* 作用：删除无用的js代码，压缩js代码，将代码中的变量定义成a,b,c短变量形式

* 使用

```markdown
plugins:[
    new Webpack.optimize.UglifyJsPlugin()
]
```

* 问题
  * 插件本身不支持ES6，所以如果使用了ES6的代码，必须同时使用babel-loader




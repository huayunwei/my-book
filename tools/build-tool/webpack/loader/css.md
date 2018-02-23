## CSS相关的loader

### style-loader - 用于将css加入到打包后的js文件中

### css-loader - 允许css文件以import的形式添加到.js文件中

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

//在html引入打包后的js文件，即可以使用css
<script src="app.bundle.js"></script>
```

### sass-loader

### lass-loader




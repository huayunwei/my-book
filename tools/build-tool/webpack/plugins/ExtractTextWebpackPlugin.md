## ExtractTextWebpackPlugin -- 提取css

* 安装

```
npm install extract-text-webpack-plugin --save-dev
```

* 引入

```
const ExtractTextWebpackPlugin = requrie('extract-text-webpack-plugin');
```

* 使用

```
modules:{
    rules:[
        {
            test:/\.css$/,
            use:ExtractTextWebpackPlugin.extract({
                fallback:{
                    loader:'style-loader'
                },
                use:['css-loader']
            })
        }
    ]
},
plugins:[
    new ExtractTextWebpackPlugin({
        filename:'[name].min.css'
    })
]

//手动在html中添加link标签引入提取后的css文件
<link rel="styleSheet" href="xxx.min.css" />
```




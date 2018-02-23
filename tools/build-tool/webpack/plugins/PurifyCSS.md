## PurifyCSS

* 作用：删除css中没有使用的样式
* 安装

```
npm install purifycss-webpack glob-all --save-dev
```

* 使用

```
var PurifyCSS = require('purifycss-webpack')
plugins:[
    new PurifyCSS({
        path:glob.sync([
            path.join(__dirname,'会使用到css类名或id名的文件的地址')
        ])
    })
]
```




## CommonsChunkPlugin：打包公共代码

* 写法

```markdown
var webpack = require('webpack');
module.exports={
    entry:{},
    output:{},
    plugins:[
        new webpack.optimize.CommonsChunkPlugin(opt)
    ]
}
```




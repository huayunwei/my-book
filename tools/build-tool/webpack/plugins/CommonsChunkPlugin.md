## CommonsChunkPlugin：打包公共代码

* 基本写法

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

* opt的值
* 实例
  * 提取代码中的公共代码

  ```markdown
  //将指定次数的公共代码提取到一个公共文件中
  ```

  * 提取第三方代码
  * 分别提取第三方代码和webpack的代码
  * 分别提取业务代码中的公共代码和第三方代码和webpack代码




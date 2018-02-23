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

  A.js  B.js  jquery.js

  * 提取代码中的公共代码

  ```markdown
  //将指定次数的公共代码提取到一个公共文件中
  const path = require('path');
  const webpack = require('webpack');

  module.exports={
      entry:{
          A:'A.js',
          B:'B.js',
          //jquery:'jquery'即使在入口中添加了jquery，jquery的代码依旧会被作为公共代码打包到common文件中
      },
      output:{
          path:path.resolve(__dirname,'build'),
          filename:'[name].bundle.js'
      },
      plugins:[
          new webpack.optimize.CommonsChunkPlugin({
              name:'common',//公共代码打包后的名字common.bundle.js
              minChunks:2//最少出现多少次会被认为是公共代码被打包
          })
      ]
  }

  //build文件下的文件
  A.bundle.js B.bundle.js common.bundle.js (如果entry中有jquery.js则会输出jquery.bundle.js但是里面没有内容)
  ```

  * 提取第三方代码

  ```markdown
  //将webpack和第三方代码提取到一个文件中
  const path = require('path');
  const webpack = require('webpack');

  module.exports={
      entry:{
          A:'A.js',
          B:'B.js',
          jquery:'jquery'//第三方库必须加入到入口文件中，否则不会进行提取
      },
      output:{
          path:path.resolve(__dirname,'build'),
          filename:'[name].bundle.js'
      },
      plugins:[
          new webpack.optimize.CommonsChunkPlugin({
              name:'jquery',//第三方库打包的名字
              //如果名字和入口文件的名字不一致，会将webpack打包到此处定义的文件中，而将入口文件中定义的第三方库打包到另外的文件中
              //只定义名字不定义minChunks或minChunks定义为Infinity
              //如果定义了minChunks为具体数字，则同上面的情况
          })
      ]
  }


  ```

  * 分别提取第三方代码和webpack的代码
  * 分别提取业务代码中的公共代码和第三方代码和webpack代码




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
  1. name:string/array 打包后文件的name值,打包后文件的整体名字是根据output中定义的filename定义的
  2. filename：忽略output中的filename定义，而是使用此处定义的名字作为打包后文件的名字
  3. minChunks：最少出现多少次就被认定为公共代码进行提取
  4. chunks：提取代码的范围
  5. children：是否在子模块中查找
  6. deepChildren：是否在所有子模块都查找
  7. async：异步代码块

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

  //build文件夹下的文件
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
              name:'jquery',//第三方库打包的名字,会将webpack和第三方库打包该文件中

              //如果名字和入口文件的名字不一致，会将webpack打包到此处定义的文件中，而将入口文件中定义的第三方库打包到另外的文件中

              //minChunks定义为Infinity(无穷次)或多于业务代码中公共代码的出现次数，都会等同于只定义name的情况
          })
      ]
  }

  //build文件夹下的文件
  A.bundle.js B.bundle.js jquery.bundle.js(webpack和jquery都被打包在该文件中)
  ```

  * 分别提取第三方代码和webpack的代码

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
              name:['jquery','webpack'],
              //如果定义了filename,则在build文件夹中打包文件名为：jquery.js和webpack.js
              //filename:[name].js
          })
      ]
  }

  //build文件夹下的文件
  A.bundle.js B.bundle.js jquery.bundle.js(只有jquery代码) webpack.bundle.js(只有webpack代码)
  ```

  * 分别提取业务代码中的公共代码和第三方代码和webpack代码

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
              name:'common',//A和B中的公共代码会被提取到common文件中
              minChunks:2,
              chunks:['A','B']//指定提取代码的范围，如果不指定会报错
          }),
          new webpack.optimize.CommonsChunkPlugin({
              name:['jquery','webpack']
          })
      ]
  }

  //build文件夹下的文件
  A.bundle.js B.bundle.js common.bundle.js(A,B中公共代码) jquery.bundle.js(只有jquery代码) webpack.bundle.js(只有webpack代码)
  ```




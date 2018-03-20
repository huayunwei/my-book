## clean-webpack-plugin -- 用于清空输出文件夹

* 会删除文件夹和文件夹下所有内容
* 安装

```
npm install clean-webpack-plugin --save-dev
```

* 使用

```
const CleanWebpackPlugin = require('clean-webpack-plugin');

plugins:[
    new CleanWebpackPlugin(['文件名']);
]
```




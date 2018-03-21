## Linux命令

### linux命令查询网站：[https://explainshell.com](https://explainshell.com)![](/assets/linux_command.png)

### 常用命令

* cd：进入目录
  * cd 目录名：进入到该目录
  * cd ..：进入上一级目录
* pwd：显示当前目录
* mkdir：创建目录
  * mkdir 目录名
  * mkdir -p 目录路径
* whoami：当前用户
* ls：查看当前路径下的内容
  * ls -a：显示当前路径所有内容，包括隐藏的以点和点点开头的路径
  * ls -l：显示当前路径下的内容和对应的详细信息，不包括隐藏的内容
  * ls -al：显示当前路径下的全部内容和对应的详细信息

  ![](/assets/linux_ls.png)
* cat：查看文件内容
  * cat 文件路径：显示文件内容不可以编辑
* vim：查看和编辑文件内容
  * vim 文件路径
    * 编辑模式：i
    * 保存：esc+:w
    * 退出：esc+:q
    * 强制退出：esc+:q!
* echo：输出
  * echo 内容&gt; 文件路径：将文件创建在路径下，并且将内容插入

  * echo 内容 &gt;&gt; 文件路径：在文件中追加内容
* touch：创建文件
  * touch 文件名
* mv：移动文件
  * mv 文件名 新文件名 ：移动加重命名
* rm：删除
  * rm 文件路径：删除文件
  * rm -f 文件路径：强制删除文件
  * rm -r 目录路径：删除目录
  * rm -rf 目录路径：强制删除目录
* tree：查看目录结构
* ln：建立软连接
  * ln -s 真实文件 链接
* curl：
  * curl -L urld地址：下载文件
* wget：
  * wget -p -H -e robots=off url地址：拷贝网页
* df：
  * df -kh：显示磁盘占用
* du：
  * du -sh：显示当前目录大小
  * du -h：显示各个文件的大小




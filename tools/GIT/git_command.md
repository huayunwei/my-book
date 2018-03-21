## git相关命令

* git init：初始化一个git仓库

  * 会在当前文件夹下生成.git文件夹
    * .git文件夹包括：git配置文件，项目的快照数据等
  * 在git bash中当前文件夹后会显示\(master\)字样

  ![](/assets/git_init.png)

* git remote：远程仓库的相关配置

  * git remote add 远程仓库名字 远程仓库地址：添加远程仓库

  * git remote -v ：查看添加的远程仓库列表

  * git remote show 远程仓库的名字：查看该远程仓库的详细信息

  * git remote rename 原来的名字 新名字：修改远程仓库的名字

  * git remote rm 远程仓库的名字：删除该远程仓库

* git add：将文件添加到缓存中

  * git add xxx：将xxx文件添加到缓存中

  * git add xxx yyy ：将xxx和yyy文件添加到缓存中

  * git add .：将当前目录下的所有文件和子文件夹下的文件都添加到缓存中

* git commit：提交缓存中的文件到仓库中

  * git commit -m 描述信息：对提交的文件添加描述信息

* git status：查看提交之后是否还有被修改的文件

* git push：

* git clone：




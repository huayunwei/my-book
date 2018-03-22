## 建站的服务器配置

### 网站的域名，服务器
* 域名 -- 可以在阿里云购买，需要实名制

* 服务器 -- 可以在阿里云购买

* 域名备案 -- 在阿里云购买域名和服务器，则可以直接在阿里云进行备案

	* 初次备案个人网站的基本步骤：
		* [备案地址](https://beian.aliyun.com)
		
		* 填写好基本网站信息后，需要上传身份证照，签字单据的扫描件
		
		* 上一步通过后，需要将填写的单据邮递给阿里云，同时申请一块拍照用的幕布，收到后拍照上传
		
		* 等待工信部的审核

* 域名的解析 -- 可以购买阿里云的云解析或使用其他

	* 云解析：控制台 - 域名和网站 - 云解析DNS - 点击域名 - 添加解析
		* 记录类型：
		
			* A：将域名指向一个IPV4地址，即记录值填写IP地址
			
			* CNAME：将域名指向另一个域名，即记录值填写域名
			
		* 主机记录：域名前缀，如二级域名xxx.baidu.com中的xxx
		
		* 解析线路：DNS解析的路径，目前不知道区别，选的默认
		
		* 记录值：根据记录类型的不同，填写不同的值，如果记录类型为A，则填写购买的服务器的对外IP地址
		
		* TTL值：解析的缓存时间


### 服务器的环境配置

* 服务器的操作系统版本 -- ubtunu16

* 关于硬盘：买服务器会自带一块硬盘，会直接挂载，如果多买了需要手动挂载

	挂载步骤：[参考文档](https://jingyan.baidu.com/article/90808022d2e9a3fd91c80fe9.html)
	
	* 查看所有分区：df -h：看所有分区的总大小和购买的大小是否一致
	
	* fdisk -l：可以查看所有的盘
	
	* 对未挂载的盘先进行分区：fdisk -S 56 /dev/盘name
	
	* 对分区进行格式化：mkfs.ext3 /dev/盘name
	
	* 永久挂载 vim /etc/fstab文件，添加如下内容
			/dev/分区名 /本地一个用于挂载的文件夹 ext4 defaults 0 0
			
	* mount -a：挂载	
	
	* df -h ：查看一下是否挂载成功
		
* 配置一个普通权限的用户：`adduser 用户名`

* 切换到新创建的用户：`su 用户名`

* 修改ssh默认的22端口
	
	* 修改ssh配置：`vim /etc/ssh/sshd_config` 里Port 22//端口号，可以修改成0-1024之外的值`

	* 重启ssh服务：`service ssh restart`

	* 查看ssh是否监听的是新修改的端口号：`netstat -natlp` 

	注：上述步骤完成后，还需在阿里云的实例-管理-本实例安全组-配置规则-增加一条端口号为你上面配置的端口号的规则，在入方向里

	* 以新的端口号进行链接

* 配置防火墙

	* 清空所有的iptables规则
		
		`iptables -F`
	
	* 创建防火墙配置文件
		
		`vim /etc/iptables.up.rules`
	
		
		```
		* filter

		# allow all connect
		-A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT 

		# 
		-A OUTPUT -j ACCEPT

		# allow http https
		-A INPUT -p tcp --dport 443 -j ACCEPT
		-A INPUT -p tcp --dport 80 -j ACCEPT

		# allow ssh port 9908
		-A INPUT -p tcp -m state --state NEW --dport 9908 -j ACCEPT


		#ping
		-A INPUT -p icmp -m icmp --icmp-type 8 -j ACCEPT

		# log for denied calls
		-A INPUT -m limit --limit  5/min -j LOG --log-prefix "iptables denie:" --log-level 7

		# drop incoming sensitive connections
		-A INPUT -p tcp --dport 80 -i eth0 -m state --state NEW -m recent --set
		-A INPUT -p tcp --dport 80 -i tho0 -m state --state NEW -m recent --update --seconds 60 --hitcount 150 -j DROP

		# reject all other inbound
		-A INPUT -j REJECT
		-A FORWARD -j REJECT

		COMMIT

		```
	* 指定防火墙的配置文件为iptables.up.rules
	
		`iptables-restore < /etc/iptables.up.rules`
	* 查看所有配置成功的规则
	
		`iptables -L`
	
	* 设置开机之后防火墙的配置默认为/etc/iptables.up.rules
	
		```
		//创建文件
		vim /etc/networt/if-up.d/iptables
		//文件内容
		#!/bin/sh
		iptables-restore /etc/iptables.up.rules
		//给文件执行的权限
		chmod +x /etc/network/if-up.d/iptables
		```

* 配置Fail2Ban -- 监控系统日志文件中检测到的可疑行为，做出不同的处理

	* 安装：`apt-get install failtoban`

	* 修改配置文件：`vim /etc/fail2ban/jail.conf `

	* 查看服务状态：`service fail2ban status`

	* 停止服务：`service fail2ban stop`
	
* 配置node.js环境 -- 注意：环境要安装在后期代码所处的环境，如果在root下安装，而代码在其他用户下，node是无法使用的
	* 安装一些依赖包：`apt-get install vim openssl build-essential libssl-dev wget curl git`

	* 安装nvm工具,用于管理node.js的不同版本,[nvm地址](https://github.com/creationix/nvm)
	
		`wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.33.8/install.sh | bash`

	* 用nvm安装node.js -- 如果在当前页面提示没有nvm这个命令，退出后再登录就好了

		`nvm install 8.9.4`

	* nvm配置当前和默认node版本 -- 如果只安装了一个node版本，则默认使用当前版本，不需要配置
	
		`nvm use 8.9.4`
		
		`nvm alias default 8.9.4`

	* 查看node版本

		`node -v`

	* 配置npm为国内淘宝源
	
		`npm config set registry http://registry.npm.taobao.org`

* 配置数据库 -- 可以在阿里云购买mongodb数据库，下面是在服务器上自己搭建mongodb数据库的步骤

	* 具体参考步骤：[mongodb.md]()
	
	* 安装：[官网安装步骤](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/)
	
	* 开启服务：

		`service mongod start`

	* 修改mongo的默认端口号 -- /etc/ipatables.up.rules和阿里云实例的安装组
		* 在/etc/iptables.up.rules里添加如下内容
		
			```
			# mongoDB connect
			-A INPUT -s 127.0.0.1 -p tcp --destination-port 10000 -m state --state NEW,ESTABLISHED -j ACCEPT
			-A OUTPUT -d 127.0.0.1 -p tcp --source-port 10000 -m state --state NEW,ESTABLISHED -j ACCEPT
			```
		* 更新防火墙的配置文件：
		
			`iptables-restore < /etc/iptables.up.rules`
		
		* 使用新的端口号登录mongo

			`mongo 127.0.0.1:10000`

	* 将本地的数据库上传到服务器上
	
		* 开启本地的数据库服务
		
		* 在本地使用下面的命令下载数据库

			`mongodump -h 数据库ip:数据库端口号 -d 数据库名字 -o 下载后的地址`

		* 将下载的数据库数据打包上传
			* 打包
				
				`tar zcvf 打包后的名字.tar.gz 打包的文件名`

			* 上传 -- 本地执行以下命令

				`scp -P 服务器端口号 打包文件名 登录名@服务器ip地址:上传后文件的路径`

			* 解压缩

				`tar xvf 包名`

			* 更新到服务器上的数据库
				
				`mongorestore --host 数据ip地址:端口号 -d 数据库名 解压缩后的文件的路径`


	* 数据库的备份 --- 待更新


* PM2链接私有云仓库和服务器 -- 实现本地更新后服务器代码同步更新

	* 上传代码到私有云仓库 -- 因为github的私有仓库是要收取费用的，所以使用码云
		* 操作同上传github
		
	* 安装pm2

		`npm install pm2 -g`

	* [pm2操作手册]()

	* 编写配置文件 -- ecosystem.json
		* 文件内容
			
			``

	* 部署 -- 在本地执行
		* 部署生产环境
		
			`pm2 deploy ecosystem.json production setup`
		* 部署开发环境
		
			`pm2 deploy ecosystem.json staging setup`

	* 发布
		* 生产环境
		
			`pm2 deploy ecosystem.json production`
		* 开发环境
		
			`pm2 deploy ecosystem.json staging` 


### 配置nginx
	
	* 路径
		`/etc/nginx/conf.d`
	* 创建文件
	
		
```
upstream shaoli{
	server 127.0.0.1:3080;
}

server{
	listen 80;
	
	server_name shaoli.huayunwei.cn;

		location /{
		proxy_set_header X-Real-IP $remote_addr;
		proxy_set_header X-Forward-For $proxy_add_x_forwarded_for;
		
		proxy_set_header Host $http_host;
		proxy_set_header X-Nginx-Proxy true;

		proxy_pass http://shaoli;
		proxy_redirect off;
	}
	//使用服务器上的静态文件
	//如果按照如下方式定义如果1.mp3在current文件夹下，则直接http://xxx/1.mp3就可以访问到
	如果是在current/map/1.mp3，通过http://xxx/map/1.mp3可以访问
	location ~* ^.+\.(mp3){
		root /huayunwei/www/shaoli/production/current;
		client_max_body_size 50M;//上传文件的大小




	}
}

```








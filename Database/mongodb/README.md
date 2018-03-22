### mongodb
* 简介：基于分布式文件存储的开源数据库系统
	* 数据存储为一个文档
	* 数据结构为键值对
	* 常见术语：
		
	```
	1.collection：集合(sql数据中的数据库表)
	2.document：文档(sql数据库中的行)
	3.field：域(sql数据库中的字段)
	```
* 安装：
	* window

		```
		1.[官网](https://www.mongodb.com/download-center#community)下载
		2.必须要手动建数据目录，否则无法使用
			例如数据目录存放在d盘：在d盘建立一个data的文件夹,在data中创建一个db文件夹
		```
	* linux
	
		```
		1.[官网安装步骤 -- ubuntu](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/)
		2.步骤简述：
			2.1添加public key：
				在服务器命令行上输入：
					sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 2930ADAE8CAF5059EE73BB4B58712A2291FA4AD5

			2.2为配置文件创建一个列表：版本不同命令不同，以16.04为例
				在服务器命令行输入：
					echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.6 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.6.list

			2.3更新包：sudo apt-get update

			2.4安装mongodb：sudo apt-get install -y mongodb-org
		```


* 基本语法
	
	* 开启服务 	
		* window：cmd.exe下

			`mongodb安装目录\mongodb\bin\mongod.exe --dbpath d:\data\db(数据目录地址)`

		* Linux：

			`service mongod start`

	* 链接mongodb
		* window：cmd.exe下

		 	`mongodb安装目录\mongodb\bin\mongo.exe`

		 * Linux

		 	`mongo`

	* 用户
		* 用户创建
	

	* 数据库
		* 创建：`use database-name` -- 如果有这个数据库则进入数据库，否则创建并进入
		* 显示：`show dbs`
		* 删除：`use xx(要删除的数据库) --> db.dropDatabase()`

	* 集合
		* 创建：`db.name.insert({xxx})//直接插入文档，如果集合不存在则创建`
		* 显示：`show tables`
		* 删除：`db.name.drop()`

	* 文档
		* 插入：`db.collection-name.insert/save({xxx})`
		* 查找：
			* query-查询条件，不写查询全部，{key:value}键值对的形式
				* and：{key1:value1,key2:value2}
				* or：{$or:[{key1:value1},{key2:value2}]}
				* 相等：{key:value}
				* 小于：{key:{$lt:value}}
				* 小于或等于：{key:{$lte:value}}
				* 大于：{key:{$gt:{$gt:value}}}
				* 大于等于：{key:{$gte:value}}
				* 不等于：{key:{$ne:value}}
				* 类型：$type
			* 全部
				
				`db.collection-name.find(query)`
			* 一个

				`db.collection-name.findOne(query)`
			* 数量：查找指定数量(num)的值,exec用于执行查询后的回调

				`db.collection-name.find().limit(num)`
			* 跳过：结果跳过指定数量(num)的值显示其他的,num默认为0 --- 测试一下全集和skip的时间

				`db.collection-name.find().limit().skip(num)`
			* 格式化：-- 没试过

				`db.collection-name.find().pretty()`

			* 排序：1为升序，-1为降序
				
				`db.collection-name.find().sort({key-name:1/-1})`	

		* 更新：

			```
			db.collection-name.update({query:value},{update:value},{
				upsert:boolean,//可选，不存在根据query找到的内容，是否插入更新内容，默认为不插入
				multi:boolean//可选，是否只更新第一个符合的值，默认true都更新
			})

			```
		* 删除：删除根据query超找出的结果，参数juseOne可选，默认为true，只删除一个文档
		
			`db.collenction-name.remove({query:value},{juseOne:boolean})//`

		* 聚合：用于处理数据，返回处理后的值

		* 自增长：\_id字段的自增长

* 可视化工具 --- robo3t


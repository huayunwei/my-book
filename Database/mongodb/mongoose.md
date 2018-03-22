<<<<<<< HEAD
### 配合express的mongoose -- 在node环境下链接和操作mongodb的库
* 安装

	`npm install mongoose --save`
* 链接mongodb
	
```javascript
//引入mongoose
const mongoose = require('mongoose');
/*
	链接数据库
	user：登录数据的用户名
	passwd：对应的密码
	url：数据库地址
	port：端口号，默认27017
	database：要链接的数据库名字
*/

mongoose.connect('mongodb://user:passwd@url:port/database');

//监听数据库链接状态
const conn = mongoose.connection;
conn.on('connected',fn)：监听是否链接成功
conn.on('disconnected',fn)：监听是否断开链接
```


* 对应于mongodb的collection的Model+Schema
	* Schema：必须有,Model根据Schema进行创建，定义Model的字段，类型，公共方法等
		-- 但是Schema是否需要定义全部的Model字段？

```javascript
const Schema = mongoose.Schema;

/*
	key：字段名
	type：字段数据类型(String,Number,Date,Buffer,Boolean,Mixed,ObjectId,Array)
*/

const name = new Schema({
		key:type,
		key:[{key1:type}],
		key:{type:value1,defaul:value2},
		key:{key1:type,key2:type}
	})

//model公共方法
Schema.methods.fn = function(){}

//设置索引
1.设置在Schema中
new Schema({
	name:{type:String,index:true}
})

2.在Schema实例中设置
const name = new Schema();
name.index({name:1,type:-1});//其中1代表正序，-1代表逆序



//字段的检验 --  使用save时会自动检测
1.required：必填字段
new Schema({
	name:{
		type:String,
		required:[true,"错误提示信息"]
	}
})

2.min,max：对Number类型的数据的限制
new Schema({
	name:{
		type:Number,
		min:num,
		max:num
	}
})

3.match,maxlength,minlength：对字符串的检测
new Schema({
	name:{
		type:String,
		match://,
		maxlength:num,
		minlength:num
	}
})

4.自定义验证：
new Schema({
	name:{
		type:String,
		validate:{
			validator(){return xxx},
			message:
		}
	}
})

```

	

	* 根据Schema创建model

```javascript
//此时创建的model-name并不是数据库中collection的名字，而是他的单数形式，在数据库应该为model-name+'s'
const xxx = mongoose.model('model-name','Schema实例名字')
```
	
	* 使用model操作mongodb数据库
		* 向collection中插入document

```javascript
//key，value为要插入到model即mongodb中对应collection的值，如果collection不存在，会默认创建 ---- 如果手动建collection会导致model无法和collection联系在一起

model.save({key：value}).then(fn);
```
		* 查询
			* find：没有找到返回空数组

```javascript
/*
	参数1：查询的条件
	参数2：只在所写的字段下进行查询,-filed：代表不在该字段下进行查找
	参数3：一些内置方法，例如limit,skip等
	参数4：找到数据后执行的回调
*/
model.find({key:value},'filed1 filed2',{method:value},function(){})

model.find({key:value}).method().exce(function(){})//同上
```
			* findById：根据_id字段找对应的文档
				
```javascript
model.findById(id[,'filed1 filed2'],function(){})

model.findById(id).method().exec();

model.findById().exec();
```

			* findOne：只找一个值，第一个匹配的？没有找到返回null

		* 更新
				* update
	
				* updateMany
	
				* updateOne
	
				* findOneAndUpdate：查找并更新
				
```javascript
/*
	参数1：查找条件
	参数2：更新的内容
	参数3：选项
	参数4：回调
*/
model.findOneAndUpdate(query,update,options,callback);
```

			* findByIdAndUpdate：根据id查找并更新

```javascript
model.findByIdAndUpdate(id,update,options,callback)
```

		* 删除
			* remove/deleteMany：删除所有匹配的文档

```javascript
model.remove({key:value},function(){})
```

			* deleteOne：删除第一个匹配的文档

```
model.deleteOne({key:value},function(){})
```
			
			* findOneAndRemove：查找并删除

```
model.findOneAndRemove({key:value},options,fn);
```

			* findByIdAndRemove：通过id查找并删除	

		* 数量
		
				* count：返回匹配的文档的数量
				model.count({key:value},function(){})

	
		* 字段的自增


* 常用method
	* select
	* distinct
	* slice
	* limit：返回结果的长度
	* skip：跳过
	* sort：根据指定字段排序，1升序，-1降序
=======
### 配合express的mongoose -- 在node环境下链接和操作mongodb的库
* 安装

	`npm install mongoose --save`
* 链接mongodb
	
```javascript
//引入mongoose
const mongoose = require('mongoose');
/*
	链接数据库
	user：登录数据的用户名
	passwd：对应的密码
	url：数据库地址
	port：端口号，默认27017
	database：要链接的数据库名字
*/

mongoose.connect('mongodb://user:passwd@url:port/database');

//监听数据库链接状态
const conn = mongoose.connection;
conn.on('connected',fn)：监听是否链接成功
conn.on('disconnected',fn)：监听是否断开链接
```


* 对应于mongodb的collection的Model+Schema
	* Schema：必须有,Model根据Schema进行创建，定义Model的字段，类型，公共方法等
		-- 但是Schema是否需要定义全部的Model字段？

```javascript
const Schema = mongoose.Schema;

/*
	key：字段名
	type：字段数据类型(String,Number,Date,Buffer,Boolean,Mixed,ObjectId,Array)
*/

const name = new Schema({
		key:type,
		key:[{key1:type}],
		key:{type:value1,defaul:value2},
		key:{key1:type,key2:type}
	})

//model公共方法
Schema.methods.fn = function(){}

//设置索引
1.设置在Schema中
new Schema({
	name:{type:String,index:true}
})

2.在Schema实例中设置
const name = new Schema();
name.index({name:1,type:-1});//其中1代表正序，-1代表逆序



//字段的检验 --  使用save时会自动检测
1.required：必填字段
new Schema({
	name:{
		type:String,
		required:[true,"错误提示信息"]
	}
})

2.min,max：对Number类型的数据的限制
new Schema({
	name:{
		type:Number,
		min:num,
		max:num
	}
})

3.match,maxlength,minlength：对字符串的检测
new Schema({
	name:{
		type:String,
		match://,
		maxlength:num,
		minlength:num
	}
})

4.自定义验证：
new Schema({
	name:{
		type:String,
		validate:{
			validator(){return xxx},
			message:
		}
	}
})

```

	

	* 根据Schema创建model

```javascript
//此时创建的model-name并不是数据库中collection的名字，而是他的单数形式，在数据库应该为model-name+'s'
const xxx = mongoose.model('model-name','Schema实例名字')
```
	
	* 使用model操作mongodb数据库
		* 向collection中插入document

```javascript
//key，value为要插入到model即mongodb中对应collection的值，如果collection不存在，会默认创建 ---- 如果手动建collection会导致model无法和collection联系在一起

model.save({key：value}).then(fn);
```
		* 查询
			* find：没有找到返回空数组

```javascript
/*
	参数1：查询的条件
	参数2：只在所写的字段下进行查询,-filed：代表不在该字段下进行查找
	参数3：一些内置方法，例如limit,skip等
	参数4：找到数据后执行的回调
*/
model.find({key:value},'filed1 filed2',{method:value},function(){})

model.find({key:value}).method().exce(function(){})//同上
```
			* findById：根据_id字段找对应的文档
				
```javascript
model.findById(id[,'filed1 filed2'],function(){})

model.findById(id).method().exec();

model.findById().exec();
```

			* findOne：只找一个值，第一个匹配的？没有找到返回null

		* 更新
				* update
	
				* updateMany
	
				* updateOne
	
				* findOneAndUpdate：查找并更新
				
```javascript
/*
	参数1：查找条件
	参数2：更新的内容
	参数3：选项
	参数4：回调
*/
model.findOneAndUpdate(query,update,options,callback);
```

			* findByIdAndUpdate：根据id查找并更新

```javascript
model.findByIdAndUpdate(id,update,options,callback)
```

		* 删除
			* remove/deleteMany：删除所有匹配的文档

```javascript
model.remove({key:value},function(){})
```

			* deleteOne：删除第一个匹配的文档

```
model.deleteOne({key:value},function(){})
```
			
			* findOneAndRemove：查找并删除

```
model.findOneAndRemove({key:value},options,fn);
```

			* findByIdAndRemove：通过id查找并删除	

		* 数量
		
				* count：返回匹配的文档的数量
				model.count({key:value},function(){})

	
		* 字段的自增


* 常用method
	* select
	* distinct
	* slice
	* limit：返回结果的长度
	* skip：跳过
	* sort：根据指定字段排序，1升序，-1降序
>>>>>>> 0d508a3cc92ab72c1ae5fb2cc7910220396c46ba

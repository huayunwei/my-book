multer ：用于接受文件的插件

接受单一文件

```
//自定义上传后文件的名字和路径
var storage = multer.diskStorage({
    destination:function(req,file,cb){
        cb(null,'data/audio');
    },
    filename:function(req,file,cb){
        if(num != null){
            cb(null,num+'.mp3');
        }else{
            sql.count({}).then((data)=>{
                num = data.res;
                cb(null,num+'.mp3');
            })
        }

    }
})



var loader = multer({
    storage:storage
}).single('filename');


// var loader = multer({
//     fileFilter:fileFilter
// });

app.post('/api/save',function(req,res){
    loader(req,res,function(err){
        const file = req.file,
            body = req.body;
        console.log(req.file,req.body);
        if(err){
            res.status(500);
            return res.send({
                status:1,
                msg:err.message,
                res:''
            });
        }
        const songData = {
            "name" : file.originalname,
            "url" : file.destination+'/'+file.filename,
            "during" : body.duration,
            "update" : +new Date(),
            "listenCount" : 0,
            "downCount" : 0,
            "type" : body.type,
            "lrc" : "",
            "id" : num,
        }
        //将songData存到数据库中
        num++;
        return res.send({
            status:0,
            msg:'',
            res:'成功'
        });
    }
)})
```




## 数组方法（自封装）

* ### indexOf

```markdown
if(Array.prototype.indexOf !== 'function'){
    /*
        查找第一个匹配的数组项的下标
        @param:search - 要超找的值
        @param:start - 从此处开始超找
        @return:index - 下标
    */
    Array.prototype.indexOf = function(search,start){
        let index = -1;
        start = start * 1 || 0;//start转为数字，如果转换不了则为0;
        for(let i=start,length = this.length;i<length;i++){
             if(this[i] === search){//是完全相等的比较
                 index = i;
                 break;
             }   
        }
        return index;
    }
}
```

* ### allIndexOf

```markdown
/*
    查找所有匹配的数组项的下标
    @param:search - 要超找的值
    @param:start - 从此处开始查找
    @return:index - 匹配的下标集合
*/
Array.prototype.allIndexOf = function(search,start){
    let index = [];
    start = start * 1 || 0;
    for(let i=start,length = this.length;i<length;i++){
        if(this[i] === search){
            index.push(i);
        }
    }
    return index;
}
```

* ### sum

```markdown
/*
    求和
    @return:sum - 和
*/
Array.prototype.sum = function(){

    let sum = 0;

    //1.for循环

    for(let i=0,length=this.length;i<length;i++){
        sum +=this[i]; 
    }


    //2.reduce
    sum = this.reduce(function(prev,next){
        return prev + next;
    },0);

    return sum;   
}
```

* ### reduce

```
/*
    对数组元素进行组合，生成单个值
    @param：callback - 执行函数
    @param: initialValue - 初始值
    @return: con - 返回值
*/
    if(typeof Array.prototype.reduce !== 'function'){
        
        Array.prototype.reduce = function(callback,initialValue ){
            
        }
    }
*/
```

* ### reduceRight
* ### map
* ### forEach
* ### filter
* ### some
* ### every
* ### noRepeat
* ### inArray
* ### copy




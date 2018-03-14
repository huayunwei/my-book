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

```markdown
/*
    对数组元素进行组合，生成单个值
    @param：callback - 执行函数
    @param: initialValue - 初始值
    @return: con - 返回值
*/
    if(typeof Array.prototype.reduce !== 'function'){

        Array.prototype.reduce = function(callback,initialValue ){
            let prev = initialValue , i = 0 , length = this.length;
            if(typeOf prev === 'undefined'){
                prev = this[i];
                i = i + 1;//注：没有初始值的时候，k是从1开始的
            }
            for(i;i<length;i++){
                //传回reduce中函数的四个参数即返回值，当前值，当前下标，数组
                prev = callback(prev,this.[i],i,this);
            }
            return prev;
        }
    }
```

* ### reduceRight

```markdown
if(typeof Array.prototype.reduceRight !== 'function'){
    Array.prototype.reduceRight = function(callback,initialValue){
        let prev = initialValue , length = this.length , i = length - 1;
        if(typeof prev == 'undefined'){
            prev = this[i];
            i = i - 1;
        }
        for(i;i>-1;i--){
            prev = callback(prev,this[i],i,this);
        }

        return prev;
    }
}
```

* ### map

```markdown
/*
    对数组中每一项执行函数，返回执行后的结果组成的函数
    @param:fn - 执行函数
    @param:context - 上下文环境
    @return:arr - 结果数组
*/

if(typeof Array.prototype.map !== 'function'){
    Array.prototype.map = function(fn,context){
        let arr = [];
        if(typeof fn === 'function'){
            for(let i=0,length = this.length;i<length;i++){
                arr.push(fn.call(context,this[i],i,this));
            }
        } 
    }
}
```

* ### forEach

```markdown
/*    对数组中每一项执行函数
    @param:fn - 执行函数
    @param:context - 上下文环境
*/
if(typeof Array.prototype.forEach !== 'function'){
    Array.prototype.forEach = function(fn,context){
        if(typeof fn === 'function'){
            for(let i=0,length = this.length;i<length;i++){
                fn.call(context,this[i],i,this);
            }
        }
    }
}
```

* ### filter

```markdown
/*
    过滤
    @param:fn - 执行函数
    @param:context - 上下文
    @return:arr - 过滤后的数组
*/
if(typeof Array.prototype.filter !== 'function'){
    Array.prototype.filter = function(fn,context){
        let arr = [];
        if(typeof fn === 'function'){
            for(let i=0,length = this.length;i<length;i++){
                if(fn.call(context,this[i],i,this)){
                    arr.push(this[i])
                }
            }
        }
        return arr;
    }
}
```

* ### some

```markdown
/*
    只要有一个符合，就返回true
    @param：fn - 执行函数
    @param：context - 上下文
    @return: flag - 布尔值，是否有符合的项
*/
if(typeof Array.prototype.some !== 'function'){
    Array.prototype.some = function(fn,context){
        let flag = false;
        if(typeof fn === 'function'){
            for(let i=0,length = this.length;i<length;i++){
                if(fn.call(context,this[i],i,this)){
                    flag = true;
                    break;
                }
            }
        }
        return flag;
    }
}
```

* ### every
* ### noRepeat
* ### inArray
* ### copy




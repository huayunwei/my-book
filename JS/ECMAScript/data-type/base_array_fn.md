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

```
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
* ### reduce
* ### reduceRight
* ### map
* ### forEach
* ### filter
* ### some
* ### every
* ### noRepeat
* ### inArray
* ### copy




## 数组方法（自封装）

* ### indexOf

```markdown
if(Array.prototype.indexOf !== 'function'){
    /*
        返回查找到的第一个位置的下标
        @param:search - 要超找的值
        @param:start - 开始查找的位置
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




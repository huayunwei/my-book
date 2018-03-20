## 元素节点

* ### 属性

  * childNodes：获取元素的全部子节点

  ```
  function getElNode(el){
      const child = el.childNodes;
      let result = [];
      for(let i=0,length=child.length;i<length;i++){
          if(child[i].nodeType==1){
              result.push(child[i]);
          }
      }
      return result;
  }
  ```

  * 




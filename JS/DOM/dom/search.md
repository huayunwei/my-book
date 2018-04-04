## 节点查询型API

* document.getElementById：根据元素id返回元素，返回Element类型，不存在，返回null
  * 元素id大小写敏感
  * 如果html中存在多个相同id的元素，则返回第一个元素
  * 只能搜索已在文档中的元素
* document.getElementByTagName：根据元素标签名获取元素，返回一个HTML Collection类型
  * 如果没有指定的标签，则返回空HTML Collection
  * 可以使用\*表示所有的标签




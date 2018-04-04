## 关系API

* 父：
  * parentNode：元素的父节点，可以是任意类型的
  * parentElement：元素的父节点，返回的必须是一个Element类型
* 兄：
  * previousSibling：节点的前一个节点（可以是任意类型的），返回节点是任意类型的，如果该节点是第一个节点，返回null
  * nextSibling：节点的后一个节点（可以是任意类型的），如果该节点是最后一个节点，为null
  * nextElementSibling：返回后一个元素节点，必是元素类型的节点才会返回
* 子：
  * childNodes：返回NodeList，表示元素的子节点列表，子节点可以是文本或注释节点等
  * children：元素类型的子节点
  * firstNode：第一个子节点，类型任意
  * lastNode：最后一个子节点，类型任意
  * hasChildNodes：判断是否包含子节点




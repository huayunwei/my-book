## 修改型API

* appendChild：将指定节点添加到调用该方法的节点的子元素的末尾
  * 如果添加的节点是页面存在的节点，则执行后这个节点会添加到指定位置，原位置的节点删除
  * 如果添加的节点是新节点，则直接添加到文档末尾
  * 如果添加的节点绑定了事件，被移动时，事件仍然绑定

```
parent.appendChild(child);
```

* insertBefore：添加一个节点到一个参照节点之前
  * refNode是必传的，如果不传该参数会报错
  * 如果refNode是undefined或null，则insertBefore会将节点添加到子元素的末尾

```
//newNode:要添加的节点，会添加在refNode之前
//refNode：参照节点
parent.insertBefore(newNode,refNode);
```




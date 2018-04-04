## 节点创建型api

* createElement：指定标签名创建一个元素，传入的标签名未知，则创建一个自定义标签，IE8以下不支持自定义标签

```
document.createElement('div');
```

* creatTextNode：创建一个文本节点

```
document.createTextNode('xxx');
```

* cloneNode：返回调用方法的节点的副本
  * 如果是通过addEventListener或onclick进行绑定，则副本节点不会绑定
  * 如果是内联方式绑定，则副本节点也会被触发

```
document.cloneNode(true);//复制子节点
document.cloneNode(false);//不复制子节点
```

* createDocumentFragment：创建一个DocumentFragment，文档片段，用于临时存储节点




## DOM

* 定义：js操作网页的接口，全称为文档对象模型
* 最小组成单位：节点（node）
* 节点类型：
  * 元素节点 - Node.ELEMENT\_NODE
    * nodeType：1
    * nodeValue：null
  * 属性节点 - Node.ATTRIBUTE\_NODE
    * nodeType：2
  * 文本节点 - Node.TEXT\_NODE
    * nodeType：3
    * nodeName：\#text
  * CDATA节点 - Node.CDATA\__SECTION\_NODE_
    * nodeType：4
    * nodeName：\#cdata-section
  * 实体引用名称节点 - Node.ENTRY\__REFERENCE\_NODE_
    * nodeType：5
    * nodeName：null
  * 实体名称节点 - Node.ENTITY\_NODE
    * nodeType：6
    * nodeName：null
  * 处理指令节点 - Node.PROCESSING\__INSTRUCTION\_NODE_
    * nodeType：7
    * nodeName：target
  * 注释节点 - Node.COMMENT\_NODE
    * nodeType：8
    * nodeName：\#comment
  * 文档节点 - Node.DOCUMENT\_NODE
    * nodeType：9
    * nodeName：\#document
    * nodeValue：null
  * 文档类型节点 - Node.DOCUMENT\__TYPE\__NODE
    * nodeType：10
    * nodeName：doctype
    * nodeValue：null
  * 文档片段节点 - Node.DOCUMENT\__FRAGMENT_\_NODE
    * nodeType：11
    * nodeName：\#document-fragment
    * nodeValue：null
  * DTD声明节点 - Node.NOTATION\_NODE
    * nodeType：12
    * nodeValue：null
* 节点属性
  * nodeType：节点类型
  * nodeName：节点名称，大写字符，例如：DIV
  * nodeValue：节点值，返回字符串，没有返回null




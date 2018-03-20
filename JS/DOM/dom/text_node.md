## 文本节点

* ### 属性

  * data：和nodeValue属性值相同，返回文本节点的文本值

  * wholeText：将当前文本节点和紧邻的文本节点作为一个整体返回

  * length：文本节点字符的数目
* 方法

  * document.createTextNode\( 文本节点 \)：创建一个文本节点

  * el.normalize\(  \)：合并相邻的文本节点

  * el.splitText\( num \)：拆分两个文本节点，num为要分割的位置

  * el.appendData\( text \)：将text添加到节点末尾

  * el.deleteData\( offset,count \)：从offset指定的位置开始删除count个字符

  * el.insertData\( offset,text \)：在offset指定的位置插入text

  * el.replaceData\( offset,count,text \)：用text替换从offset指定位置开始到offset+count为止的文本

  * el.substringData\( offset,count \)：提取从offset指定的位置开始到offset+count为止的字符串并返回




## WWW（**World Wide Web**）

* ### Tim Berners-Lee发明了WWW，并且发明了第一个服务器，第一个浏览器和第一个网页
* ### 第一个网页地址：[info.cern.ch](http://info.cern.ch/)
* ### URI（Uniform Resource Identifier）：统一资源标识符，俗称网址

  ![](/assets/URI.png)

  * URL\(Uniform Resource Locator\)：统一资源定位符，可以确定唯一的地址（网址）

    * 标准格式：scheme:\[//host\[:port\]\]\[/path\]\[?query\]\[\#fragment\]

    * 完整格式：scheme:\[//\[user\[:password\]@\]host\[:port\]\]\[/path\]\[?query\]\[\#fragment\]

      ![](/assets/URL.png)

      * 协议：scheme

      * 凭证：user：password

      * 域名：host

        * 最后的为顶级域名，例如上图中的.com

        * 然后依次往后为一级域名，二级域名。。。

      * 端口号：port

        * 1--1023系统保留，1024--4999由客户端程序自由分配，5000--65535由服务器端程序自由分配在UDP协议中

        * 21：ftp

        * 22：ssh

        * 443：https

        * 1080：socks网络应用程序代理服务

        * 3306：mysql

        * 80：http

      * 路径：path

      * 查询参数：query

      * 锚点：fragment

  * URN\(Uniform Resource Name\)：统一资源名称，可以确定唯一的资源

* ### DNS（Domain Name System）：域名系统

  * 作用：输入域名，输出域名对应的ip地址
* ### HTTP（HyperText Transfer Protocol）：两个电脑之间传输内容的协议
* ### HTML（HyperText Markup Language）：超级文本

* ### TCP/IP

  * 网络是在TCP/IP协议族的基础上运作的，HTTP是它的一个子集

  * 分层：

    * 应用层 - 向用户提供应用服务时通信的活动，包括HTTP，DNS等协议

    * 传输层 - 对上层应用层提供处于网络连接中的两台计算机之间的数据传输，包括TCP和UDP协议

    * 网络层 - 处理在网络上流动的数据包\(数据包：网络传输最小的数据单位\)

      * 规定通过怎样的路径到达对方计算机，并把数据包传送给对方

    * 数据链路层\(网络接口层\) - 处理连接网络的硬件部分

      * 包括操作系统，硬件的设备驱动，网络适配器，光纤等

    * 利用TCP/IP协议进行网络通信的流程

      * 客户端在应用层发出一个HTTP请求

      * 传输层（TCP协议）将应用层收到的数据（HTTP请求报文）进行分割，并在各个报文上打上标记序号和端口号后转给网络层

      * 网络层\(IP协议\)，增加通信目的地的MAC地址后转发给链路层

      * 服务器在链路层接受到数据，按序往上层发送，一直到应用层，每经过一层会吧对应的首部消去

* ### IP协议

  * 处于网络层

  * 作用：把各种数据包传送给对方，需要IP和MAC地址

* ### TCP协议

  * 处于传输层

  * 作用：提供可靠的字节流服务 

    * 字节流服务 -  将大块数据分割成以报文段为单位的数据包进行管理

    * 可靠 - 将数据准确可靠的传给对方\(即可以确认是否送达\)

  * 实现方式：链接时 - 三次握手，断开时 - 四次握手

* ### DNS协议

  * 处于应用层

  * 作用：提供域名到ip之间的解析服务 - 可以正向从域名到IP，也可以逆向从ip反查域名




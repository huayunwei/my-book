### 状态码

* 当客户端向服务器端发送请求时，描述返回的请求结果

### 状态码类别

[https://zh.wikipedia.org/wiki/HTTP状态码](https://zh.wikipedia.org/wiki/HTTP状态码#3xx重定向)

* 1XX：信息性状态码，接受的请求正在处理

* 2XX：成功状态码，请求正常处理完毕

  * 200 OK - 表示从客户端发来的请求在服务器端被正常处理

  * 204 No Content - 服务器接收的请求已成功处理，但在返回的响应报文中不含实体的主体部分

  * 206 Partial Content - 服务端进行了范围请求，响应报文包含由Content-Range指定范围的实体内容

  * ### 获取部分内容的范围请求 - 会返回状态码206的响应报文

    * 在请求报文中包括

      * Range：指定资源的btye范围

    * 在响应报文中包括

      * content-Range
      * content-Length
      * content-Type：multipart/byteranges

    * 如果服务器端无法响应范围请求，则返回状态码200 OK和完整的实体内容

* 3XX：重定向状态码，需要进行附加操作以完成请求

  * 301 Moved Permanently - 永久性重定向

    ```
      请求的资源已被分配了新URI，以后应该使用新URI，会改变保存的书签
    ```

  * 302 Found - 临时重定向，本次使用新的URI访问

  * 302 See Other - 同302，但是303客户端应当采用GET方法

  * 304 Not Modified - 没有修改，直接使用缓存中的内容

* 4XX：客户端错误状态码，服务器无法处理请求

  * 400 Bad Request - 请求报文中存在语法错误

  * 401 Unauthorized - 发送的请求需要有HTTP认证的认证信息，初次接受401响应，会弹出认证用的对话窗口

  * 403 Forbidden - 请求资源的访问被服务器拒绝了

  * 404 Not Found - 服务器上无法找到请求的资源或服务器拒绝请求

* 5XX：服务器错误状态码，服务器处理请求出错

  * 500 Internal Server Error - 服务器端在执行请求时发成了错误，web应用存在BUG或某些临时故障

  * 503 Service Unavailable - 服务器暂时处于超负载或正在进行停机维护，无法处理请求




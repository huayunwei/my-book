### HTTP - 不保存状态的协议，无状态协议
	* 自身对请求和响应之间的通信状态不进行保存，即无法记录之前的请求和响应报文的信息

### HTTP 方法
	* GET：获取资源
	* POST：传输实体的主体
	* PUT：用来传输文件，要求在请求报文的主体中包含文件内容，然后保存到请求URI指定的位置
	* HEAD：同GET只是不返回报文主体部分，用于确认URI的有效性及资源更新的日期
	* DELETE：用来删除文件，按请求URI删除指定的资源
	* OPTIONS：查询针对请求URI指定的资源支持的方法，即返回上面的的几种方法支持哪种(HTTP1.1)
	* TRACE：查询发送出去的请求经过的路径(HTTP1.1)
	* CONNECT：实现用隧道协议进行TCP通信(HTTP1.1)

### 持久链接 -- HTTP/1.1所有的链接默认为持久链接
	* HTTP初始版本，每次HTTP后都会断开TCP
	* 持久链接：只要任意一端没有明确提出断开链接，就保持TCP链接状态

### 发送多种数据 -- 首部字段中有Content-type

### 获取部分内容的范围请求 - 会返回状态码206的响应报文
	* 在请求报文中包括

		* Range：指定资源的btye范围
	* 在响应报文中包括
		* content-Range
		* content-Length
		* content-Type：multipart/byteranges

	* 如果服务器端无法响应范围请求，则返回状态码200 OK和完整的实体内容

### 内容协商
	* 客户端和服务器端就响应的资源内容进行交涉，提供给客户端最合适的资源
	* 在请求报文中的某些首部字段作为判断条件
		* Accept
		* Accept-Charset
		* Accept-Encoding
		* Accept-Language
		* Content-Language
	* 类型
		* 服务器驱动协商 - 根据请求的首部字段为参考，在服务器端自动处理
		* 客户端驱动协商 - 利用JS
		* 透明协商 -  由服务器端和客户端各自进行内容协商



### HTTP报文 -- 用于HTTP协议交互的信息
	* 报文结构：报文首部和报文主体
	* 报文首部：
		* 状态/请求行：
			
			```
			请求行：用于请求的方法，请求URI和HTTP版本，例：GET/HTTP/1.1
			状态行：表明响应结果的状态码，原因短语和HTTP版本，例：HTTP/1.1 200 OK
			```
		* 报文首部字段
		* 其他 - 可能包含HTTP的RFC里未定义的首部，例如Cookie

	* 报文主体 -- 用户和资源的信息


### 报文的编码
	* 内容编码：在实体内容上的编码格式，并保持实体信息原样压缩
		* gzip
		* compress
		* deflate
		* identity(不进行编码)
	* 分块传输编码：
		* HTTP通信中，如果实体资源没有全部传输完成，浏览器是无法显示请求的页面的
		* 将传输的大容量数据分割成多块，能够让浏览器逐步显示页面


### 报文首部字段 -- 用于给浏览器和服务器提供报文主体大小、所使用的语言、认证信息等内容
	* 键值对的形式 -- key：value1，value2
	* 类型
		* 通用首部 - 请求报文和响应报文都会使用的首部
			* Cache-Control：操作缓存
				* 请求指令的值
					* no-cache：不接受缓存过的资源
					* no-store：不缓存请求或响应的任何内容
					* max-age=[秒]：如果缓存服务器的资源缓存时间小于max-age，则接受该缓存，否则将请求转发给服务器
					* max-stale(=[秒])：接收已过期的响应，如果没有指定值，则无论过期多久都可以接受，如果指定值，则过期时间在指定值内可以接受
					* min-fresh=[秒]：如果缓存服务器的资源没有超过该事件，则可以接受，否则无法接受
					* no-transform：代理不可更改媒体类型
					* only-if-cached：从缓存获取资源，如果缓存服务器有该资源，不向服务器请求，则接受，如果无，则返回504
					* cache-extension：新指令标记(token)
				* 响应指定的值
					* public：可向任意方提供响应的缓存
					* private：仅向特定用户返回响应
					* no-cache：缓存服务器不能对资源进行缓存
					* no-store：同上
					* no-transform：同上
					* must-revalidate：可缓存但必须再向源服务器进行确认，
					* proxy-revalidate：要求中间缓存服务器对缓存的响应有效性再进行确认
					* max-age=[秒]：资源保存为缓存的最长时间，比Expires优先级高
					* s-maxage=[秒]：公共缓存服务器响应的最大时间，忽略Expires和max-age指令的处理
			* Connection：控制不再转发给代理，管理持久链接
			 	* Close：明确提出要关闭链接
			 	* Keep-Alive：1.0的时候需要手动指定持久链接
			* Date：创建HTTP报文的日期和时间
			* Pragma：1.1之前版本使用
			* Trailer：声明在报文主体后记录了哪些首部字段
			* Transfer-Encoding：传输报文主体时采用的编码方式，仅对分块传输编码有效
			* Via：在经过代理和网关时，会在首部字段Via中附加该服务器的信息，可以用于追踪浏览器和服务器之间的传输路径
			* Warning：用于告知用于与缓存相关的问题的警告

		* 请求首部 -- 从客户端向服务器端发送请求报文时使用的
			* Accept：客户端能处理的媒体类型及媒体类型的相对优先级
				* 文本文件：text/html,text/plain,text/css...
				* 图片文件：image/jpeg,image/gif,image/png...
				* 视频文件：video/mpeg,video/quicktime..
				* 应用程序使用的二进制文件：application/octet-stream,application/zip...
				* 权重：q= 权重值;(值为0-1之间，1位最大，默认为1)
			* Accept-Charset：客户端支持的字符集
			* Accept-Encoding：支持的内容编码
			* Accept-Language：客户端能够使用的语言集(中文zh-cn或英文en等)
			* Authorization：告知服务器，客户端的认证信息
			* From：告知服务器用户的电子邮箱地址
			* Host：告知服务器，请求的资源所处的互联网主机名和端口号（必写）
			* If-Modified-Since：如果资源更新时间早于该时间，则返回304，否则返回新资源
			* If-Range：值和ETag值相同则作为范围请求处理，否则返回全体资源
			* Range：获取部分资源的范围请求，返回206，无法处理该范围返回200和全部资源
			* Referrer：告知服务器请求的原始资源的URI
			* TE：传输编码，例如分块传输TE:trailers
			* User-Agent：创建请求的浏览器和用户代理名称等信息
		* 响应首部
			* Age：告知客户端，服务器在多久前创建了响应，如果是缓存服务器，则指缓存后的响应再次发起认证到认证完成的时间值
			* ETag：客户端实体标志，将资源以字符串形式做唯一性标识的方式，当资源更新时ETag也需要更新
			* Location：将响应接收方引导至某个于请求URI位置不同的资源
			* Retry-After：客户端应该在多久后再次发送请求
			* Server：告知客户端当前服务器上安装的HTTP服务器应用程序的信息
		* 实体首部
			* Allow：通知客户端能够支持的所有HTTP方法，如GET等，如不支持则返回405
			* Content-Encoding：告知客户端服务器对实体的主体部分使用的编码方式
			* Content-Language：告知客户端实体的主体的自然语言
			* Content-Length：实体主体部分的大小
			* Content-MD5：用于检查报文主体在传输过程中是否保持完整
			* Content-Range：针对范围请求，告知客户端作为响应返回的实体的哪个部分范围
			* Content-Type：实体主体内对象的媒体类型
			* Expires：将资源失效的日期告知客户端
			* Last-Modified：资源最终修改的时间

		* Cookie
			* Set-Cookie：开始状态管理所使用的Cookie信息
				* NAME=VALUE：赋予Cookie的名称和其值
				* expires=DATE：Cookie的有效值(若不明确指定则默认为浏览器关闭前为止)
				* path=PATH：将服务器上的文件目录作为Cookie的适用对象
				* domain=域名：作为Cookie适用对象的域名
				* Secure：仅在HTTPD安全通信时才会发送Cookie
				* HttpOnly：加以限制，使Cookie不能被JS脚本访问
			* Cookie：服务器接收到的Cookie信息

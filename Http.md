一：含义

1. HTTP(HyperText Transfer Protocol)

http是超文本传输协议，超文本传输协议（HTTP，HyperText Transfer Protocol)是互联网上应用最为广泛的一种网络协议。所有的WWW文件都必须遵守这个标准。设计HTTP最初的目的是为了提供一种发布和接收HTML页面的方法。它教客户端如何请求、服务器如何响应。

二：常见状态码 

HTTP响应码由三位十进制数字组成，它们出现在由HTTP服务器发送的响应的第一行。

是服务器对浏览器说的话：

200 通常的成功 OK

GET：请求的对应资源会作为响应返回。响应将包含描述或操作的结果。

POST：返回处理对应请求的结果。

204 成功处理请求，没有返回任何内容 No Content

表示服务器接收到的请求已经处理完毕，但是服务器不需要返回响应。比如，客户端是浏览器的话，那么浏览器显示的页面不会发生更新。

206 Partial Content

成功处理了部分GET请求

301 Moved Permanently

请求的网页已永久移动到新位置，永久性重定向

302 Found

网站临时性重定向，暂时不能访问（备案、被查）

303 See Other

该状态码表示由于请求对应的资源存在另一个URI，并指定必须使用GET方法定向获取请求的资源。和302不同的是，302是不会改变上次的请求方法

304 Not Modified

访问不了，并返回和上次一样的话,表示资源未被修改过，还是和上次访问时一样。

307 Temporary Redirect

临时重定向，和302、303类似，不同的是，不会指定客户端要用什么样的方法请求，

400 Bad Request

表示客户端中存在语法错误，导致服务器无法理解该请求。客户端需要修改请求的内容后再次发送请求。

401 Unauthorized

即用户没有必要的凭据。该状态码表示当前请求需要用户验证。

403 Forbidden

服务器已经理解请求，但是拒绝执行它。

404 Not Found

服务器找不到请求的网页。

500 Internal Server Error

服务器遇到错误，无法完成请求。

503 Service Unavailable

由于临时的服务器维护或者过载，服务器当前无法处理请求。这个状况是暂时的.

三：请求的方式和格式

 请求的格式（背下来）

1.GET请求

GET / HTTP/1.1

Host: baidu.com

Accept: text/html

2.POST请求

POST /login HTTP/1.1

Host: baidu.com

Accept: application/json

Content-Type: application/x-www-form-urlencoded

Content-Length: …

username=fang&password=666

四：响应的方式和格式

4.响应的格式

GET的响应

HTTP/1.1 200 OK

Content-Length: …

Content-Type: text/html或application/x-JavaScript; charset=utf-8

POST

若密码错了

HTTP/1.1 401 Unauthorized（若成功了就是200 OK）

Content-Type: application/json

Content-Length: …

{‘’error”}

 五：响应头信息

* Location : 服务端用来告诉浏览器,请求需要重定向.(必须结合状态吗302使用)

Server : 服务端用来告诉浏览器,服务器的类型

* Content-Encoding: 服务端用来告诉浏览器,服务器对数据采用的编码（主要是指压缩的格式）

Content-Length:  服务端用来告诉浏览器,响应正文的长度

Content-Language: 服务端用来告诉浏览器,zh-cn服务发送的文本的语言

*Content-Type: 服务端用来告诉浏览器,你要用哪个码表来解析二进制数据

* Last-Modified : 服务端用来告诉浏览器,访问资源的最后修改时间

 *Refresh：服务端用来告诉浏览器,多长时间刷新一次

*Content-Disposition: 服务端用来告诉浏览器,以下载文件的方式打开文件

 * Expires: -1 : 服务端用来告诉浏览器,不要缓存 Cache-Control:no-cache (1.1)   Pragma: no-cache   (1.0)

 ***** Set-Cookie: 服务端用来告诉浏览器,要存储的内容

六：如何查看响应和请求

1：打开Network

2：刷新网址

3：选中第一个响应 

4：查看Headers里的Response Headers点view source可以看到响应的前两部分，Request Headers点view source可以看到请求

5:查看Response你可以看到响应的第四部分

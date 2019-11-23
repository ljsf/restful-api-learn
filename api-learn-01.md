
参考链接：https://kite.com/blog/python/flask-restful-api-tutorial/
目录表：
 1.what is ajn API？
 
 2.what is REST？
  client： a client can refer to either a devleloper or software application which uses the API
  resource：A resource describes an object , data or peive of information that you may need to store or send other services
 
3.what is HTTP and Requests?
 

REST特点：
 1.客户端--服务器
  客户端和服务器之家必须要有明确的界限
 2.无状态
  客户端发出的请求中必须要包含所有必要的信息，服务器不能再两次请求之间保存客户端的任何状态
 3.缓存
  服务器发出的响应可以标记为可缓存或者不可缓存，这样出于优化目的，客户端（或者客户端和服务器之间的中间服务） 可以使用缓存
 4.统一接口
  客户端访问服务器资源时使用的协议必须一致，定义良好，且已经标准化，REST Web服务最常使用的统一接口是HTTP协议
 5.系统分层
  在客户端和服务器之间可以按需插入代理服务器，缓存或网关，以提高性能，稳定性和伸缩性
 6.按需代码
  客户端可以选择从服务器上下载代码，在客户端的环境中执行

资源就是一切
 资源时REST架构方式的核心概念，在REST架构中，资源时程序中你要着关注的事物，例如，在博客程序中，用户，博客和评论但是资源
 每个资源都要使用唯一的URL表示，还是以博客程序为例，一篇博客文章可以使用URL/api/posts/12345 表示，其中12345是这篇文章的唯一标识，
 使用文章在数据中的主键表示，URL的格式内容无关紧要，只要资源的URL只表示唯一的一个资源即可
 
 某一类资源的集合也要有一个URL，博客文章集合的URL可以是/api/post/ , 评论集合的URL可以是/api/comments/
 
 API还可以为某一类资源的逻辑子集定义集合URL，例如，编号为12345的博客文章，其中的所有评论可以使用URL /api/posts/12345/comments/ 表示，
 表示资源集合的URL习惯在末端加入一个斜线，代表一种文件夹 结构
 
 注； Flask会特殊对待末端带有斜线的路由，如果客户端请求的URL的末端没有斜线，而唯一匹配的路由末端有斜线，Flask会自动响应一个重定向，转向末端带斜线的URL，反之则不会重定向
 
请求方法：
  客户端程序在建立起的资源URL上发送请求，使用请求方法表示期望的操作，若要从博客API中获取现有博客文章的列表，客户端可以向http://www.exam-ple.com/poosts/ 发送GET请求，若要插入一篇新博客文章，客户端可以向同一地址发送POST请求，而且请求主体中哟啊包含文章的内容，若要获取编号12345的博客文章，客户端可以向http://www.example.com/api/posts/12345发送GET请求，

# Web服务器

## Web server, HTTP server

假设我们要打开本地Web服务器一个页面 index.html，那么我们在浏览器输入URL: [http://192.168.1.5/index.html](http://192.168.1.1/index.html), 之后我们会在浏览器看到页面内容。

其中，浏览器作为客户端。当我们输入URL并敲下回车，客户端会向Web服务器发送一个HTTP请求，Web服务器接收到该请求后，会发送一个HTTP响应给该客户端，这个响应包含了index.html的内容，由浏览器解释这个内容并呈现给我们。

![](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LhVVVI7iIuTsQN7G1oY%2F-LhVVYu-YEPEa4TkawNG%2F-LhVVhptvBeAJnh6IQzc%2Fimport.png?generation=1560692318751106&alt=media)

## Web服务器定义

- 服务器:

	指的是 [服务器软件](https://en.wikipedia.org/wiki/Server_software), 或者是专门用于运行所述软件的硬件。一般我们按照 "服务器软件" 来理解。

- Web服务器:

	简单来说，它**总是**地等待客户端发送请求。当收到请求之后，它会生成相应的响应，然后其返回至客户端。响应一般包含一个HTML文件，有时也可以包含纯文字档案、图像或其他类型的文件。

	Web服务器通过HTTP协议与客户端通信，因此也被称为HTTP服务器。

## Web服务器的工作原理

一般分为四步：

建立连接，请求，响应 和关闭连接。

 1. 建立连接
客户端通过TCP/IP协议主动建立到服务器的TCP连接，过程可以称为TCP的**三次握手**。

2. 请求
客户端向服务器发送HTTP协议请求包，请求服务器里的资源

3. 响应
服务器向客户端发送HTTP协议响应包，如果请求的资源包含有动态语言的内容 (例如http请求包含一个php文件，`http://test.com/login.php?name=david&passwd=123`)，那么服务器会调用动态语言的解释引擎负责处理“动态内容”，并将处理得到的数据返回给客户端。由客户端（这里指浏览器）解释HTML文档，在客户端屏幕上渲染图形结果。

4. 关闭连接
客户机器主动与服务器断开，也就是TCP的**四次挥手**。

## 实例

![](https://gblobscdn.gitbook.com/assets%2F-LhVVVI7iIuTsQN7G1oY%2F-LhVVYu-YEPEa4TkawNG%2F-LhVVhpwjbzUPIMGVw6r%2Fimport2.png?generation=1560692318657646&alt=media)

在F12 开发者工具可以找到:
- 客户端请求的URL
- 请求的方法
- Web服务器返回给客户端的状态码 。

![](https://gblobscdn.gitbook.com/assets%2F-LhVVVI7iIuTsQN7G1oY%2F-LhVVYu-YEPEa4TkawNG%2F-LhVVhpyqXId_fabX2ff%2Fimport3.png?generation=1560692318639375&alt=media)


在客户端的请求标头中包含了以下信息，其中Host是被请求的服务器的 IP **:** 端口号 。

(端口号默认为80，在图中被隐藏)

![](https://gblobscdn.gitbook.com/assets%2F-LhVVVI7iIuTsQN7G1oY%2F-LhVVYu-YEPEa4TkawNG%2F-LhVVhq-lHc7QOoELr68%2Fimport4.png?generation=1560692318613204&alt=media)

在服务器的响应标头中，可以看到服务器返回了一个text/html类型的文件给客户端

![](https://gblobscdn.gitbook.com/assets%2F-LhVVVI7iIuTsQN7G1oY%2F-LhVVYu-YEPEa4TkawNG%2F-LhVVhq1nr17HgwJpdkY%2Fimport5.png?generation=1560692318622983&alt=media)

这个text/html文件的内容如下:

![](https://gblobscdn.gitbook.com/assets%2F-LhVVVI7iIuTsQN7G1oY%2F-LhVVYu-YEPEa4TkawNG%2F-LhVVhq3RE4fSA2ELUWd%2Fimport6.png?generation=1560692318618868&alt=media)

当客户端接收到这个文件后，经过解释和渲染，就得到之前实例图展示的效果。

关于请求标头和响应标头的更多内容，可以参考[这里](http://tools.jb51.net/table/http_header)。

## 总结

虽然说web服务器的主要工作是根据request返回response，但是实际中的 Web 服务器远远比上面示例的复杂的多，因为要考虑的因素实在是太多了，比如：

-   缓存机制：讲一些经常被访问的页面缓存起来，提高响应速度；
    
-   安全：防止黑客的各种攻击，比如 SYN Flood 攻击；
    
-   并发处理：如何响应不同客户端同时发起的请求；
    
-   日志：记录访问日至，方便做一些分析。
    
目前在UNIX和LINUX平台下使用最广泛的免费 Web 服务器有Apache和 Nginx 。
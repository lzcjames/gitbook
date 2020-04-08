# Web服务

# web services

它是一种跨编程语言和跨操作系统平台的远程调用技术。Web服务依赖于一组广泛使用的Internet协议（XML，HTTP）进行通信。此通信基于XML消息格式进行的请求和响应。

- **跨编程语言**，就是说服务端程序采用java编写，客户端程序则可以采用其他编程语言编写，反之亦然。

- **跨操作系统平台**，则是指服务端程序和客户端程序可以在不同的操作系统上运行。

- **远程调用**，就是一台设备的应用可以调用其他设备上的应用。

例如：支付宝，支付宝并没有银行卡等数据，它只是去调用银行提供的接口来获得数据。还有天气预报等，也是气象局把自己的系统服务以webservice服务的形式暴露出来（比如以API形式），让第三方网站和程序可以调用这些服务功能。

## web服务三要素

### 1. SOAP

Simple Object Access Protocol, 简单对象访问协议。

以XML格式封装消息，由网络传输协议 (HTTP, HTTPS, SMTP etc) 进行通信的协议。

### 2. WSDL

WebServices Description Language, Web服务描述语言。

一个XML格式文档，用以描述服务端口访问方式和使用协议的细节。

### 3. UDDI

Universal Description Discovery and Integration, 统一描述、发现和集成。

用来管理、分发、查询web服务。

## 使用web服务的方式

使用web服务方式的三种最普遍的手段是：
- [远程过程调用](https://zh.wikipedia.org/wiki/%E8%BF%9C%E7%A8%8B%E8%BF%87%E7%A8%8B%E8%B0%83%E7%94%A8)（RPC）
- [服务导向架构](https://zh.wikipedia.org/wiki/%E6%9C%8D%E5%8B%99%E5%B0%8E%E5%90%91%E6%9E%B6%E6%A7%8B)（SOA）
- 表述性状态转移（[REST](https://zh.wikipedia.org/wiki/REST)）。

‌
### 1. RPC

web服务提供一个分布式函数或方法接口供用户调用，这是一种比较传统的方式。但是现在过时了。

### 2. SOA

​[service-oriented architecture](https://en.wikipedia.org/wiki/Service-oriented_architecture), 面向服务的体系结构。SOA是一种分布式运算的软件设计方法。.软件的部分**组件**(调用者)，可以透过网络上的**通信协议**调用另一个应用软件**组件**，让调用者获得**服务**。

### 3. REST

​[Representational State Transfer](https://en.wikipedia.org/wiki/Representational_state_transfer), 表示层状态转换。它是一种架构的风格，其将 web 服务视为资源，可以由其 URL 作为唯一标识。

REST 的基本设计原则对典型 CRUD (增查改删)操作使用 HTTP 协议方法：

-   POST - 创建资源
    
-   GET - 检索资源
    
-   PUT – 更新资源
    
-   DELETE - 删除资源
    
REST 服务的主要优势在于：

-   它们是跨平台 (Java、.net、PHP 等）高度可重用的，因为它们都依赖基本 HTTP 协议。
    
-   它们使用基本的 XML，而不是复杂的 SOAP的XML，使用非常方便。
  
## 相关链接

​[WebService深入浅出](https://blog.csdn.net/qq_35712358/article/details/71244342)​

​[WebService技术详解 (一)](https://blog.csdn.net/c99463904/article/details/76018436) ​

​[极致精简的webservice例子](https://www.cnblogs.com/fengwenzhee/p/6915606.html)
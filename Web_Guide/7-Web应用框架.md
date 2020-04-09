# Web应用框架

## Web application framework

​[Web应用框架](https://en.wikipedia.org/wiki/Web_framework)目的是减轻服务器的工作负荷和减少一般代码的重复性，使代码易于维护和精确编写。比如连接数据库，只要调用web框架的一个接口（或一个函数）再处理就ok了，便免去了自己写这种代码的麻烦。总之使用web框架对开发人员来说，是省时省力的。 一般**框架结构模式**常见的类型为**MVC**

## MVC 结构模式

​[Model–view–controller](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller), 分为三个基本部分：模型（Model）、视图（View）和控制器（Controller）。

![](https://gblobscdn.gitbook.com/assets%2F-LhVVVI7iIuTsQN7G1oY%2F-LhVVYu-YEPEa4TkawNG%2F-LhVViDpSNOy1scGRuyd%2F122.PNG?generation=1560692320107513&alt=media)

### Model

处理应用程序**数据业务逻辑**的部分。通常负责在数据库中存取数据

### View

处理**数据显示**的部分。通常是依据Model的数据创建的

### Controller

处理**用户交互**的部分。通常负责从View读取数据，控制用户输入，并向Model发送数据

MVC 分层简化了分组开发。不同的开发人员可同时开发视图、控制器逻辑和业务逻辑。
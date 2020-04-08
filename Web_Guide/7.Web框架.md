# Web框架

## Web (application) framework

​[web框架](https://en.wikipedia.org/wiki/Web_framework)目的是减轻服务器的工作负荷和减少一般代码的重复性，使代码易于维护和精确编写。比如连接数据库，只要调用web框架的一个接口（或一个函数）再处理就ok了，便免去了自己写这种代码的麻烦。总之使用web框架对开发人员来说，是省时省力的。 一般框架常见的类型为**MVC**和**CMS**。

## MVC

​[Model–view–controller](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller), 分为三个基本部分：模型（Model）、视图（View）和控制器（Controller）。

![](https://gblobscdn.gitbook.com/assets%2F-LhVVVI7iIuTsQN7G1oY%2F-LhVVYu-YEPEa4TkawNG%2F-LhVViDpSNOy1scGRuyd%2F122.PNG?generation=1560692320107513&alt=media)

### Model

处理应用程序**数据业务逻辑**的部分。通常负责在数据库中存取数据

### View

处理**数据显示**的部分。通常是依据Model的数据创建的

### Controller

处理**用户交互**的部分。通常负责从View读取数据，控制用户输入，并向Model发送数据

MVC 分层简化了分组开发。不同的开发人员可同时开发视图、控制器逻辑和业务逻辑。

## CMS

​[Content Management System](https://en.wikipedia.org/wiki/Content_management_system), 内容管理系统， 总体是用于创建和修改数字内容，根据不同需求可精确CMS的开发，如学校账户管理系统，医院管理系统，公司内部与对外管理系统和个人博客管理系统等。

比较流行开源的CMS的有WordPress, October和Joomla! 等， 通常PHP作为CMS的模板语言。

内容管理系统（CMS）通常有两个主要组件：

- 内容管理应用程序（CMA）是前端用户界面，允许用户即使在专业知识有限的情况下，添加，修改和删除网站上的内容。
- 内容交付应用程序(CDA), （根据我的理解）应该是开发CMS的插件（plugin）或其他应用程序。
# 通过WP本身获取信息

由于WordPress是开源的，其结构公开得很清楚。详见[官网链接](https://codex.wordpress.org/WordPress_Files) 或[CSDN博客](http://blog.csdn.net/ppiao1970hank/article/details/6301808)

举例几个重要的文件：
- /wp-login.php -> 默认登陆页面

- /wp-config.php ->配置的连接数据库MySQL的文件

- /wp-admin/admin.php -> 管理文件的核心, 连接到数据库，集成动态菜单数据，显示仪表盘等.

- /wp-admin/admin-ajax.php -> 用来处理前端的ajax请求

## 1. 获取管理员名称 (login)

> 语法：
```http
http://example.com/?author=1
```
> 解释：

返回用户ID为1的所有文章的页面和用户名称。一般ID=1的WP用户是站点的超级管理员。

> 实例：
```http
http://www.ren21.net/?author=1
```

![](https://gblobscdn.gitbook.com/assets%2F-LhVVVIAnQXltst0fTl_%2F-LhVVZDY6yX73avND9-D%2F-LhVVgDxlAfQd86HWgG4%2Fimport.png?generation=1560692311748047&alt=media)

以上我画的三个地方均显示管理员的名称为admin

若查看源代码, 则同样显示管理员的名称:

![](https://gblobscdn.gitbook.com/assets%2F-LhVVVIAnQXltst0fTl_%2F-LhVVZDY6yX73avND9-D%2F-LhVVgE-B2vHRDVC2lpZ%2Fimport2.png?generation=1560692323735892&alt=media)

## 2. 小提问

为什么要获取管理员名称呢？

大多数WP的网站的默认登陆页面为wp-login.php，若站点使用的是弱密码，则黑客很容易**暴力破解**。

若不能暴力破解，则可以通过点击忘记密码，然后输入管理员名称，再通过**SQL注入**来让网页显示激活码，然后重新输入新密码。

之后的章节我将会讲解暴力破解, SQL注入等常见WP攻击方法。

附：[wordpress漏洞每日更新报告](https://wpvulndb.com/)

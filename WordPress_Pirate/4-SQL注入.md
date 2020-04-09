# SQL注入

本文参考了部分 [CSDN博客](http://blog.csdn.net/luyuncsd123/article/details/17859227) 。

WP站点网址后的参数是支持SQL子查询的,若尝试将参数值换成SQL语句,你会发现SQL语句被执行了，这就是SQL注入。

## 基本原理

sql注入主要是对页面参数**没有进行非法字符校验**导致，比如说一个订单页面要显示某个客户的所有订单列表，这个页面的地址可能是:
```http
http://xxx.com/list.php?customID=3
```

推理一下，这样页面的后台处理的sql应该是这样的：

select * form custom_order where custom_id =  {$_GET['customID']}


按正常情况下，这里的接收的参数`{$_GET['customID']}`的值应该是传入的值`3`，这样页面就能正确的把所有客户ID等于3的订单信息显示到页面上。但是，如果这个参数被人恶意改成了如下形式：

```http
http://xxx.com/list.php?customID=-1 union select 1,2,3,user,5,passwd,7,8,9,10 from admin
```

按这样的参数拼装成的后台处理的sql就成了这样：

select * form custom_order where custom_id = -1 union select 1,2,3,user,5,passwd,7,8,9,10 from admin

union select ~from 之间的参数总共有10个，说明表的结构是十列，表的列数要慢慢试出来。

则在网页显示结果为第四列显示user，第六列显示password。

这样注入恶意sql后，订单列表页显示的就不是订单信息了，而是数据库中用户的名称和密码，或者任意其它想要的信息。

## 实例 All Video Gallery

在2012年，插件[All Video Gallery](http://wordpress.org/plugins/all-video-gallery/) 存在SQL注入漏洞，于是在google搜了一下使用这个插件的网站:
```
"index of" /wp-content/plugins/all-video-gallery
```
或
```
inurl:/wp-content/plugins/all-video-gallery
```

![](https://gblobscdn.gitbook.com/assets%2F-LhVVVIAnQXltst0fTl_%2F-LhVVZDY6yX73avND9-D%2F-LhVVgFwaDiedK8eyEcK%2Fimport4.png?generation=1560692311958060&alt=media)

看来2018年还是有很多网站用这种插件的，但是很多站点更新了wordpress，站点安全方面得以加强，所以这个插件的SQL注入失败。。

![](https://gblobscdn.gitbook.com/assets%2F-LhVVVIAnQXltst0fTl_%2F-LhVVZDY6yX73avND9-D%2F-LhVVgFy6d-P6wBd9UFI%2Fimport5.png?generation=1560692311845315&alt=media)


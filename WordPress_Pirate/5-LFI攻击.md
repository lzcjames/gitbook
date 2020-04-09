# LFI攻击

LFI, Local File Include, 直译为本地文件包含。文件包含漏洞是代码注入攻击(Remote File Inclusion)的一种。

## 代码注入攻击

###  对网络用户端的攻击

注入一段网络用户端 (浏览器等) 能控制的脚本或代码，并让服务器端执行。

### 对应用程序客户端的攻击

例如 Javascript，属于跨站脚本攻击（[XSS](https://www.oneasp.com/sp/xss)）。

更多介绍详见[博客](http://blog.oneapm.com/apm-tech/558.html)

## 实例 Slider Revolution

在2014年，滑块插件 Slider Revolution 存在严重漏洞，该漏洞允许黑客从服务器的wordpress里**下载和上传文件。**

漏洞插件[源码](https://github.com/mchandleraz/tuner/tree/master/wp-content/themes/bazar/theme/templates/sliders/revolution-slider), 漏洞利用版本为4.2.0以下。

### 1. 下载文件

由于用户输入过滤器(user input filters)未能正确处理通过action 的请求“revslider_show_image”传递给“admin-ajax.php”的“img”参数值，导致黑客通过浏览器下载wordpress的有关文件，如：

```http
http://example.com/wp-admin/admin-ajax.php?action=revslider_show_image&img=../wp-config.php`
```
![](https://gblobscdn.gitbook.com/assets%2F-LhVVVIAnQXltst0fTl_%2F-LhVVZDY6yX73avND9-D%2F-LhVVgGDPBboiPK5_T10%2Fimport7.png?generation=1560692312475855&alt=media)

下载的任何文件名均为admin-ajax.php，这里实则下载的是wp-config.php，打开：

![](https://gblobscdn.gitbook.com/assets%2F-LhVVVIAnQXltst0fTl_%2F-LhVVZDY6yX73avND9-D%2F-LhVVgGF3-dh10WMtqse%2Fimport8.png?generation=1560692312467680&alt=media)

获得的是服务器数据库的database名称，管理员login和password，若该服务器的数据库接口暴露在外网，则可以直接访问。

### 2. 上传文件

#### 分析漏洞

通过制作http请求访问以上传文件。参考于[博客](http://blog.securelayer7.net/wordpress-plugin-revslider-update-captions-css-file-critical-vulnerability/)(找超久的)，接下来了解一下漏洞所在处：

```http
`http://example.com/wp-admin/admin-ajax.php?action=revslider_ajax_action&client_action=get_captions_css`
```

通过向admin-ajax.phpaction发送POST请求，请求参数为?action=...... **get_captions_css**，相当于：

```
`array(“action” => “revslider_ajax_action”,”client_action” => “get_captions_css”, “data” => “return content of css”);`
```
‌
于是在插件源码中被执行的函数是 **onAjaxAction()，**位于**revslider_admin.php。getPostGetVar()** 接收POST或GET的参数

![](https://gblobscdn.gitbook.com/assets%2F-LhVVVIAnQXltst0fTl_%2F-LhVVZDY6yX73avND9-D%2F-LhVVgGJDfqteGkSynrH%2Fimport14.png?generation=1560692312502610&alt=media)

其中触发了该函数的case语句**get_captions_css**

![](https://gblobscdn.gitbook.com/assets%2F-LhVVVIAnQXltst0fTl_%2F-LhVVZDY6yX73avND9-D%2F-LhVVgGLoeH14MtcfqMQ%2Fimport19.png?generation=1560692312512045&alt=media)

最后，返回的是captions._css_的文本内容：

![](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LhVVVIAnQXltst0fTl_%2F-LhVVZDY6yX73avND9-D%2F-LhVVgGNJZ-6OSFfnB9R%2Fimport17.png?generation=1560692312482861&alt=media)

若请求参数为?action=......**update_captions_css**，相当于：

```
array(“action” => “revslider_ajax_action”,”client_action” => “update_captions_css”, “data” => “HTML-Update-Data here”);
```

其中触发了该函数的case语句**update_captions_css**:

![](https://gblobscdn.gitbook.com/assets%2F-LhVVVIAnQXltst0fTl_%2F-LhVVZDY6yX73avND9-D%2F-LhVVgGPQIxVyKkFpP3m%2Fimport10.png?generation=1560692312468643&alt=media)

Enter a caption for this image (optional)

‌

其中函数**updateCaptionsContentData(),** 位于**inc_php/revslider_operations.class.php**

![](https://gblobscdn.gitbook.com/assets%2F-LhVVVIAnQXltst0fTl_%2F-LhVVZDY6yX73avND9-D%2F-LhVVgGR5lg_jYLErasv%2Fimport11.png?generation=1560692312507423&alt=media)

‌
其中**writeFile()是UniteFunctionsRev类**的函数**，**该类位于**inc_php/functions.class.php** 或 **inc_php/framework/functions.class.php**

![](https://gblobscdn.gitbook.com/assets%2F-LhVVVIAnQXltst0fTl_%2F-LhVVZDY6yX73avND9-D%2F-LhVVgGTXpCHIbAnBsVA%2Fimport12.png?generation=1560692312478322&alt=media)

终于找到了漏洞点，函数**fwrite()**和没有进行任何处理的参数**$str**

‌

### 3. 实战

理一下思路，post请求中的`data` = `一段html恶意代码`，`data` 被函数**onAjaxAction()**接收并放入`$data`里，接着执行该函数的case语句**update_captions_css**，把`$data`传到函数**updateCaptionsContentData()**,  此时`$data`相当于`$content`, 把`$content`传到函数**writeFile()**，此时`$content`相当于`$str`, 然后把`$str`传到函数**fwrite()**中, 执行完毕。

还有一点很重要的是站点服务器**others组**的**写入权限**应该对captions.css起效才行：

![](https://gblobscdn.gitbook.com/assets%2F-LhVVVIAnQXltst0fTl_%2F-LhVVZDY6yX73avND9-D%2F-LhVVgGVf-uDga1cB6qg%2Fimport20.png?generation=1560692312478647&alt=media)

[攻击的源码的链接这里查看](https://packetstormsecurity.com/files/131246/WordPress-Revolution-Slider-File-Upload.html)

![](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LhVVVIAnQXltst0fTl_%2F-LhVVZDY6yX73avND9-D%2F-LhVVgGXaJ9zFA6peGCS%2Fimport18.png?generation=1560692312780427&alt=media)

执行之后，相当于把**captions.css**文件内容改为`<h1>Bonjour!</h1>`, 在浏览器输入

```
example.com/wp-admin/admin-ajax.php?action=revslider_ajax_action&client_action=get_captions_css 
```

就可以看到结果.

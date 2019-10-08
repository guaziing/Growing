# HTML头文件及其style scirpt中配置的意思
## **html**
```htmlbars
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>bilibili首页</title>
</head>
<body>
  
</body>
</html>
```
**1. &lt;!DOCTYPE html>**
**解释： **它是指示 web 浏览器关于页面使用哪个 HTML 版本进行编写的指令。这种写法指的是使用HTML5的版本进行编写（HTML5的写法只有这一种）
***
**2. &lt;html lang="en">**
**解释：** 写在html标签中的lang属性作用：声明当前页面的语言类型。
```htmlbars
<html lang='en'></html> //英文
<html lang='zh'></html> //中文
<html lang='zh-CN'></html> //中文简体
<html lang='ja'></html> //日文
<html lang='en-us'></html> //美式英文
注意：lang属性中的语言代码不区分大小写
<html lang='en-us'></html> //英文
<html lang='en-US'></html> //英文
上面的两行代码一样的效果。
另外，lang属性也可以加到普通标签上。
如：
<div lang='en'>this is English .</div>
```
***
**3. &lt;head>标签的内容**
```htmlbars
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width,initial-scale=1.0">
    <title>traveling</title>
  </head>
```
**4. meta标签的两个属性：http-equiv属性和name属性**
- name属性
```html
1.viewport属性
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0">
<!-- 
width=device-width: 可视区域的宽度(设备的宽度）
intial-scale:页面首次被显示是可视区域的缩放级别，取值1.0则页面按实际尺寸显示，无任何缩放
maximum-scale=1.0, minimum-scale=1.0;可视区域的缩放级别，
maximum-scale用户可将页面放大的程序，1.0将禁止用户放大到实际尺寸之上。
user-scalable:是否可对页面进行缩放，no 禁止缩放 
viewport-fit：将整个网站扩展到整个屏幕
-->
<!-- 移动端的需要的配置 -->
<meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no, minimum-scale=1.0, maximum-scale=1.0" />
<!-- iphoneX配备一个覆盖整个手机的全面屏，顶部的“刘海”为相机和其他组件留出了空间，网站被限制在一个“安全区域”，在两侧边缘会出现白条儿，解决最终方案加viewport-fit=cover -->
<meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no, minimum-scale=1.0, maximum-scale=1.0 viewport-fit=cover" />

2.keyword属性：用于告诉搜索引擎，你网页的关键字
<meta name="keywords" content="Lxxyx,博客，文科生，前端">

3.description属性：网站内容的描述
<meta name="description" content="文科生，热爱前端与编程。目前大二，这是我的前端博客">

？？？？？？？？？？？？
4.robots：robots用来告诉爬虫哪些页面需要索引，哪些页面不需要索引。
content的参数有all,none,index,noindex,follow,nofollow。默认是all。
<meta name="robots" content="none">
<!-- 
1.none : 搜索引擎将忽略此网页，等价于noindex，nofollow。
2.noindex : 搜索引擎不索引此网页。
3.nofollow: 搜索引擎不继续通过此网页的链接索引搜索其它的网页。
4.all : 搜索引擎将索引此网页与继续通过此网页的链接索引，等价于index，follow。
5.index : 搜索引擎索引此网页。
6.follow : 搜索引擎继续通过此网页的链接索引搜索其它的网页。
-->

5.author：用于标注网页作者
<meta name="author" content="Lxxyx,841380530@qq.com">
：6.generator：网页制作软件？？？？？？
<meta name="generator" content="Sublime Text3">

7.copyright：用于标注版权信息
<meta name="copyright" content="Lxxyx"> //代表该网站为Lxxyx个人版权所有。

8.revisit-after：如果页面不是经常更新，为了减轻搜索引擎爬虫对服务器带来的压力，可以设置一个爬虫的重访时间。如果重访时间过短，爬虫将按它们定义的默认时间来访问
<meta name="revisit-after" content="7 days" >

9.renderer：renderer是为双核浏览器准备的，用于指定双核浏览器默认以何种方式渲染页面。比如说360浏览器。
<meta name="renderer" content="webkit"> //默认webkit内核
<meta name="renderer" content="ie-comp"> //默认IE兼容模式
<meta name="renderer" content="ie-stand"> //默认IE标准模式
```
- http-equiv属性: 相当于http的文件头作用
```html
1.content-Type:用于设定网页字符集，便于浏览器解析与渲染页面
<meta http-equiv="content-Type" content="text/html;charset=utf-8">  //旧的HTML，不推荐
<meta charset="utf-8"> //HTML5设定网页字符集的方式，推荐使用UTF-8

2.X-UA-Compatible：用于告知浏览器以何种版本来渲染页面。（一般都设置为最新模式，在各大框架中这个设置也很常见。）
<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1"/> //指定IE和Chrome使用最新版本渲染当前页面

3. cache-control:一个是指导浏览器如何缓存某个响应以及缓存多长时间
<meta http-equiv="cache-control" content="no-cache">
<!-- 1.no-cache: 先发送请求，与服务器确认该资源是否被更改，如果未被更改，则使用缓存。
2.no-store: 不允许缓存，每次都要去服务器上，下载完整的响应。（安全措施）
3.public : 缓存所有响应，但并非必须。因为max-age也可以做到相同效果
4.private : 只为单个用户缓存，因此不允许任何中继进行缓存。（比如说CDN就不允许缓存private的响应）
5.maxage : 表示当前请求开始，该响应在多久内能被缓存和重用，而不去服务器重新请求。例如：max-age=60表示响应可以再缓存和重用 60 秒。 
参考：HTTP缓存：https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/http-caching?hl=zh-cn#cache-control-->
另一个作用：用于禁止当前页面在移动端浏览时，被百度自动转码。虽然百度的本意是好的，但是转码效果很多时候却不尽人意。所以可以在head中加入例子中的那句话，就可以避免百度自动转码了。
<meta http-equiv="Cache-Control" content="no-siteapp" />

4.expires：用于设定网页的到期时间，过期后网页必须到服务器上重新传输。
<meta http-equiv="expires" content="Sunday 26 October 2016 01:00 GMT" />

5.refresh：网页将在设定的时间内，自动刷新并调向设定的网址
<meta http-equiv="refresh" content="2；URL=http://www.lxxyx.win/"> //意思是2秒后跳转向我的博客

6.Set-Cookie：如果网页过期。那么这个网页存在本地的cookies也会被自动删除。
<meta http-equiv="Set-Cookie" content="name, date"> //格式
<meta http-equiv="Set-Cookie" content="User=Lxxyx; path=/; expires=Sunday, 10-Jan-16 10:00:00 GMT"> //具体范例
```
**5. &lt;base>标签**
```htmlbars
<base href="http://www.w3school.com.cn/i/" />
<base target="_blank" />
```
**解释：**href：规定页面中所有相对链接的基准URL;
	target ：规定在何处打开页面中所有的链接
**6. &lt;link>标签**        标签定义文档与外部资源的关系
**7. &lt;script>标签**        标签定义文档与外部资源的关系，script元素既可以包含脚本语句，也可以通过src属性指向外部脚本文件，-必需的type属性规定脚本的MIME类型

----------
**8. style**
```htmlbars
<style lang="stylus" rel="stylesheet/stylus">
```
**rel:**为了让编辑器知道是stylus的语法，不让编辑器认为只是一个错误的代码

**9. script**
```htmlbars
<script type="text/ecmascript-6"></script>
```
**type="text/ecmascript-6"** 让script中支持ES6的语法
### HTML头文件的意思
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
**&lt;!DOCTYPE html>**
**解释： **它是指示 web 浏览器关于页面使用哪个 HTML 版本进行编写的指令。这种写法指的是使用HTML5的版本进行编写（HTML5的写法只有这一种）
***
**&lt;html lang="en">**
**解释： **写在html标签中的lang属性作用：声明当前页面的语言类型。
```htmlbars
<html lang='en'></html> //英文
 <html lang='zh'></html> //中文
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
**&lt;head>标签的内容**
```htmlbars
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width,initial-scale=1.0">
    <title>traveling</title>
  </head>
```
**meta**    标签的配置：width=device-width: 可视区域的宽度(设备的宽度)
intial-scale:页面首次被显示是可视区域的缩放级别，取值1.0则页面按实际尺寸显示，无任何缩放
maximum-scale=1.0, minimum-scale=1.0;可视区域的缩放级别，
maximum-scale用户可将页面放大的程序，1.0将禁止用户放大到实际尺寸之上。
user-scalable:是否可对页面进行缩放，no 禁止缩放
**&lt;base>标签**
```htmlbars
<base href="http://www.w3school.com.cn/i/" />
<base target="_blank" />
```
**解释：**href：规定页面中所有相对链接的基准URL;
	target ：规定在何处打开页面中所有的链接
**&lt;link>标签**        标签定义文档与外部资源的关系
**&lt;script>标签**        标签定义文档与外部资源的关系，script元素既可以包含脚本语句，也可以通过src属性指向外部脚本文件，-必需的type属性规定脚本的MIME类型


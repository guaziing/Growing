# 整理js的文件
## 一些基本的命令
```js
var demo = document.getElementById("demo");

//打开窗口进行的命令
window.onload = function(res) {
}
```
```js
//1. 对页面样式和内容的操作：
var width = window.getComputedStyle(demo).width;//获取Dom元素的宽高

//write()会对内容进行html的分析后得出表达内容  document.write会将页面上的所有内容清除包括标题
document.write("<h1>This \is a heading</h1>");
//相当于在这一行加一个</br> 
document.writeln("<h1> this is a demo") 
//innerHTMl会重写这个Dom结点的内容
demo.innerHTML = "<p>nihao</p>"

//改变样式
demo.style.color = "white";

//获取input的value
var x = document.getElementById("demo").value;
```
**获取页面上Dom结点的信息点击事件的操作**
```js

//html中的点击的写法： 
<button type="button" onclick="myFunction()">点击这里</button>

//字符串中的\n\n表示换行

//代码中try...catch用来及检测代码 try中包含检测的代码，catch中会有代码中出现的错误
try
{
  adddlert("Welcome guest!")
}
catch(err)
{
  txt="本页中存在错误。\n\n"
  txt+="错误描述：" + err.description + "\n\n"
  txt+="点击“确定”继续。\n\n"
  alert(txt)
}
```
**对数据类型的操作**
```js
//对对象的操作
var o = new Object;
o.call = "赵星星";
document.write(o.call);
delete o.call;

/*原型方式并改进
function creat(){}
	
creat.prototype.color = "red";
creat.prototype.doors = 15;
creat.prototype.show = showcolor;
creat.prototype.xinde = new Array("Mike","john");
var nu1=new creat();
nu1.xinde.push("bill")
```

# js中的setInterval
用法：对操作方法按照一定时间间隔进行调用的函数。（循环调用）
语法：
> **第一种：setInterval(
fnname(匿名函数的引用|函数名),
time（设定的调用faname的时间间隔，单位为毫秒，）,
par1,par2,........parn(par1.......parn为可选参数，是传递给faname方法的参数。));
第二种：setInterval(
obj(对象),
fnname(faname参数是obj对象的方法),
time,
par1,par2,......parn);**
```js
//普通语法的第一种写法
 
setInterval(function(){
    alert("我是setInterval方法打印结果")；
  }，3000) //每隔3秒打印一次
 
//普通语法的第二种写法
 
function alert1(){
    alert("我是setInterval方法打印结果")
  }
function alert2(str){
    alert(str);
  }
  setInterval(alert1,3000);
  setInterval("alert1()",3000);
  setInterval(alert2,3000,"我是setInterval方法打印结果");
  setInterval("alert1()",3000,"我是setInterval方法打印结果");
 
//对象方法写法
 
obj = new Object();//创建一个新的对象
 
obj.alert1 = function(){
    alert("我是setInterval方法打印结果");
  }
 
obj.alert2 = function(str){
    alert(str);
  }
 
setInterval(obj,alert1,3000);
setInterval(obj,alert2,3000,"我是setInterval方法打印结果")；
```
**常用搭配**
```js
//，clearInterval的作用是清除setInterval方法的调用，clearInterval的参数是setInterval的返回值

var timer = setInterval(obj,alert1,3000);
clearInterval(timer);
```
*参考：[ https://www.jb51.net/article/69680.htm ]*
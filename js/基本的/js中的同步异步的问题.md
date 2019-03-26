# js中的同步异步的问题
*参考：[ https://www.cnblogs.com/zhuchenglin/p/7651990.html ]*

## **1. Promise**
> *Promise是ES6中的函数，规范了如何处理异步任务的回调函数，功能类似于jQuery的defferred。简单说就是通过promise对象的不同状态调用不同的回调函数。目前IE8及以下不支持，其他浏览器都支持。*

### **resolve**
// 对于执行成功的回调就会使用resolvePromise.resolve方法返回一个promise的实例
```js
Promise.resolve('foo') 
// 上面等价于：
new Promise((resolve) => {
  resolve('foo')
})
```
根据resolve中的参数的不同分为下列几种情况

- 参数是一个Promise的实例: 如果参数是一个Promise的实例，那么Promise.resolve将不作任何修改，原封不动的返回这个实例
- 参数是一个thenable对象: Promise.resolve方法会将这个对象转为Promise对象，然后立即执行thenable对象的then方法

```js
//thenable对象
let thenable = {
    then:function(resolve,reject){
        console.log(55555);
        resolve(42);
    }
}
//下面会将thenable对象转换为Promise对象
let p = Promise.resolve(thenable);
p.then((value)=>{
    console.log(value);
});
// 结果：555 42
```
- 参数不是具有then方法的对象或者不是对象: 如果参数是一个原始值，或者是一个不具有then方法的对象，那么Promise.resolve方法返回一个新的Promise对象，状态为Resolved。
```js
var p = Promise.resolve("hello 1024");//字符串不属于异步操作，判断方法是不具有then方法，返回的Promise的实例从生成起就是Resolved，所以回调函数会立即执行。Promise.resolve参数就会同时传给回调函数
p.then((value)=>{
    console.log(value);//hello 1024
});
```
- 不带任何参数: 直接返回一个状态为resolved的Promise对象，所以如果希望得到一个Promise对象，最直接的方法就是直接调用Promise.resolve方法
```js
var p = Promise.resolve("name");
p
    .then((data)=>{
    console.log(data) //name
    return "next-name"  // return的内容可以是promise对象也可以是直接的数据   
})
    .then((data) => {
        consoel.log(data)// next-name
    })
    .catch((reject)=>{
    });
```
**对比promise函数和直接回调函数**
```js
function runAsync(){
  var p = new Promise(function(resolve, reject){
      //做一些异步操作
      setTimeout(function(){
          console.log('执行完成');
          resolve('随便什么数据');
      }, 2000);
  });
  return p;   // return的内容可以是promise对象也可以是直接的数据
}
runAsync().then(function(data) {
  console.log(data) //其中的data 表示的是上面函数成功的resolve的结果
  return "hao"
})
.then(function(data) {
  console.log(data)
})

////上面的方法同样可以这样写
function runAsync(callback){
    setTimeout(function(){
        console.log('执行完成');
        callback('随便什么数据');
    }, 2000);
}

runAsync(function(data){
    console.log(data);
});
```
***缺陷：**这样写的话遇到多个异步操作就会很麻烦，而Promise的优势在于，可以在then方法中继续写Promise对象并返回，然后继续调用then来进行回调操作；从表面上看，Promise只是能够简化层层回调的写法，而实质上，Promise的精髓是“状态”，用维护状态、传递状态的方式来使得回调函数能够及时调用，*
```js
// 链式操作的写法
function taskA() {
  setTimeout(function() {
    console.log("three")
  },1000);
}
function taskB() {
  console.log("taskB");
}
Promise.resolve()
      .then(taskA)
      .then(taskB)
    console.log("one")
// 结果： one taskB taskB
```

### **reject**
*reject的作用是把Promise的状态置为rejected，这样我们在then中就能捕捉到，然后执行“失败”情况的回调。*
```js
function getNumber(){
    var p = new Promise(function(resolve, reject){
        //做一些异步操作
        setTimeout(function(){
            var num = Math.ceil(Math.random()*10); //生成1-10的随机数
            if(num<=5){
                resolve(num);
            }
            else{
                reject('数字太大了');
            }
        }, 2000);
    });
    return p;            
}

getNumber()
.then(
    function(data){
        console.log('resolved');
        console.log(data);
    }, 
    function(reason, data){
        console.log('rejected');
        console.log(reason);
    }
);
// catch
getNumber()
.then(data => {
console.log(data)
}
.catch((reason) => {
    console.log(reason)//reject回调函数的信息
})
```
### **catach**
*和reject的用法相似：看上面*
*与此同时，在链式环节中出现了异常则会直接跳到catch方法中去 *

### **promise.all**
*接收一个 promise对象的数组作为参数，当这个数组里的所有promise对象全部变为resolve或reject状态的时候，它才会去调用 .then 方法。*

    Promise
    .all([runAsync1(), runAsync2(), runAsync3()])
    .then(function(results){
        console.log(results);
    });
    // all数组里面的内容全部都是promise函数
    //输出内容：1完成 2完成 3完成 ["随便1"， "随便2", "随便3"]
*有了all，你就可以并行执行多个异步操作，并且在一个回调中处理所有的返回数据，是不是很酷？有一个场景是很适合用这个的，一些游戏类的素材比较多的应用，打开网页时，预先加载需要用到的各种资源如图片、flash以及各种静态文件。所有的都加载完后，我们再进行页面的初始化。*

### **Promise.race**
```js
Promise
.race([runAsync1(), runAsync2(), runAsync3()])
.then(function(results){
    console.log(results);
});
//结果：1完成 数据1 2完成 3完成
```

### **Promise.done()**
*Promise 对象的回调链，不管以then方法或catch方法结尾，要是最后一个方法抛出错误，都有可能无法捕捉到（因为 Promise 内部的错误不会冒泡到全局）。因此，我们可以提供一个done方法，总是处于回调链的尾端，保证抛出任何可能出现的错误。*
```js
asyncFunc()
  .then(f1)
  .catch(r1)
  .then(f2)
  .done();
```
### **Promise.finally()**
*finally方法用于指定不管 Promise 对象最后状态如何，都会执行的操作。只要proise对象出现最后状态，finally方法就一定会执行*
```js
server.listen(0)
  .then(function () {
    // run test
  })
  .finally(server.stop);
  //finally done借鉴https://blog.csdn.net/momDIY/article/details/77856099
```
*以上借鉴：[https://blog.csdn.net/qq_27970999/article/details/78702225*
[https://blog.csdn.net/weixin_42367621/article/details/80824277
## **2. 同步异步**
JavaScript最基础的异步函数是setTimeout和setInterval
*对于setTimeout函数：这个API不能保证计时会如期准确地运行。由于CPU负载、其他任务等所导致的延迟是可以预料到的。*
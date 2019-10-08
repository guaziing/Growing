# js中filter和map的使用

**filter作用:** 它用于把Array的某些元素过滤掉，然后返回剩下的元素。

filter中的函数可以有三个参数 filter(function(element(数组中的各项值)，index(各项值得索引)， self(该数组的变量（arr）)) {})
利用其性质可以巧妙的修改数组：案例(将重复项去除)

    var r, arr = ['apple','strawberry','banana','pear','apple','orange','orange','strawberry;
    r = arr.filter(function (element, index, self) {
            return self.indexOf(element) === index; //返回留下的条件
        });
    console.log(r.toString());
    
    
**map：** 保存键值对。任何值(对象或者原始值) 都可以作为一个键或一个值,其中键可以是任意值，包括函数、对象、基本类型。map和object很相似，允许你按键存取一个值、删除键、检测一个键是否绑定了值，属性：**size,delete(键),has(值)(判断有没有这个值),set(键,值),get(键)(获取键相关的值),keys()(返回以键形成的新的数组)，clear()(清空map中的值)**

在下列情况下比较适合使用map：

 - 一个对象的键只能是字符串或者 Symbols"Symbol()函数会返回symbol类型的值，该类型具有静态属性和静态方法。它的静态属性会暴露几个内建的成员对象；它的静态方法会暴露全局的symbol注册，且类似于内建对象类，但作为构造函数来说它并不完整，因为它不支持语法："new Symbol()"。但一个Map的键可以是任意值，包括函数、对象、基本类型
 - 可以通过size属性来看有多少个键值对个数，object只能手动计算
 - Map 在涉及频繁增删键值对的场景下会有些性能优势。
 
实例代码：
```js
    /**
     * map() 方法返回一个新数组，数组中的元素为原始数组元素调用函数处理后的值。
     * map() 方法按照原始数组元素顺序依次处理元素。
     * 注意： map() 不会对空数组进行检测。
     * 注意： map() 不会改变原始数组。
     */
    var m = new Map([[1,"x"],[2,"y],[3,"z]]);
    //返回Map对象的键/值对的数量。
    console.log(m.size)
    //map赋值
    m.set("key","value")
    //判断是否有值
    m.has("bar"); // 还可以写成containKey(key)(有没有这个键值的)，containValue(value)
    //返回键对应的值，如果不存在，则返回undefined。
    m.get("key")
    //移除任何与键相关联的值，并且返回该值，该值在之前会被Map.prototype.has(key)返回为true。
    //之后再调用Map.prototype.has(key)会返回false。
    m.delete("key")
    //返回一个新的 Iterator对象， 它按插入顺序包含了Map对象中每个元素的键 。
    m.keys();
    //清空map中的值
    m.clear();
    //向map中添加元素（key，value）
    put(key,value)
    //删除指定的key元素
    remove(key)//成功返回true
    //获取指定索引的元素
    emement(index)//使用element.key,element.vlaue获取value和key值，失败返回null
    //获取map中的所有value，key数组
    m.values()//m.keys()
    for of 遍历map
    for (var x of m){
        //遍历map
        console.log(x);
        console.log(x[0]);
        // test();
        // console.log(area_of_circle(3));
    }
    //Map的回调函数参数依次为value、key和map本身：
    m.forEach(function(value,key,map){
        console.log('value='+value+',key='+key+',map='+map)
    })
```
参考[https://blog.csdn.net/weixin_33725239/article/details/88237449]
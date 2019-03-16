### vue文档获取的知识
**修饰符**
> **表单中的input的修饰符：**
> .lazy：加lazy修饰符的区别相当于在输入后失去焦点或者摁了enter键视图才更新。不加lazy则是在keyup就更新
.trim:自动过滤用户输入的首尾空格（中间空格过滤不了）
.number：把输入的数值从字符串或其他类型转换为number类型
.trim:自动过滤用户输入的首尾空格（中间空格过滤不了）
**事件修饰符**
.stop:  阻止单击事件冒泡
.pervent: 提交事件不再重载页面
.capture: 添加事件侦听器时使用事件捕获模式 
.self:  只当事件在该元素本身（而不是子元素）触发时触发回调 
**按键修饰符**
.数字（<input v-on:keyup.13="submit">):只有在 keyCode 是 13 时调用 vm.submit() 
其他按键：enter，tab，delete (捕获 “删除” 和 “退格” 键)，esc，space，up，down，left，right

可以通过全局 config.keyCodes 对象自定义按键修饰符别名：
```vue
    Vue.config.keyCodes.f1 = 112
```

    <input v-model.trim="msg">
    <input @click.stop.prevent="msg">//修饰符可以串联

**绑定:v-model(用在的对象)**
 **input** **textarea** **select**
 
**其他修饰符**
> **.native** 监听组件根元素的原生事件。 
主要是给自定义的组件添加原生事件。

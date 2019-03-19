# vue架构 对比 组件化

### **MV*架构**
*架构从喜欢传统后台MVCx向REST API + 前端MV*（包括了MVC MVP MVVM(Vue.js框架使用的)） 迁移*

 - **MVVM**
 *使用的该架构的框架: angular.js react.js vue.js*
 
```flow
st=>start: View(视图DOM)
op1=>operation: ViewModel（通讯（观察者，连接视图和数据的中介））
op2=>operation: Model（数据JavaScript对象）
cond=>condition: Yes or No?
e=>end

st->op1->op2
```
*具体过程*通过viewmodel来进行通信,观察model的数据变化在反馈到视图上面,监听视图的变化哦通知数据改动,实现双向绑定
*使用的好处:*
1. 针对复杂交互
2. 提供基础的架构抽象
3. 通过ajax数据持久化,保证前端用户体验
4. 轻量级
5. 数据驱动 + 组件化的前端开发
6. 社区完善(论坛之类的,分支里面有源码)
> **数据驱动** dom是数据的一种自然映射（viewjs进行监听属性）
*model(数据)是怎么驱动view视图更新的*

### 与其他框架的对比
1. vue.js更轻量
2. 容易上手（最难的是angular.js（很多思想是后端的），react学习曲线平稳，借鉴其他的长处（借鉴了angular指令的概念（v-show之类的），react的组价话思想），还有自己的计算属性）


### 组件化
*扩展HTML元素，封装可重用的代码*
> **组件设立原则：** 
1. 每个独立可交互的区域
2. 每个组件对应一个工程目录，组件所需要的资源
3. 可嵌套
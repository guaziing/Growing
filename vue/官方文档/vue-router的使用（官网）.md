# vue-router的使用（官网）
### **1. 在自己新建的路由文件中引入vue-router**
```vue
import Vue from 'vue'
import VueRouter from 'vue-router'
//后面引入组件 

Vue.use(VueRouter)
const router = new VueRouter({
    routes: [{}] //在里面配置路由。配置路由相关项
})
export default router //到处路由
```
**实例**
```js
import Vue from 'vue'
import VueRouter from 'vue-router'
import Foo from '../components/foo.vue'
import Index from '../components/index.vue'
import Bar from '../components/bar.vue'

Vue.use(VueRouter)
const router = new VueRouter({
  linkActiveClass: 'active', //这个位置的使用主要是用于正在活跃的元素中拥有.active的元素的配置，比如说 a &.active{样式}
  hashbang: true, // 将路径格式化为#!开头
  history: true, // 启用HTML5 history模式，可以使用pushState和replaceState来管理记录
  routes: [
    {
      path: '/',
      component: Index
    },
    {
      path: '/foo',
      component: Foo
    },
    {
      path: '/bar',
      component: Bar
  }]
})
/*
router.beforeEach((to, from, next) => {
  store.dispatch('updateHistoryLength')
  next()
}) */
export default router
```
### **2. 在main.js中引入上面的文件**
```js
// The Vue build version to load with the `import` command
// (runtime-only or standalone) has been set in webpack.base.conf with an alias.
import Vue from 'vue'
import App from './App'
import router from './router/index.js'

Vue.config.productionTip = false

/* eslint-disable no-new */
new Vue({
  el: '#app',
  router,
  components: { App },
  template: '<App/>'
})
```
### **3. 在项目中的跳转路由（还可以传输数据）**
**$router**

> this.$router.push('跳转的路径')
还可以写成:

```js
this.$router.push({
    path:'/',
    query: {
      id: 'bar'
    }
})
```
### 4. **关于路由跳转的方式和跳转历史**

- 替换路由： this.$router.replace(url)
- 退或者进路由的转换：this.$router.go(num)（退后或者前进多少步）
```vue
window.history.length > 1    //判断访问的路由有多少个了
    ? this.$router.go(-1)   //回到上一次访问的路由
    : this.$router.push('/')
```
### **5. 命名视图**
使用方法：
**1. 在app.vue中先进行渲染**

```vue
<template>
  <div id="app">
    <router-view></router-view>
    <router-view name="nav"></router-view>
    <router-view name="ul"></router-view>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
</style>
```
**2.在router.js中写合成的组件**

```js
import Vue from 'vue'
import VueRouter from 'vue-router'

Vue.use(VueRouter)

const router = new VueRouter({
  linkActiveClass: 'active',
  hashbang: true, // 将路径格式化为#!开头
  history: true, // 启用HTML5 history模式，可以使用pushState和replaceState来管理记录
  routes: [
    {
      path: '/index',
      components: {
        default: () =>import('../components/index/index.vue'),
        ul: () => import('../components/index/components/ul.vue')
      }
    },{
      path: '/head',
      components: {
        default: () => import('../components/index/components/head.vue'),
        nav: () => import('../components/index/components/nav.vue')
      }
    },{
      path: '/nav',
      components: {
        nav: () => import('../components/index/components/nav.vue'),
        ul: () => import('../components/index/components/ul.vue')
      }
    }]
})
/*
router.beforeEach((to, from, next) => {
  store.dispatch('updateHistoryLength')
  next()
}) */
export default router
```
还可以嵌套和命名视图一起用
*参考:[https://www.jb51.net/article/154940.htm]*

### **6. 重定向和别名**
[https://blog.csdn.net/lhjuejiang/article/details/81085427]

### **7. 嵌套路由中的使用**
```js
const routes = [
  {
    path:"/",
    component: Index,
    redirect: '/index/seller',   //默认的子路由，在访问根路径的时候直接到路由/index/seller
    children: [
      {
        path: '/index/seller',
        component: Seller
      },
      {
        path: '/index/goods',
        component: Goods
      },
      {
        path: '/index/ratings',
        component: Ratings
      }
    ]
  }
]
```
### Passing Props to Route Components
# 建立vue基础模板

### 1. 安装SublimeTmpl插件
> 在官网中[https://github.com/kairyou/SublimeTmpl]clone下来[git clone https://github.com/kairyou/SublimeTmpl.git]放到*C:\Users\acer\AppData\Roaming\Sublime Text 3\Packages*目录中
*参考：[http://www.cnblogs.com/yanchuanblog/p/3817634.html]*

### 2. 建立vue基础模板
> 1.Preferences>Browse Packages>SublimeTmpl>templates   新建vue.tmpl
```vue
<template>
	<div>
		<header-component/>
		<div>this is template body</div>
		<other-component/>
	</div>
</template>
<style>
	body{
		background-color: #ff0000;
	}
</style>
<script>
	import HeaderComponent from './components/header.vue'
	import OtherComponent from './components/other.vue'
	export default{
		data(){
			return{
				msg:'hello vue'
			}
		},
		components:{
				'other-component':OtherComponent,
				HeaderComponent
			}
	}
</script>
```
> 2.Preferences>Package settings> sublime Tmpl>Commands default,打开Default.sublime-commands, 复制粘贴：
```js
,{
    "caption": "Tmpl: Create vue", "command": "sublime_tmpl",
    "args": {"type": "vue"}
}
```
> 3.添加快捷键Preferences>Package settings>sublime Tmpl>key Bindings-Default,打开Default.sublime-commands，复制粘贴以下配置：
```js
,{
        "keys": ["ctrl+alt+e"], "command": "sublime_tmpl",
        "args": {"type": "vue"}, "context": [{"key": "sublime_tmpl.vue"}]
    }
```
*参考：https://blog.csdn.net/qikule/article/details/80417515*

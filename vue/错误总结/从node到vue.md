### 从node到vue
####  感天动地，Oh，yeah
> * 在官网安装node：[https://nodejs.org/en/]
> * 再在自己安装的目录下新建两个文件夹（自己新建的nodejs文件夹）：node_cathe和node_global
> * 运行：npm config set prefix "D:\浏览器\nodejs\node_global"以及运行：npm config set cache "D:\浏览器\nodejs\node_cache"（该部分本人安装错误，后面也可以了）
> * 安装测试包: npm install express -g
> * 在环境变量中新建变量NODE_PATH，变量值：D:\浏览器\nodejs\node_global\node_modules
> * 进入node测试：运行 node    运行：require('express')如果出现详细信息就成功的安装了全局

以上的借鉴： https://jingyan.baidu.com/article/91f5db1b2bb6941c7f05e33c.html

#### 安装vue
> * 安装cnpm在命令行中输入npm install -g cnpm--registry=http://registry.npm.taobao.org
> * 运行 npm install -g vue-cli
> * 运行vue init webpack firstVue 出错了(vue不是内部或外部命令)
以上借鉴[https://www.jb51.net/article/113612.htm]

>**原因：**没有正确安装环境变量
> * **解决方法：**

> * 运行： npm config get prefix（获取查看npm的全局路径是什么）
借鉴： [https://blog.csdn.net/GXing007/article/details/79621147]
> * 在将其配置在环境配置里面（path中）

再次vue init webpack demo运行正确

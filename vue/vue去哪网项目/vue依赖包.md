### vue依赖包
package.json: 安装相关依赖
package-lock.json：可以帮助我们知道第三方的版本
LICESE: 项目协议的说明
index.html：默认模板文件
pstcssrc.js: 对postcss的配置项
gitignore：选择哪些文件不被上传到（本地或者线上的）仓库
eslintrc.js: 规定代码的一些规范（检测工具）
eslintignore: 不被检测工具的文件
editorconfig：配置编辑器中的语法（tab表示两个空格的缩进）
babelrc：语法解析器（语法转换，需要配置的时候需要放在这个文件中来做）

static：静态资源，只有这个部分的内容可以被外部访问（比如浏览器下面可以直接访问这个目录下的内容http://localhost:8080/static/mock/index.json）

node_modeules: 项目开发时依赖的相关node的包

config: 项目的配置文件
index.js：基础的配置信息
dev.env.js: 开发环境的配置信息
prod.env.js: 线上环境的配置信息

src: 整个项目的源代码
assets：项目中用到的图片类的资源
main.js：入口文件
App.vue： 项目的最原始根组件
router》index.js：放整个项目路由
components：放小组件

build：项目打包的webpack的内容
webpack.bace.conf.js webpack.dev.conf.js webpack.prod.conf.js: 配置基础的webpack配置项 开发环境 线上环境的配置项


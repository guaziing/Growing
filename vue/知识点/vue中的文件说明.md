### vue中的文件说明
package.json: 配置文件，安装相关依赖
> dependencies：在生产环境中的依赖

package-lock.json：可以帮助我们知道第三方的版本
LICESE: 项目协议的说明
index.html：默认模板文件
pstcssrc.js: 对postcss的配置项## 标题 ##
gitignore：选择哪些文件不被上传到（本地或者线上的）仓库，进行忽略
eslintrc.js: 规定代码的一些规范（检测工具）
> extends: standard(标准规则)[https://github.com/vuejs/eslint-plugin-vue#priority-a-essential-error-prevention]
> rules（配置规则）
关于其中的配置（比如必须加上；）可以到官网上去看[https://eslint.org/docs/rules/]

eslintignore: 不被检测工具的文件（忽略对es6语法的检查）
editorconfig：配置编辑器中的语法（tab表示两个空格的缩进）
> charset(表示编码)
> indent_style = space（缩进风格）
> indent_size = 2 （缩进代码是两个）
> end_of_line: lf(linux换行的风格) (换行符风格 )
> insert_final_newline = true (表示创建一个文件会在文末插入一行)
> trim_trailing_whitespace = true(表示在文末会删除多余的空格)

babelrc：语法解析器（语法转换，需要配置的时候需要放在这个文件中来做，由于兼容性问题在这个部分可以将部分代码记性转换）
> presets(预设)：预先安装的插件
> plugins(将es6的方法进行转换)
> comments：false（转换过后给代码生成注释）

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


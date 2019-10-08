# vue中安装的配置和依赖
### **1. 安装stylus**
```js
npm install stylus stylus-loader --save-dev
```
在写css的时候会发现vue会自动补全兼容性问题
*原因：vue中有postcss插件，自动磨平浏览器中的兼容性的写法*

### **2. 在vscode中形成vue的模板**
> 在设置中的用户模板进行设置，
> 在搜索框中输入vue后enter
> 将下面的json文件放在vue.json中
```json
{
  "Print to console": {
    "prefix": "vue",
    "body": [
      "<!-- $0 -->",
      "<template>",
      "  <div></div>",
      "</template>",
      "",
      "<script>",
      "export default {",
      "  data () {",
      "    return {",
      "    };",
      "  },",
      "",
      "  components: {},",
      "",
      "  computed: {},",
      "",
      "  mounted: {},",
      "",
      "  methods: {}",
      "}",
      "",
      "</script>",
      "<style lang='scss' scoped>",
      "</style>"
  ],
    "description": "Log output to console"
  }
}
```
**注意：$0 表示你希望生成代码后光标的位置 ; prefix 表示生成对应预设代码的命令**
**vue模板的使用： vue文件输入vue后enter**
### **3. dev-**
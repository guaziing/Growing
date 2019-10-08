# 初识react

## 1. 第一个：demo的react helloworld
```htmlbars
注意：如果我们需要使用 JSX，则 <script> 标签的 type 属性需要设置为 text/babel。
```

## 2. 正式创建react项目demo
步骤：
> cnpm install -g create-react-app
 create-react-app my-app
 cd my-app/
 npm start

 ### react组件的方式
 ```js
// 封装一个成一个函数
function Hello(props) {
  return <h1>{{props.name}}</h1>
}
const element = <Hello name="Runboob" />;

React.render(
  element,
  document.getElementById('example')
)

//使用ES6的class来定义一个组件
class Welcome extends React.Component {
  reder () {
    return <h1>hello world</h1>
  }
}
 ```

 ## 在react中的state状态
 ```js
class Clock extends React.Component {
  constructor(props) {
    super(props);
    this.state = {date: new Date()};
  }
 ```
 *super的作用：在ES6中，在子类的constructor中必须先调用super才能引用this，super(props)的目的：在constructor中可以使用this.props*
 *借鉴: [http://www.cnblogs.com/SpiritWalker/p/7586617.html*

 ## 使用生命周期钩字
 componentDidMount() compoentWillUnmount()
 执行的顺序：
 1. 组件传递给reactDOM.redder(),调用构造函数，将里面的内容进行初始化，等待稍后更新
 2. 调用组建的render()方法，判断显示什么内容，然后react更新dom以匹配组建的渲染输出
 3. 输出组建插入到DOM中时，调用componentDidMount()生命周期钩子
 4. 组件通过tick函数对this.state进行更新（函数中有this.setState）,不断地更新DOM
 5. 当移除组件的时候react会调用componentWillUnmount()这个钩子函数，定时器被清除
   
   一般都是单向数据流
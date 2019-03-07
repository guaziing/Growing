### 关于line-height的问题
```htmlbars
<nav>
	<ul class="nav-top-right">
	        <li>
	          <div>
	            <img src="./imges/fanfan.jpg">
	          </div>
	        </li>
	        <li><a href="#">历史</a></li>
	        <li><a href="#">投稿</a></li>
	</ul>
<nav>
```
>1.当设置li设置line-height的时候如果里面的元素为block则line-height将不起作用
>2.当设置li中的元素浮动的时候line-height也将不起作用
>3.line-height只对行内元素起作用，当为li中包含的元素的display：inline-block的时候需要设置该元素vertical-align：middle（该属性定义了行内元素的基线相对于该元素所在行的基线的垂直对齐。）
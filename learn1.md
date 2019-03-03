# 课堂内容

## CSS盒模型

## 常见的块级元素和行内元素（div ul ol li dl dd p table h form   i b a img input span em）
### 块元素与行内元素区别
1）块级元素会独占一行，其宽度自动填满其父元素宽度
行内元素不会独占一行，相邻的行内元素会排列在同一行里，知道一行排不下，才会换行，其宽度随元素的内容         而变化
2） 块级元素可以设置 width, height属性，行内元素设置width,  height无效【注意：块级元素即使设置了宽度，仍然是独占一行的】
3) 块级元素可以设置margin 和 padding.  行内元素的水平方向的padding-left,padding-right,margin-left,margin-right 都产生边距效果，但是竖直方向的padding-top,padding-bottom,margin-top,margin-bottom都不会产生边距效果。（水平方向有效，竖直方向无效）
### 转换

## 浮动和清除浮动
1.添加一个标签其中的style样式这只位置为清除浮动
2.父级元素定义一个overflow：auto/hidden
3.:after

## 定位方式
absolute static realtive fixed 

## 常见的居中方式

## 语义化
新增的元素：
article aside(主内容之外的某些内容（比如侧栏）) details(查看隐藏细节与summary搭配) figcaption(对图片作解释) figure(与图片搭配的标题很常见。) footer header main mark nac progress section(节) summary(细节名字) time

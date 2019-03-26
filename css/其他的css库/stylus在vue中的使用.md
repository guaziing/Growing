# stylus在vue中的使用
**1.创建mixin.styl放函数**
> 函数中一般放的是代码段，这些函数在vue的css中可以被直接引用，减少了重复代码的书写
```css
border-1px($color)
  position: relative
//在其他地方的引用
.index
  .tab
    display: flex
    width: 100%
    height: 40px;
    line-height: 40px;
    border-1px(rgba(7, 17, 27, .1))
    // border-bottom: 1px solid rgba(7, 17, 27, .1)
    .tab-item
      flex: 1
      text-align: center
      a
        &.active
          color: rgb(240,20,20)
```
**2.对于stylus在组件的相关使用技巧**
**引入文件的时候：**
```css
@import "../../.styl"/
@import "~styles/.styl" //styles是在config文件的路径简写
```
**对于样式的穿透**
```htmlbars
<style lang="stylus"(说明采用的是stylus的配置) scoped(其中的内容只在该组件中有有用)>
.wrapper >>> .swiper-pagination-bullet-active
    background: white !important
// 解释：在.wrapper下面只要出现子组件.swiper-pagination-bullet-active都变成红色进行穿透，不受scoped的限制了
```
**对于副class**
```css
.icon
    display: inline-block
    width: 12px
    height: 12px
    margin-right: 4px
    background-size: 12px 12px
    bacground-repeat: no-repeat
    &.decrease   //表示icon外加的class
      background-image: url('./decrease.png')
    &.discount
      background-image: url('./discount.png')
    &.discount
      background-image: url('./discount.png')
```
**排列的文字和图片高度对齐**
```css
.icon
    display: inline-block
    width: 12px
    vertical-align: top
    height: 12px
    margin-right: 4px
    background-size: 12px 12px
    bacground-repeat: no-repeat
.text
    font-size: 10px
    color: white
    line-height: 12px
```
**3.建立varibles.styl**
为增强维护性将颜色等数据放在其他文件中：在src的assets的styles中创建文件varibles.styl
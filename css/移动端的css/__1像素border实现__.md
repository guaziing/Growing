# **1像素border实现**

**原因：**
> 在移动端border的1px不是1px，有一个概念dpr：物理像素是设备像素两倍（在phone6中看上去就像2px的border

**解决方案**

- 在项目中定义一个mixin.styl为css溢出容器提供一个方法，通过定义函数来解决
- 在mixin中设置after伪类，再进行缩放（全局定义class=>创建base.styl）


**代码**
```css
//mixin.styl
border-1px($color)
  position: relative
  &:after
    display: block
    position: absolute
    left: 0
    bottom: 0
    width: 100%
    border-top: 1px solid $color
    content: ' '
//base.styl
@media (-wekit-min-device-pixel-ratio: 1.5),(min-device-pixel-ratio: 1.5)
  .border-1px
    &::after
      -sebkit-transfrom: scaleY(0.7)
      transform: scaleY(0.7)
@media (-wekit-min-device-pixel-ratio: 2),(min-device-pixel-ratio: 2)
  .border-1px
    &::after
      -sebkit-transfrom: scaleY(0.5)
      transform: scaleY(0.5)
//
```

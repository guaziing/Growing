# css中的filter
filter的语法(不支持IE浏览器，浏览器要求比较高)
```css
filter: 滤镜名(参数值) 滤镜名(参数名)
//他的属性名（滤镜名）：

alpha：设置透明层次 | 
brightness(%) | 
contrast(%) 
blur(px)：创建高速度移动效果，即模糊效果 | 
chroma：制作专用颜色透明 | 
drop-shadow(h-shadow v-shadow blur spread color)：创建对象的固定影子 | 
FlipH：创建水平镜像图片 | 
FlipV：创建垂直镜像图片 | 
glow：加光辉在附近对象的边外 | 
gray：把图片灰度化 | invert：反色 | 
light：创建光源在对象上 | 
mask：创建透明掩膜在对象上 | 
shadow：创建偏移固定影子 | 
wave：波纹效果 | 
Xray：使对象变得像被x光照射一样
```
brightness:
> 给图片应用一种线性乘法，使其看起来更亮或更暗。如果值是0%，图像会全黑。值是100%，则图像无变化。其他的值对应线性乘数效果。值超过100%也是可以的，图像会比原来更亮。如果没有设定值，默认是1。
**contrast:**
> 调整图像的对比度。值是0%的话，图像会全黑。值是100%，图像不变。值可以超过100%，意味着会运用更低的对比。若没有设置值，默认是1。

*参考：[http://www.runoob.com/cssref/css3-pr-filter.html]*
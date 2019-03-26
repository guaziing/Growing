# css3中的动画
## **animation**
**属性:**
 >- animation-name(主要是为@keyframes动画对顶一个名称)
- animation-duration
- animation-delay
- animation-timing -function:( linear ease ease0-in ease-out ease-in-out cubic-bezier(n,n,n,n) ) 
- animation-iteration-count(规定动画应该播放的次数): 
- animation-direction(规定是否应该轮流反向播放动画):normal(altermate)
- animation-play-state: pause:(running,paused)

*语法：animation： name duration time-function delay iteratin-count direction*
**案例：**
```htmlbars
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>唱片播放</title>
  <style type="text/css">
    @keyframes myrotate {
      0% {
        transform: rotate(0deg);
      }
      100% {
        transform: rotate(360deg)
      }
    }
    .rotateCD-div {
      width: 200px;
      height: 200px;
      background: lightgrey;
      position: absolute;
      left: 0;
      bottom: 0;
      right: 0;
      top: 0;
      margin: auto;
    }
    .rotateCD-div .rotateCD {
      position: absolute;
      top: 0;
      bottom: 0;
      margin: auto;
      left: 0;
      right: 0;
      width: 150px;
      height: 150px;
      border-radius: 50%;
      background: no-repeat;
      background-size: cover;
      background-image: url(images/img-f4b787f45b170e9c9902857e2118fe6f.jpg);
      animation: myrotate 9s infinite linear;
    }
  </style>
</head>
<body>
  <div class="rotateCD-div">
    <div class="rotateCD-div1">
      <div class="rotateCD">
      </div>
    </div>
  </div>
</body>
</html>
```
## **@keyframes**
合法的值
> -  0-100%
- from（0%）
- to （100%）
*语法
@keyframes animationname {keyframes-selector {css-styles;}}*
**案例：**
```css
@keyframes mydemo {
    form {
        top: 0;
    }
    to {
        top: 50px;
    }
}
```
## **transform**
**属性：**

| 水果        | 价格    |  数量  |
| --------   | -----:   | :----: |
| 香蕉        | $1      |   5    |
| 苹果        | $1      |   6    |
| 草莓        | $1      |   7    |

| 属性  | 作用|
| --- | --- |
| matrix(n,n,n,n,n,n) |定义 2D 转换，使用六个值的矩阵|
|matrix3d(n,n,n,n,n,n,n,n,n,n,n,n,n,n,n,n) |定义 3D 转换，使用 16 个值的 4x4 矩阵|
|translate(x,y) |定义 2D 转换。|
|translate3d(x,y,z) |作用|
|translateX(x) |作用|
|translateY(y) |作用|
|translateZ(z) |作用|
|scale(x,y) |作用|
|scale3d(x,y,z) |作用|
|scaleX(x) |作用|
|scaleY(y) |作用|
|scaleZ(z) |作用|
|rotate(angle) |作用|
|rotate3d(x,y,z,angle)	 |作用|
|rotateX(angle) |作用|
|rotateY(angle) |作用|
|rotateZ(angle) |作用|
|skew(x-angle,y-angle) |作用|
|skewX(angle) |作用|
|skewY(angle) |作用|
|perspective(n) |作用|

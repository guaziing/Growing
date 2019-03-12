### 在HTML中引入iconfont
> 现在阿里巴巴中下载iconfont的包在将其包文件引入到css中,注意在html中用的时候要用class
 =“iconfont”才能设置相关的属性
```css
<style type="text/css">
@font-face {
    font-family: "iconfont";
    src: url('AmazeUI-2.7.2/fonts/iconfont.eot'); /* IE9*/
    src: url('AmazeUI-2.7.2/fonts/iconfont.eot#iefix') format('embedded-opentype'), /* IE6-IE8 */
    url('AmazeUI-2.7.2/fonts/iconfont.woff') format('woff'), /* chrome, firefox */
    url('AmazeUI-2.7.2/fonts/iconfont.ttf') format('truetype'), /* chrome, firefox, opera, Safari, Android, iOS 4.2+*/
    url('AmazeUI-2.7.2/fonts/iconfont.svg#iconfont') format('svg'); /* iOS 4.1- */
}

.iconfont {
    font-family: "iconfont" !important;
    font-size: 30px;
    font-style: normal;
    -webkit-font-smoothing: antialiased;
    -webkit-text-stroke-width: 0.2px;
    -moz-osx-font-smoothing: grayscale;
}
</style>
```
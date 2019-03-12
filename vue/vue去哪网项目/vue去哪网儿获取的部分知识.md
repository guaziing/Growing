### vue去哪网儿获取的部分知识
<router-link to="/List">列表页</router-link>：跳转页面

组件名HomeHeader在写标签时候可以是<home-header></>

子组件中的data的写法：
data () {return {}}
data: function() {return {}}

规定几个并排的带边框的框：：box-sizing: border-box （https://www.cnblogs.com/geyouneihan/p/9377204.html）

/....(表示根目录下的....)
》》》》》》》》》》》》》》》》
css的内容：
让多出的说明内容变成3个点： 
overflow: hidden
white-space: nowrap
text-overflow: ellipsis

宽高比例始终一致：
overflow: hidden
height: 0
width：100%；
padding-bottom：宽高的比例%（不能直接在height上面设置）


》》》》》》关于stylus（有关移动端的布局（rem））
对于stylus在组件中的限制：<style lang="stylus"(说明采用的是stylus的配置) scoped(其中的内容只在该组件中有有用)>

想要影响其他组件的样式（穿透样式）：
.wrapper >>> .swiper-pagination-bullet-active
    background: white !important
解释：在.wrapper下面只要出现子组件.swiper-pagination-bullet-active都变成红色进行穿透，不受scoped的限制了

rem：相对于html的font-size设置的像素的倍数

为增强维护性将颜色等数据放在其他文件中：在src的assets的styles中创建文件varibles.styl


》》》》》》》》》》》》》》关于js的补充内容
this.items.forEach(function(item, index){});（对数组（对象）进行循环）
Math.Floor(number)（取比较近的整数）

.then()(异步执行，就是当.then()前的方法执行完后再执行then()内部的程序，这样就避免了，数据没获取到等的问题)


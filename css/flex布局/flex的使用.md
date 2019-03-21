# flex的使用
> Flexbox布局最适合应用程序的组件和小规模的布局，而网格布局更适合那些更大规模的布局。著作权归作者所有。
商业转载请联系作者获得授权,非商业转载请注明出处。
原文: https://www.w3cplus.com/css3/a-guide-to-flexbox.html © w3cplus.com

### **属性**
> 1. **display: inline-flex || flex** (不定义flex-direction的话里面的元素都是横向排列的，行和块的区别)
2. **flex-direction: row | row-reverse | column | column-reverse**
3. **flex-wrap: nowrap | wrap | wrap-reverse**
4. **flex-flow: row wrap**
5. **justify-content: flex-start | flex-end | center | space-between(左右两边不留空隙，平均分配) | space-around(平均分配左右空隙)**
6. **align-content: flex-start | flex-end | center | space-between | space-around | stretch(垂直的justify-content)**
7. **align-item：flex-start | flex-end | center | baseline(伸缩项目根据他们的基线对齐) | stretch(伸缩项目拉伸填充整个伸缩容器)**
8. **flex-grow: <number> (默认值为： 0)**
*如果所有伸缩项目的“flex-grow”设置了“1”，那么每个伸缩项目将设置为一个大小相等的剩余空间。如果你给其中一个伸缩项目设置了“flex-grow”值为“2”，那么这个伸缩项目所占的剩余空间是其他伸缩项目所占剩余空间的两倍。著作权归作者所有。*
9. **flex-shrink: <number> (默认值为： 1)**（根据需要用来定义伸缩项目收缩的能力，同上）
10. **flex-basis：numpx**（这个用来设置伸缩基准值，剩余的空间按比率进行伸缩。）
11. **flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]**(缩写)
12. **align-self: auto | flex-start | flex-end | center | baseline | stretch**(就对于本身来说的，不影响其他的)
*以上参考： [https://www.w3cplus.com/css3/a-guide-to-flexbox.html]*
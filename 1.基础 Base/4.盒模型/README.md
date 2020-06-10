<!--
 * @abstract: JianJie
 * @version: 0.0.1
 * @Author: bhabgs
 * @Date: 2020-05-27 14:06:20
 * @LastEditors: bhabgs
 * @LastEditTime: 2020-06-08 20:22:17
-->

# 盒模型

> 所有 HTML 元素可以看作盒子，在 CSS 中，"box model"这一术语是用来设计和布局时使用。CSS 盒模型本质上是一个盒子，封装周围的 HTML 元素，它包括：边距，边框，填充，和实际内容。盒模型允许我们在其它元素和周围元素边框之间的空间放置元素。

- 下面的图片说明了盒子模型(Box Model)：

![img](http://public-1251206464.file.myqcloud.com/pub/1590993661500004.png)

> 盒模型分两种，一种标准盒模型，一种 IE 怪异盒模型，下面主要讲解标准盒模型！

## Q: 标准盒模型是什么样的

> 标准盒模型的可视宽高计算公式：
>
> **标准盒模型的可视宽高** = **border** + **padding** + **width/height（content）**

![img](http://public-1251206464.file.myqcloud.com/pub/1591614946636006.png)

### width 和 height 是什么?

> width 为元素的宽度 height 为元素的高度，只有块级元素能够设置狂傲属性，内联元素不具备宽高属性

### border 是做什么用的？[link](../7.边框%20Border/README.md)

### Q: padding 是内边距吗？

> padding 属性指定了盒的 padding 区的宽度。'padding'简写属性一次性设置四周的 padding，而其它 padding 属性只设置它们各侧的

### Q: margin 是外边距吧？

> margin 属性指定了盒的 margin 区的宽度。margin 简写属性一次性设置四周的 margin，而其它 margin 属性只设置它们各侧的。这些属性适用于所有元素，但非替换行内元素上的竖直 margin 将不会产生任何效果

## E: 练习题

### E: 1. 制作一个宽 100px 高 50px 内填充为 50px，左边距为 30px 的标准盒子

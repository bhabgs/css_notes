<!--
 * @abstract: JianJie
 * @version: 0.0.1
 * @Author: bhabgs
 * @Date: 2020-06-01 08:58:04
 * @LastEditors: bhabgs
 * @LastEditTime: 2020-06-01 08:58:20
-->

# border

> **border**，顾名思义 就是边框，为 html 元素定义该元素的边框样式粗细颜色等等。
>
> **border** 是一种 CSS 简写属性，一次性定义了常用的背景属性，包括 border-width, border-style, border-color。

---

## Q: 一、如何使用 border

### A: 1.想使用 border 我们首先讲一下 border 的常用语法

以下是 **border** 的常用属性：
| 属性值 | 默认值 | 说明 |
| ------------- | --------------------: | :------------------: |
| border-style | not specified | 指定要使用的边框演示 |
| border-width | medium | 指定要使用的边框宽度 |
| border-color | not specified | 指定要使用的边框颜色 |
| border-radius | 0 | 指定要使用的边框圆角 |
| border-image | none 100% 1 0 stretch | 指定使用图片绘制边框 |
| 。。。 | | |

> 前三个属性可以在一起使用，也可以单独使用。
> 比如我设置了 `border-style`, 又设置了 `border-width`

> **分别设置：**
>
> ```css
> border-style: solid;
> border-width: 1px;
> border-width: black;
> ```
>
> **组合设置(简写)**
>
> ```css
> border: solid 1px black;
> ```

## Q: 二、如何设置上下左右不同的边框

### A: 1.单独设置单个方向的边框

> ```css
> border-top: solid 1px red;
> border-bottom: dotted 1px black;
> ```

### A: 2.单独设置单个属性各个方向的边框

> ```css
> border-style: dotted solid double dashed;
> border-width: 1px 3px 2px;
> ```

**border-style 取值说明：**

1. dotted 点线;
2. solid 直线;
3. double 双线;
4. dashed 虚线

> 定义四个值：上-右-下-左
>
> 定义三个值：上-左右-下
>
> 定义两个值：上下-左右
>
> 定义一个值：上下左右
>
> border-radius: 右上-右下-左下-左上

## Q: 三、图片边框如何使用

### A: 1.border-image 的常用语法

以下是 **border-image** 的常用属性：
| 属性值 | 默认值 | 说明 |
| ------------------- | ------: | :------------------: |
| border-image-source | none | 图片的路径 |
| border-image-slice | 100% | 图片裁剪长度 |
| border-image-width | 1 | 边框背景宽度 |
| border-image-outset | 0 | 边框背景超出边框的量 |
| border-image-repeat | stretch | 图片重复性 |

**border-image-repeat 取值说明：**

1. repeat 重复;
2. round 平铺;
3. stretch 拉伸;

> 图片裁剪长度：将图片的上下左右裁减多少宽度作为边框的宽度，默认单位 px
>
> 边框背景宽度：设定绘制图片的区域宽度，如果大于或者小于图片的宽度，则会根据 border-image-repeat 进行绘制

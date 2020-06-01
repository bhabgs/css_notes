<!--
 * @abstract: JianJie
 * @version: 0.0.1
 * @Author: bhabgs
 * @Date: 2020-05-27 14:11:23
 * @LastEditors: bhabgs
 * @LastEditTime: 2020-05-28 21:06:13
-->

# Background

> **Background**，顾名思义 就是背景，为 html 元素定义该元素的背景属性与样式
>
> **Background** 是一种 CSS 简写属性，一次性定义了所有的背景属性，包括 color, image, origin 还有 size, repeat 方式等等。

---

## Q: 一、如何使用 background

### A: 1.想使用 Background 我们首先讲一下 Background 的常用语法

以下是 **Background** 的常用属性：
| 属性值 | 默认值 | 说明 |
| --------------------- | ----------: | :----------------------------------------------: |
| background-color | transparent | 指定要使用的背景颜色 |
| background-image | none | 指定要使用的一个或多个背景图像 |
| background-repeat | repeat | 指定如何重复背景图像 |
| background-attachment | scroll | 设置背景图像是否固定或者随着页面的其余部分滚动。 |
| background-position | 0%, 0% | 指定背景图像的位置 |
| background-size | auto | 指定背景图片的大小 |
| 。。。 | | |

> 以上这些属性可以在一起使用，也可以单独使用。
> 比如我设置了 `background-color`, 又设置了 `background-image`

> **分别设置：**
>
> ```css
> background-color: black;
> background-image: url(http://public-1251206464.file.myqcloud.com/pub/1590641816829002.jpg);
> ```
>
> **组合设置(简写)**
>
> ```css
> background: black url(http://public-1251206464.file.myqcloud.com/pub/1590641816829002.jpg);
> ```
>
> **还有几个高级属性会在 css3 进阶课程里讲述**

### A: 2.官方推荐书写顺序为

> `bg = background`

```css
bg: '';
bg-color: '';
bg-image: '';
bg-repeat: '';
bg-attachment: '';
bg-position: '';
```

建议书写顺序：

> `bg-color || bg-image || bg-position bg-size || bg-repeat || bg-attachment || bg-origin || bg-clip`

**注意**

1. 顺序并非固定
2. background-position 和 background-size 属性, 之间需使用/分隔, 且 position 值在前, size 值在后。

**示例**

```css
background: url(http://public-1251206464.file.myqcloud.com/pub/1590641816829002.jpg)
  10px 20px/100px no-repeat content-box;
```

### A: 3.[简单的背景属性](./example/base.html)

> 可以打开目录下的 `example.base.html`文件，通过 [chrome](https://www.google.cn/intl/zh-CN/chrome/) 浏览器下打开进行查看。

```html
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>背景色 基础样式</title>
  <style>
        .base {
          width: 100px;
          /*宽度100px*/
          height: 100px;
          /*高度100px*/
          background-color: black;
          /*背景色黑色*/
          background-image: url('
    http://public-1251206464.file.myqcloud.com/pub/1590641816829002.jpg);
          /*宽引用图片*/
          background-size: 50%;
          /*背景图片比例*/
          background-repeat: no-repeat;
          /*不重复*/
        }
  </style>
</head>

<body>
  <div class="base"></div>
</body>
```

## Q: 二、如何使用 `background-repeat`

### A: 1. `background-repeat` 属性用来设置背景图像的铺排填充方式, 默认值: `repeat`

**取值说明：**

1. repeat-x 表示横向上平铺, 相当于设置两个值 repeat no-reapeat;
2. repeat-y 表示纵向上平铺, 相当于设置两个值 no-repeat repeat;
3. repeat 表示横向纵向上均平铺;
4. no-repeat 表示不平铺;
5. round 表示背景图像自动缩放直到适应且填充满整个容器。 注意: 当设置为 round 时, background-size 的 cover 和 contain 属性失效。
6. space 表示背景图像以相同的间距平铺且填充满整个容器或某个方向. 注意: 当 background-size 设置为 cover 和 contain 时, background-rapeat 的 space 属性失效。

**注意：**

1. background-repeat 的 round/space 属性, 部分浏览器不支持。
2. 提供一个参数，则表明作用于两个方向；提供两个参数时，第一个作用于 x 轴，第二个作用于 y 轴

## Q: 三、`background-attachment` 是干什么的

### A: 1.`background-attachment` 属性用来设置背景图像是随对象内容滚动还是固定的，默认值 `scroll。`

**取值说明:**

1. `fixed` 背景图像相对窗体固定，即内容滚动时，图片不动;
2. `scroll` 相对元素固定，背景图像跟随元素本身，元素内容滚动时背景图像不动;
3. `local` 相对元素内容固定，背景图像跟随元素内容。

**注意：**

> 当元素设置`overflow: auto` 时，滚动的是元素的内容

1. `scroll` 属性值：背景图像跟随元素本身，元素本身没有滚动，所以背景图像不动;
2. `local` 属性值：背景图像相对元素内容固定，跟随元素的内容一起滚动。

## Q: 四、`background-position` 如何使用

### A: 1.background-position 属性用来设置背景图像的位置, 默认值: 0% 0%, 效果等同于 left top

**取值说明:**

1. 如果设置一个值, 则该值作用在横坐标上, 纵坐标默认为 50%(即 center) ;
2. 如果设置两个值, 则第一个值作用于横坐标, 第二个值作用于纵坐标, 取值可以是方位关键字[left\top\center\right\bottom], 如 `background-position: left center;` 也可以是百分比或长度, 百分比和长度可为设置为负值, 如: `background-position: 10% 30px ;`
3. css3 支持 3 个值或者 4 个值, 注意如果设置 3 个或 4 个值, 偏移量前必须有关键字, 如: `background-position: right 20px bottom 30px`;

**示例**

> 可使用 background-position-x 或 background-position-y 来分别设置横坐标或纵坐标的偏移量

```css
background-position: right 100px top 30px;
```

**注意：**

> 当使用 background-position-x 以及 background-position-y 时, 需考虑 火狐浏览器的 兼容性的问题

## Q: 五、`background-size` 如何使用

### A:1. background-size 属性用来指定背景图像的大小。默认值: auto

**取值说明:**

1. 可使用 长度值 或 百分比 指定背景图像的大小, 值不能为负值
   1. 设置一个值, 则用于定义图像的宽度, 图像的高度为默认值 auto, 且根据宽度进行等比例缩放;
   2. 设置两个值, 则分别作用于图像的宽和高。
2. auto 默认值, 即图像真实大小。
3. cover 将背景图像等比缩放到完全覆盖容器, 背景图像有可能超出容器。(即当较短的边等于容器的边时, 停止缩放)
4. contain 将背景图像等比缩放到宽度或高度与容器的宽度或高度相等, 背景图像始终被包含在容器内。(即当较长的边等于容器的边时, 停止缩放)

**示例**

```html
<style>
  .size {
    width: 800px;
  }

  .cover {
    background-size: cover;
  }

  .contain {
    background-repeat: no-repeat;
    background-size: contain;
  }
</style>
<body>
  <h1>size</h1>

  <div class="size cover base_bg"></div>
  <div class="size contain base_bg"></div>
</body>
```

## Q: 六、能设置多组背景图吗

> 当然可以，background 是一个复合属性, 可设置多组属性, 每组属性间使用逗号分隔, 其中背景颜色不能设置多个且只能放在最后一组。如设置的多组属性的背景图像之间存在重叠, 则前面的背景图像会覆盖在后面的背景图像上。

### A: 1. background 设置多组复合背景

**示例**

```html
<style>
  .composite {
    width: 800px;
    height: 800px;
    padding: 10px;
    background: url('http://public-1251206464.file.myqcloud.com/pub/1590641816829002.jpg')
        0% 0%/60px 60px no-repeat padding-box, url('http://public-1251206464.file.myqcloud.com/pub/1590641816829002.jpg')
        40px 10px/110px 110px no-repeat content-box,
      url('http://public-1251206464.file.myqcloud.com/pub/1590641816829002.jpg')
        140px 40px/200px 100px no-repeat content-box red;
  }
</style>
<body>
  <h1>多组复合属性</h1>
  <div class="composite"></div>
</body>
```

## E: 七、**练习题**

> img: http://public-1251206464.file.myqcloud.com/pub/1590641816829002.jpg

![img](http://public-1251206464.file.myqcloud.com/pub/1590641816829002.jpg)

```html
<style>
  .bg_box {
    width: 300px;
    height: 300px;
    background-image: url(http://public-1251206464.file.myqcloud.com/pub/1590641816829002.jpg);
  }
  .box_1 {
  }
  .box_2 {
  }
  .box_3 {
  }
  .box_4 {
  }
  .box_5 {
  }
</style>
<body>
  <h1>1.创建一个红色背景的盒子，给盒子添加背景图片居中显示在盒子内</h1>
  <div class="box_1 bg_box"></div>
  <h1>2.用简写的形式完成习题 1</h1>
  <div class="box_2 bg_box"></div>
  <h1>3.将图片平均分布在整个元素范围内</h1>
  <div class="box_3 bg_box"></div>
  <h1>4.使用 background 复合属在元素上设置多个背景</h1>
  <div class="box_4 bg_box"></div>
  <h1>5.课外拓展题，制作一个渐变色的背景</h1>
  <div class="box_5 bg_box"></div>
</body>
```

### E: 1.创建一个红色背景的盒子，给盒子添加背景图片居中显示在盒子内

### E: 2.习题 用简写的形式完成习题 1

### E: 3.将图片平均分布在整个元素范围内

### E: 4.使用 background 复合属性写法在元素上设置多个背景

### E: 5.课外拓展题，制作一个渐变色的背景

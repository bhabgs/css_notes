<!--
 * @abstract: JianJie
 * @version: 0.0.1
 * @Author: bhabgs
 * @Date: 2020-06-01 08:58:59
 * @LastEditors: bhabgs
 * @LastEditTime: 2020-06-16 13:43:32
-->

# 定位(position)

## Q: 什么是定位

### A: 文档流

> 在讲述定位前，我们现说一下文档流，文档流在我们讲(float)布局时已经接触到了一些。
> 简单说就是元素按照其在 HTML 中的位置顺序决定排布的过程。HTML 的布局机制就是用文档流模型的，即块元素（block）独占一行，内联元素（inline），不独占一行。
> 一般使用 margin 是用来隔开元素与元素的间距；padding 是用来隔开元素与内容的间隔。margin 用于布局分开元素使元素与元素互不相干；padding 用于元素与内容之间的间隔，让内容（文字）与（包裹）元素之间有一段“距离”。
> 只要不是 float 和绝对定位方式布局的，都在文档流里面。

**标准文档流示例**

```html
<div style="border:1px solid black">box1</div>
<div style="border:1px solid red">box2</div>
<img
  src="http://public-1251206464.file.myqcloud.com/pub/1590641816829002.jpg"
/>
```

## Q: 定位(position)是什么，它的属性有哪些

> position 属性用来指定一个元素在网页上的位置

1. `static` **默认**
2. `relative`
3. `fixed`
4. `absolute`
5. `sticky`

### A: **static**

> static 是 position 属性的默认值。如果省略 position 属性，浏览器就认为该元素是 static 定位。
> 该关键字指定元素使用正常的布局行为，即元素在文档常规流中当前的布局位置。此时 top, right, bottom, left 和 z-index 属性无效。

**示例**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>position - static</title>
    <style>
      .box {
        display: inline-block;
        width: 100px;
        height: 100px;
        background: red;
        color: white;
      }

      #two {
        position: static;
        top: 20px;
        left: 20px;
        background: blue;
      }
    </style>
  </head>
  <body>
    <div class="content">
      <div class="box" id="one">One</div>
      <div class="box" id="two">Two</div>
      <div class="box" id="three">Three</div>
      <div class="box" id="four">Four</div>
    </div>
  </body>
</html>
```

### A: **relative**

> relative 表示，相对于默认位置（即 static 时的位置）进行偏移，即定位基点是元素的默认位置。 它必须搭配 top、bottom、left、right 这四个属性一起使用，用来指定偏移的方向和距离。

**示例**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>position - relative</title>
    <style>
      .box {
        display: inline-block;
        width: 100px;
        height: 100px;
        background: red;
        color: white;
      }

      #two {
        position: relative;
        top: 20px;
        left: 20px;
        background: blue;
      }
    </style>
  </head>
  <body>
    <div class="content">
      <div class="box" id="one">One</div>
      <div class="box" id="two">Two</div>
      <div class="box" id="three">Three</div>
      <div class="box" id="four">Four</div>
    </div>
  </body>
</html>
```

### A: **fixed**

> fixed 表示，相对于视口（viewport，浏览器窗口）进行偏移，即定位基点是浏览器窗口。这会导致元素的位置不随页面滚动而变化，好像固定在网页上一样。
> 元素的位置通过 left、top、right 以及 bottom 属性进行规定。

**示例**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>position - fixed</title>
    <style>
      .content {
        width: 500px;
        height: 200px;
        overflow: scroll;
      }
      .header {
        width: 100%;
        height: 50px;
        background: red;
        color: white;
        position: fixed;
      }
      p {
        margin-top: 50px;
      }
    </style>
  </head>
  <body>
    <div class="content">
      <div class="header">Header</div>
      <div class="blank"></div>
      <p>
        我是内容~ <br />
        我是内容~ <br />
        我是内容~ <br />
        我是内容~ <br />
        我是内容~ <br />
        我是内容~ <br />
        我是内容~ <br />
        我是内容~ <br />
        我是内容~ <br />
        我是内容~ <br />
        我是内容~ <br />
        我是内容~ <br />
        我是内容~ <br />
        我是内容~ <br />
        我是内容~ <br />
        我是内容~ <br />
        我是内容~ <br />
      </p>
    </div>
  </body>
</html>
```

### A: **absolute**

> absolute 表示，相对于上级元素（一般是父元素）进行偏移，即定位基点是父元素。
> 它有一个重要的限制条件：定位基点（一般是父元素）不能是 static 定位，否则定位基点就会变成整个网页的根元素 html。
> 另外，absolute 定位也必须搭配 top、bottom、left、right 这四个属性一起使用。

**示例**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>position - absolute</title>
    <style>
      .content {
        margin-left: 100px;
        border: 2px solid blue;
      }
      .box {
        display: inline-block;
        width: 100px;
        height: 100px;
        background: red;
        color: white;
      }

      #two {
        position: absolute;
        top: 20px;
        left: 20px;
        background: blue;
      }
    </style>
  </head>
  <body>
    <div class="content">
      <div class="box" id="one">One</div>
      <div class="box" id="two">Two</div>
      <div class="box" id="three">Three</div>
      <div class="box" id="four">Four</div>
    </div>
  </body>
</html>
```

### A: **sticky**

> sticky 跟前面四个属性值都不一样，它会产生动态效果，很像 relative 和 fixed 的结合：一些时候是 relative 定位（定位基点是自身默认位置），另一些时候自动变成 fixed 定位（定位基点是视口）。比如型表格滚动的时候，表头始终固定。
> sticky 生效的前提是，必须搭配 top、bottom、left、right 这四个属性一起使用，不能省略，否则等同于 relative 定位，不产生"动态固定"的效果。原因是这四个属性用来定义"偏移距离"，浏览器把它当作 sticky 的生效门槛。

**示例**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>position - static</title>
    <style>
      * {
        box-sizing: border-box;
      }
      .content {
        width: 500px;
        height: 200px;
        overflow: scroll;
      }
      dl {
        margin: 0;
        padding: 24px 0 0 0;
      }
      dt {
        background: #b8c1c8;
        border-bottom: 1px solid #989ea4;
        border-top: 1px solid #717d85;
        color: #fff;
        margin: 0;
        padding: 2px 0 0 12px;
        position: -webkit-sticky;
        position: sticky;
        top: -1px;
      }
      dd {
        margin: 0;
        padding: 0 0 0 12px;
        white-space: nowrap;
      }
      dd + dd {
        border-top: 1px solid #ccc;
      }
    </style>
  </head>
  <body>
    <div class="content">
      <dl>
        <dt>A</dt>
        <dd>Andrew W.K.</dd>
        <dd>Apparat</dd>
        <dd>Arcade Fire</dd>
        <dd>At The Drive-In</dd>
        <dd>Aziz Ansari</dd>
      </dl>
      <dl>
        <dt>C</dt>
        <dd>Chromeo</dd>
        <dd>Common</dd>
        <dd>Converge</dd>
        <dd>Crystal Castles</dd>
        <dd>Cursive</dd>
      </dl>
      <dl>
        <dt>E</dt>
        <dd>Explosions In The Sky</dd>
      </dl>
      <dl>
        <dt>T</dt>
        <dd>Ted Leo & The Pharmacists</dd>
        <dd>T-Pain</dd>
        <dd>Thrice</dd>
        <dd>TV On The Radio</dd>
        <dd>Two Gallants</dd>
      </dl>
    </div>
  </body>
</html>
```

## E: 1. 创建两个盒子，一个盒子为父级，第二个盒子为子级，让**父级相对定位** 宽高分别为 500px、800px，让**子级绝对定位**并且距离左边 20px，距离顶部 90px

## E: 2.创建一个盒子，让该盒子的定位行为为`fixed`, 将 body 的高度设置成 5000px

<!--
 * @abstract: JianJie
 * @version: 0.0.1
 * @Author: bhabgs
 * @Date: 2020-05-27 14:14:32
 * @LastEditors: bhabgs
 * @LastEditTime: 2020-06-16 11:10:00
-->

# CSS 浮动布局-float

> 在接触界面布局后，浮动布局会是大家经常用到的属性，在好多排版布局中都是用到的浮动

## Q: 1. 什么是浮动

### A: 1.浮动(float)

> 浮动：使得元素脱离文档流，按照指定的方向(左或右发生移动)，直到它的边缘碰到包含框或另一个浮动框为止。

## Q: 2.浮动都有哪些属性

### A: 1.浮动的属性

> 1. `float:left;` 左浮动
> 2. `float:right;` 右浮动

### A: 2. 浮动代码例子

> ⚠️ 注意 html 内 css 代码, 复制代码到在线编辑器查看效果吧 😄

**不浮动**

```html
<style>
  .float {
    display: block;
    width: 100px;
    background: black;
  }
  .float1 {
    background: red;
  }
  .float2 {
    background: orange;
  }
  .float3 {
    background: blue;
  }
  .float4 {
    background: #ccc;
  }
</style>
<body>
  <div class="float">1</div>
  <div class="float1 float">2</div>
  <div class="float2 float">3</div>
  <div class="float3 float">4</div>
  <div class="float4 float">5</div>
</body>
```

**左浮动**

```html
<style>
  .float {
    float: left;
    width: 100px;
    background: black;
  }
  .float1 {
    background: red;
  }
  .float2 {
    background: orange;
  }
  .float3 {
    background: blue;
  }
  .float4 {
    background: #ccc;
  }
</style>
<body>
  <div class="float">1</div>
  <div class="float1 float">2</div>
  <div class="float2 float">3</div>
  <div class="float3 float">4</div>
  <div class="float4 float">5</div>
</body>
```

**右浮动**

```html
<style>
  .float {
    float: right;
    width: 100px;
    background: black;
  }
  .float1 {
    background: red;
  }
  .float2 {
    background: orange;
  }
  .float3 {
    background: blue;
  }
  .float4 {
    background: #ccc;
  }
</style>
<body>
  <div class="float">1</div>
  <div class="float1 float">2</div>
  <div class="float2 float">3</div>
  <div class="float3 float">4</div>
  <div class="float4 float">5</div>
</body>
```

## Q: 浮动会对文字产生影响吗

### A: 浮动后的特性

- 1.块级元素可以横排排列
- 2.行内元素可以设置宽和高
- 3.元素没有设置宽和高时，宽度为内容撑开宽
- 4.支持使用元素 margin
- 5.脱离文档流
- 6.不支持 margin：auto

## E: 1. 创建两个盒子，一个左浮动另一个右浮动

> 可查看本章例子

## E: 2. 创建一个盒子(不设置浮动属性)， 在该盒子内创建一个右浮动的盒子并在父级盒子内填满文字

> 查看浮动盒子的特性部分

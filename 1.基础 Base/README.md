<!--
 * @abstract: JianJie
 * @version: 0.0.1
 * @Author: bhabgs
 * @Date: 2020-05-30 10:41:29
 * @LastEditors: bhabgs
 * @LastEditTime: 2020-05-30 11:15:15
-->

# css3 基础前言

## Q: 什么是 css

> 层叠样式表(英文全称：Cascading Style Sheets)是一种用来表现 HTML（标准通用标记语言的一个应用）或 XML（标准通用标记语言的一个子集）等文件样式的计算机语言。CSS 不仅可以静态地修饰网页，还可以配合各种脚本语言动态地对网页各元素进行格式化。 CSS 能够对网页中元素位置的排版进行像素级精确控制，支持几乎所有的字体字号样式，拥有对网页对象和模型样式编辑的能力。

## Q: 如何使用 css

> css 使用有很多种方式（内嵌、内联、外联）
> 我们将 body 标签内的 h1 标签通过这三种方式分别设置成红色

### A: 1.内嵌

```html
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title>内嵌</title>
</head>
<body>
    <h1 style="color:red;">内嵌样式<h1>
</body>
<html
```

### A: 2.内联

```html
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title>内联</title>
    <style>
        h1{
            color:red;
        }
    </style>
</head>
<body>
    <h1>内联样式<h1>
</body>
</html>
```

### A: 外联

> 外联样式比较特殊需要创建一个文件

1. 创建 outreach.css

   ```css
   h1 {
     color: red;
   }
   ```

2. 在 html 文件内引入

   ```html
    <!DOCTYPE html>
    <html>
    <head lang="en">
        <meta charset="UTF-8">
        <title>外联</title>
        <link href='./outreach.css' />
    </head>
    <body>
        <h1>外联样式<h1>
    </body>
    </html>
   ```

## Q: 那如果同时设置了内嵌、内联、外联样式他们有什么优先顺序吗

### A: 1.他们的顺序分别是 `1-3` 由高到低 `1.内嵌 -> 2.内联 -> 3.外联`

a. 其中内联与外联有先后顺序，如下:

**示例 1**

> 如示例一所示，当内联样式引入方式高于外联样式，那么外联样式将会被覆盖

> **css:** outreach.css

```css
h1 {
  color: red;
}
```

> **html**

```html
    <!DOCTYPE html>
    <html>
    <head lang="en">
        <meta charset="UTF-8">
        <title>外联</title>
        <link href='./outreach.css' />
        <style>
            h1{
                color: black;
            }
        </style>
    </head>
    <body>
        <h1>外联样式<h1>
    </body>
    </html>
```

## E: 习题

### E: 1. 用外联样式设置 `body` 内的`div`元素背景色为黑色

### E: 2. 用外联样式覆盖内联样式，内联样式 `div`为绿色，外联样式`div` 橙色

> 参考示例一

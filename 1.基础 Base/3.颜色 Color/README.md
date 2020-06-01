<!--
 * @abstract: JianJie
 * @version: 0.0.1
 * @Author: bhabgs
 * @Date: 2020-05-30 17:00:37
 * @LastEditors: bhabgs
 * @LastEditTime: 2020-05-30 18:09:16
-->

# Color

> color 属性在 CSS 颜色中是比较常用的，本文将带你深入理解 color 属性的各个方面，包括它的语法、取值和作用。

## Q: 一、如何定义 color

> 能定义颜色的属性有很多种如; `文字颜色 color: red;`、`背景颜色: background: red;`、`边框颜色: border-color: red;`、`阴影颜色:box-shadow: 10px 10px 5px red`等。本章主要将文字颜色以及颜色的取值范围。

设置文本颜色

```html
<!DOCTYPE html>
<html lang="zh-CN">
  <head>
    <meta charset="utf-8" />
    <title>Title</title>
    <style>
      p {
        color: red;
      }
    </style>
  </head>
  <body>
    <p>
      设置文字为红色
    </p>
  </body>
</html>
```

## Q: 二、它都能识别什么样的颜色范围呢

> css 的 `color`属性能识别的颜色值有很多种在我们实际开发中大多数情况下会使用十六进制、RGB 与 RGBA 来实现各种颜色的需求。

1. **关键字颜色**
   如：
   `red`、`black`、`blue`
2. **十六进制颜色**
   如： `#FF0000`、(`#FFFFF`、简写`#FFF`)
3. **RGB 颜色**

\*RGB 代表光的三原色，Red、Green 和 Blue

如： `rgb(255,255,255)`

4. **RGBA 颜色**

\*`RGBA` 对比 RGB 多了一个透明度的值 也就是 RGBA 的第四个参数

如：`rgba(255,255,1, .3)`

5. **HSL**

> 1. **H（hue），表示色相**

- 取值范围是 0-360
- 0 和 360 是红色
- 30 是橙色
- 180 表示绿色
- 240 表示蓝色等等

> 2. **S（staturation），表示饱和度**

- 表示色彩的鲜艳成都
- 取值范围从 0%-100%
- 饱和度越高，颜色越鲜艳
- 完全不饱和的颜色没有色相

> 3.  **L（lightness），表示亮度**

- 控制色彩明暗变化
- 取值范围 0%-100%
  *数值越小，色彩越暗，越接近于黑色
  *数值越大，色彩越亮，越接近于白色

如：
`hsl（30, 100%，50%）`

1. **HSLa 和 RGBa 是一样的**

<!--
 * @abstract: JianJie
 * @version: 0.0.1
 * @Author: bhabgs
 * @Date: 2020-05-30 11:16:57
 * @LastEditors: bhabgs
 * @LastEditTime: 2020-05-30 12:22:24
-->

# Font

> 文字处理，是会在网页开发中经常遇到的知识点，通常我们会设置文字的`居中`、`行高`、`换行`。。。

## Q: 一、如何处理文字换行

> 我们开发网页开发中通常会使用`word-wrap：break-word;`和 `word-break：break-all;` 开控制文字的换行

**示例**

> **1:** word-wrap：break-word;

```css
.word_wrap{
    word-wrap：break-word;
}
```

> **2:** word-break：break-all;

```css
.word_wrap{
    word-break：break-all;
}
```

### Q: 1.他们有什么区别呢

> 如图 1 所示
>
> 第一行采用的是 `word-wrap：break-word;` 的方式进行换行处理，
>
> > **区别** word-wrap 先对行尾的单词进行换行，如果换行后单词的长度仍大于盒子的长度，则单词内换行；
>
> 第二行采用的是 `word-break：break-all;`
>
> > **区别** word-break 直接进行单词内换行

**图 1**
![img](http://public-1251206464.file.myqcloud.com/pub/1590809798019003.png)

## Q: 二、那怎样设置文字居中呢

> 文字居中有两个方向
>
> 1. 水平方向
> 2. 垂直方向
>
> 水平居中大多数情况采用 `text-align: center;`形式设置
>
> 单行文本垂直居中使用`line-height` 进行控制，多行文本垂直居中需要借助`flex`或者表格样式的方法来实现

**例子 1** 单行文本水平居中与垂直居中

css

```css
.text_center {
  height: 50px; /* 设置盒子高度 */
  text-align: center; /* 水平居中 */
  line-height: 50px; /* 根据盒子高度，将文字设置成垂直居中 */
}
```

**例子 2** 多行文本垂直居中

> 当然垂直居中的方法有很多中，后面的内容将会给大家一一呈现

css

```css
.span_box {
  display: table;
  height: 300px;
  border: 1px solid #ccc;
}
.words_span {
  display: table-cell;
  vertical-align: middle;
}
```

html

```html
<div class="span_box">
  <div class="words_span">
    多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本垂直居中
  </div>
</div>
```

## Q: 如果我设置的盒子比较小，文字有比较多的情况，怎样显示其他文字

> 这正情况，如果文字不是特别重要的，我们可以使用省略号的形式展示无法现实的文字，当然如果文字是特别重要的提示，我们还是要适当的加大盒子的大小或见效文字的大小来让文字全部展示出来

**示例 3** （文本溢出省略号处理方式）

css

```css
.ellipsis {
  width: 300px;
  height: 50px;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
```

html

```html
<div class="ellipsis">
  多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本多行文本文字溢出
</div>
```

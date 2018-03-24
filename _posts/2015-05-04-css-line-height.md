---
layout: post
title: "CSS <strong>行高</strong>"
subtitle: "For <strong>readibility</strong> concerns"
section: css
---


`line-height` 属性，可以用在块级元素上，顾名思义，就是 **每一行的高度**。

`line-height` 属性可以使用下面的单位：

* `px`
* `em`
* `%`
* 无单位, 比如 `1.5`


在没有单位的时候，它的工作原理类似百分比。比如 `150%` 和 `1.5` 是一样的。后者更实用可读。

### 为什么 line-height 非常重要


`line-height` 通过增加行间距，让你的文本更容易阅读。文本的大小影响可读性，建议使用相对与文本**动态**的值来设置行高，也就是无单位的值，不要使用`px`，因为使用px以后行高写死，如果字号变大，文字将会重叠。

In some cases, using `px` does come in handy (when you wish to vertically align text according to another element and not according to the font size).
{: .info}

当然 `px` 也是很有用的，比如说你想让一行文字对于整个块级元素上下居中，那么你可以设置行高为元素的高度。


Because using `%` or `em` values can have unexpected values, the recommended method is **unitless numbers**:

因为使用 `%` 或 `em` 的可能产生意想不到的效果，推荐使用 **无单位** 的值

* 在文章中，建议使用1.5倍行高
* 在文章标题中，建议使用1.2倍行高

```css
body{ font-size: 16px; line-height: 1.5;}
```

The computed line height will thus be 16 * 1.5 = `24px`.

通过计算，真是行高是 16 * 1.5 = `24px`

### Line-height 继承

Because the `line-height` property is inherited by the child elements, it will remain consistent no matter what `font-size` is subsequently applied.

行高是会被子元素继承的：

```css
body{ font-size: 16px; line-height: 1.5;}
blockquote{ font-size: 18px;}
```

`blockquote` 元素的行高会是 18*1.5 = `17px`

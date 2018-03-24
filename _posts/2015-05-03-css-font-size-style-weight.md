---
layout: post
title: "CSS <strong>字体属性</strong>"
subtitle: "字体的<strong>加粗</strong> 和 <em>斜体</em>"
section: css
---

### font-size

这个属性可以设置字体大小。

我们已经了解了 **[CSS 尺寸单位](/css-size-units.html)**，可以用于设置字体的大小。

```css
p{ font-size: 16px;}
```

字体设置为 `16px` 并不代表每个字都是 `16px`，具体的大小取决于字体的字体。

### font-style

这个属性可以把你的字体变成 _斜体_：

```css
h2{ font-style: italic;}
```

默认值是： `font-style: normal;`.

另外一个可选的值是 `oblique`，但是基本不用。

### font-weight

这个属性可以设置字体粗细：


```css
h2{ font-weight: bold;}
```

默认值是：`font-weight: normal;`.


根据字体所用的 `font-family`，这里的值可以设置成 `100` 到 `900`：

```css
font-weight: 100; /* Thin */
font-weight: 200; /* Extra Light */
font-weight: 300; /* Light */
font-weight: 400; /* 与 font-weight: normal; 相同 */
font-weight: 500; /* Medium */
font-weight: 600; /* Semi Bold */
font-weight: 700; /* 与 font-weight: bold; 相同 */
font-weight: 800; /* Extra Bold */
font-weight: 900; /* Ultra Bold */
```


很少有字体会支持所有的粗细程度。


### font-variant

This property turn your text into small caps:
这个可以将文本显示为小型大写字母

```css
h2{ font-variant: small-caps;}
```

默认值为：`font-variant: normal;`.

这个属性用的不多。

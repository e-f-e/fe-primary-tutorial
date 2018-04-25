---
layout: post
title: "HTML <strong>图片</strong>"
subtitle: "The major <strong>media</strong> on the Web"
section: html
---

**图片** 是第一个在网页上出现的非文本内容. 你电脑上大多数的图片类型都能在浏览器中显示： `.jpg`, `.gif` (可能是个动画), `.png` (可能存在透明色), `.bmp`...

### 语法

**图片** 使用 `<img>` 标签, 它是一个自闭和标签 (它只有开始标签).

`src` 属性定义图片的来源. 是一个连接, 你可以使用相对 URL 或者绝对 URL。

<ul class="files">
  <li>
    <i class="fa fa-folder-o"></i>
    my-first-website
    <ul>
      <li>
        <i class="fa fa-file-code-o"></i>
        home.html
      </li>
      <li>
        <i class="fa fa-image"></i>
        soyuz-spacecraft.jpg
      </li>
    </ul>
  </li>
</ul>

```html
<p>
  看这个热气球！
  <br>
  <img src="soyuz-spacecraft.jpg">
</p>
```

<div class="result">
  <p>
    看这个热气球！
    <br>
    <img src="/images/soyuz-spacecraft.jpg">
  </p>
</div>

### 尺寸

每个图片都有 **两个尺寸值**: **width** 和 **height**. 前面的图片宽 394 像素，高 248 像素。

> 当你将一张图片插入HTML的时候，你**不需要指定它的尺寸**：浏览器会自动根据他的**原始尺寸**展示出来。

### 块级还是行内

尽管一个图片有宽度和高度，并且它是一个大矩形，但是图片是一个 **行内元素**，不是一个块级元素。

为什么 `<img>` 元素是个**行内元素**呢？因为不能包含其他的HTML元素，所以被认为是行内元素，就像`<a>`，`<strong>` 或者 `<em>`。

这种行内元素可能会给你意想不到的展现效果：

```html
<p>
  There is a frog
  <img src="frog.jpg">
  in the middle of the paragraph!
</p>
```

<div class="result">
  <p>
    There is a frog
    <img src="/images/frog.jpg">
    in the middle of the paragraph!
  </p>
</div>
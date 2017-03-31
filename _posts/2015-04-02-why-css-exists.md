---
layout: post
title: "<strong>为什么</strong> 存在 CSS"
subtitle: "<strong>Separating</strong> content and styling"
section: css
---

随着 Web 在90年代的普及，Web 网页的设计水平也得到提升。 Web开发人员依靠特定的HTML标签来增强网页设计性：

* `<basefont>` 定义整个文档的字体
* `<font>` 给这个元素内的文字定义字体、颜色、字号
* `<center>` 将元素内容居中显示
* `<big>` 增大元素内文字的字号
* `<strike>` <strike> 给元素内文字增加删除线 <strike>

几个常用的 HTML 属性：

* `bgcolor` 给元素定义一个背景颜色
* `text` 定义元素内字体颜色
* 几个 `margin` 属性可以用来给元素周围添加编剧

### 为什么避免使用 表格 来布局

主要是因为，创建列可以直观的对齐元素，可以通过表格来控制两个内容之间的排列关系。Web 开发人员曾使用 `<table>` 元素去设计他们的网页，因为table可以提供一个天然的**网格**。

{% highlight html %}
<table>
  <thead>
    <tr>
      <th>Logo</th>
      <th colspan="2">Tagline</th>
    </tr>
  </thead>
  <tfoot>
    <tr>
      <th colspan="3">Copyright 2015</th>
    </tr>
  </tfoot>
  <tbody>
    <tr>
      <td>Left menu</td>
      <td>Main content</td>
      <td>Right sidebar</td>
    </tr>
  </tbody>
</table>
{% endhighlight %}

这种方法很麻烦，原因是：

* HTML 表格非常**臃肿**：他们需要大量的样板代码
* 使用这个标签在**语义**上是错误的： 表格是用来展示多维度数据的
* 修改布局需要修改标签：如果你想把左边的列移动到右边，你需要**修改HTML结构**
* 表格容易出现**语法错误**： 行和列需要非常有调理并且嵌套更加复杂
* 这个标签是**难阅读的**：表格的嵌套表格来给列中附加新的列

这就是为什么我们放弃使用表格布局并且使用CSS代替他的原因。

### CSS 是什么？

**CSS** 是 **C**ascading **S**tyle **S**heets 的简写。他的目的是_美化_标记语言（像 HTML 或 XML）。

CSS给HTML带来**生命**， 通过选择字体、修改颜色、定义边距、定位元素、动画交互等等。

### CSS 如何工作？

CSS 是如何**选取**一个HTML元素（像段落），选择一个需要修改的**属性**（像文字颜色），然后修改成一个**值**（像红色）的呢？

{% highlight css %}
p{ color: red;}
{% endhighlight %}

_"Style"_这个词存在欺骗性，你肯定觉得 CSS 只能用来修改文字颜色、大小、字体。但是CSS可以定义 HTML 文档的**布局**，通过高度，宽度，内外边距，和位置。
{: .info}

### CSS在哪里写

#### 将 CSS 作为属性

你可以直接把写 CSS 写在HTML元素内，通过元素的 `style` 属性。

{% highlight html %}
<p style="color: red;">这段文字很重要.</p>
{% endhighlight %}

#### 在 <head> 里写 CSS

你可以在 `<head>` 里 使用`<style>` 标签：

{% highlight html %}
<html>
  <head>
    <title>Hello World</title>
    <style type="text/css">
      p{ color: red;}
    </style>
  </head>
  <body>
    <p>这段文字是红色。</p>
  </body>
</html>
{% endhighlight %}

#### 将 CSS 写在单独的文件内

你可以讲 CSS 写在单独的以`.css`为扩展名的文件内，然后使用在HTML中 `<link>` 标签引入。

`style.css` 内容
{% highlight css %}
p{ color: red;}
{% endhighlight %}

{% highlight html %}
<html>
  <head>
    <title>Hello World</title>
    <link rel="stylesheet" type="text/css" href="style.css">
  </head>
  <body>
    <p>这段文字是红色的。</p>
  </body>
</html>
{% endhighlight %}

这是HTML文档“调用”了 CSS 文件，在这个例子中，一个HTML文档引入了同一目录下的 `style.css`。

在这**三个方法**中，我们首选第三种方法，外链 CSS 文件。

### 为什么不直接把 CSS 写在HTML中？

因为我们想把**内容**（HTML）和**样式**分开（CSS）。

如果你想了解更多这两种方式的区别，看这里[CSS Zen Garden](http://www.csszengarden.com/):each design uses the _exact_ same HTML but a _different_ CSS each time.

将 HTML 和 CSS 分开写更容易维护：相同的 CSS 可以用在整个网站。他更具有**灵活性**：一个专注于内容，另一个专注于样式。有利于SEO优化，还有个更多不同的目的。
---
layout: post
title: "A <strong>valid</strong> HTML document"
subtitle: "Some boilerplate"
section: html
---

直到现在，我们一直着眼于_孤立的_HTML代码片段。但是一个有效的**HTML文档**（或网页，同样的意思）需要一个具体的结构。

为什么我们关心一个HTML文档的有效性呢？

* **准确性**：一个有效的文档可以被浏览器正确地显示
* **可调试**：无效的HTML代码很难触发错误
* **可维护**：一个有效的文档以后很容易_升级_，即使是任何一个人

### 文档类型

第一个提供的信息是HTML文档的_类型_，我们称之为：**文档类型**

想象一下文档类型就像这些年的汽车系列：在1986年买的一辆福特嘉年华是嘉年华2系。假如今天你再买一辆，它是嘉年华7系。

过去常常有多个HTML版本共存（XHTML和HTML4.01已经完成标准化）。今天**HTML 5**是一种常态。

为了告诉浏览器一个HTML文档是HTML 5，只需让你的文档以下面的行开始：

{% highlight html %}
<!DOCTYPE html>
{% endhighlight %}

就是这样。只需设置它并且忘记它。

你可能想知道为什么一个HTML 5文档类型没有提到数字“5”。W3C认为以前的文档类型定义太复杂了，因此趁此机会通过移除任意的HTML版本号来简化它。
{: .info}

### <html>元素

除了文档类型行，你的**全部**文档必须被一个`<html>`元素包围：

{% highlight html %}
<!DOCTYPE html>
<html>
  <!-- The rest of your HTML code is here -->
</html>
{% endhighlight %}

`<html>`元素是所有HTML元素的**根节点**。

### <head>元素

同样的属性携带了HTML元素额外的信息，`<head>`元素携带的额外信息作用于 _整个_ 页面。

例如，页面**标题**（展示在标签页）位于`head`元素内：

{% highlight html %}
<head>
  <title>My fabulous blog</title>
</head>
{% endhighlight %}

其它的HTML元素可以出现在`<head>`中，并且 _只能_ 在`<head>`中：

* `<link>`
* `<meta>`
* `<style>`

### <body>元素

当`<head>`只包含在元信息里，并不意味着在任何地方展现（除了`<title>`之外），`<body>`元素是我们写入内容的地方。任何`<body>`_之内的_将要**展现**在浏览器窗口。

### 一个完整的可用的HTML文档

结合所有的需求，我们可以写一个简单的可用的HTML文档：

{% highlight html %}
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>MarkSheet</title>
    <meta name="description" content="A simple HTML and CSS tutorial">
  </head>
  <body>
    <p>Hello World!</p>
  </body>
</html>
{% endhighlight %}

如果你在浏览器预览这个示例，你将看到：

* _"MarkSheet"_ 显示在浏览器标签栏
* _"Hello World!"_ 是唯一显示在窗口的内容，因为它是唯一的内容在`<body>`_以内_。

<p><abbr title="World Wide Web Consortium">W3C</abbr>提供了一个<a href="http://validator.w3.org/#validate_by_input">标记验证服务</a>用于检查任何的HTML文档错误和警告。</p>
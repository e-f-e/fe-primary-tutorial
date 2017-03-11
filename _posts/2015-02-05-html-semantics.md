---
layout: post
title: "HTML <strong>Semantics</strong>"
subtitle: "HTML is about <strong>meaning</strong>"
section: html
---

HTML标签的作用是向文档传递一种 **含义** 。不必太在意你的页面看起来如何。重点关心你将使用的每一个标签。根据你写的内容，你可以选择适当的元素来匹配你要展示的文本的意思。
两个元素之间的 **距离** 是足够宽的的去容纳 **普通** 内容（像段落或列表）和更多的 **特殊** 内容像`<output>`（展示计算结果）或者`<progress>`（展示工作进度）。


### 结构元素：组织你的页面

结构元素允许你组织你页面的 **主要部分** ，它们通常包含其它的HTML元素。
这里展示一个典型的页面包括如下内容：

* `<header>` 在页面的 **第一个** 元素, 包含logo和标语
* `<nav>` 网站中跳转到其它页面的所有 **链接** 的列表
* `<h1>` 页面的标题
* `<article>` 页面的主要内容，像一篇博客
* `<footer>` 页面的 **最后** 一个元素，位于页面最底端


### 文本元素：定义你的内容

在结构元素的内部，你会发现 **文本元素** 对于定义你的页面内容是重要的。

你会主要使用如下：

* `<p>` 用来标记段落
* `<ul>` 用来标记无序列表
* `<ol>` 用来标记有序列表
* `<li>` 用来标记(有序或无序)列表中的列表项
* `<blockquote>` 用来标记引用


### 内联元素：区分你的文本

有一段文本很长，但是有不同的内容，**内联** 元素就可以让你 **区分** 出这部分不同的内容。

可用的内联元素有好多，但是你通常会遇到如下几种：

<ul>
  <li><code>&lt;strong&gt;</code> <strong>重要</strong>单词</li>
  <li><code>&lt;em&gt;</code> <em>强调</em>单词</li>
  <li><code>&lt;a&gt;</code> <a href="#">表示超链接</a></li>
  <li><code>&lt;small&gt;</code> <small>次要</small> 单词</li>
  <li><code>&lt;abbr&gt;</code> 像<abbr>W3C</abbr>这样的缩写词</li>
</ul>

<aside class="comments">
  读完这段HTML代码，你就会很容易的理解每个<strong>HTML元素</strong>的含义了，加油↖(^ω^)↗。
</aside>

{% highlight html %}
<article>
  <h1>Main title of the page</h1>
  <h2>A subtitle</h2>
  <p>
    Something something an other stuff and some <em>emphasis</em> and even <strong>important</strong> words.
  </p>
  <p>
    Another paragraph.
  </p>
  <ul>
    <li>One</li>
    <li>Two</li>
    <li>Three</li>
  </ul>
  <blockquote>
    Once said
  </blockquote>
</article>
<aside>
  <h3>My latest posts</h3>
  <ul>
    <li><a href="#">One</a></li>
    <li><a href="#">One</a></li>
    <li><a href="#">One</a></li>
  </ul>
</aside>
{% endhighlight %}


### 通用元素

当没有语义元素适合你的内容，但是你仍然想插入一个HTML元素（归类内容或给内容添加样式），你可以选择一个**通用**元素：

* `<div>` 块级元素
* `<span>` 内联元素

虽然这些HTML元素没有实际含义，但它们会让我们使用CSS样式变得方便。


### 不要考虑太多的语义

这里有[100个 HTML元素](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)可供选择，那会有很多的元素，但是已做了分类整理供你选择适合你展示内容使用的标签。
不要花费太多的时间去担心这些，如果你坚持看完以下列表中的元素并写测试代码执行，那会有助于你很好的掌握本节的内容。

<div class="table">
  <table>
    <tr>
      <th>Structure</th>
      <th>Text</th>
      <th>Inline</th>
    </tr>
    <tr>
      <td>
        <code>header</code><br>
        <code>h1</code><br>
        <code>h2</code><br>
        <code>h3</code><br>
        <code>nav</code><br>
        <code>footer</code><br>
        <code>article</code><br>
        <code>section</code>
      </td>
      <td>
        <code>p</code><br>
        <code>ul</code><br>
        <code>ol</code><br>
        <code>li</code><br>
        <code>blockquote</code>
      </td>
      <td>
        <code>a</code><br>
        <code>strong</code><br>
        <code>em</code><br>
        <code>q</code><br>
        <code>abbr</code><br>
        <code>small</code>
      </td>
    </tr>
  </table>
</div>

*[W3C]: 万维网联盟
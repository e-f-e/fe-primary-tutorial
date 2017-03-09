---
layout: post
title: "HTML <strong>Block</strong> and <strong>Inline</strong>"
subtitle: "HTML has 2 main <strong>types</strong> of elements"
section: html
---



在HTML中，主要有两种HTML元素。

* **块级** 元素：

    * 段落： `<p>`
    * 列表： 有序列表 `<ul>`、无序列表`<ol>`
    * 标题：`<h1>` 到 `<h6>`

* **内联** 元素：

    * 像 `<a>`
    * 强调 `<em>`
    * 语气更强的强调 `<strong>`
    * 短的引用 `<q>`
    * 缩写 `<attr>`


**块级** 元素可以通过将你的页面内容清晰的划分为多个部分。

**内联** 元素用来指定页面中有特殊意义的词语，给予词语一定的意义和功能，一般内联元素只用来包括一个或几个词语。

{% highlight html %}
<p>你有没有在知乎上订阅 <a href="https://zhuanlan.zhihu.com/future-fe">挨踢路透社</a> 的专栏?</p>
{% endhighlight %}



### Opening and closing tags

### 开始和闭合标签

**所有** 块级元素都有开始和闭合标签

因此，自闭和元素是行内元素，仅仅是因为他们的语法不允许他们包含其他的HTML元素。

<div class="table">
  <table>
    <tr>
      <th class="empty"></th>
      <th>有开始和闭合标签</th>
      <th>自闭和元素</th>
    </tr>
    <tr>
      <th>块级元素</th>
      <td>
        <code>&lt;p&gt;</code>
        <code>&lt;/p&gt;</code>
        <br>
        <code>&lt;ul&gt;</code>
        <code>&lt;/ul&gt;</code>
        <br>
        <code>&lt;ol&gt;</code>
        <code>&lt;/ol&gt;</code>
      </td>
      <td>
        <strong>木有</strong>
      </td>
    </tr>
    <tr>
      <th>内联元素</th>
      <td>
        <code>&lt;a&gt;</code>
        <code>&lt;/a&gt;</code>
        <br>
        <code>&lt;strong&gt;</code>
        <code>&lt;/strong&gt;</code>
        <br>
        <code>&lt;em&gt;</code>
        <code>&lt;/em&gt;</code>
      </td>
      <td>
        <code>&lt;input&gt;</code>
        <br>
        <code>&lt;br&gt;</code>
        <br>
        <code>&lt;img&gt;</code>
      </td>
    </tr>
  </table>
</div>


### 其他类型的HTML元素


这里有几个特殊的元素，虽然比较特殊但你会经常遇到它们：


* **列表项**  `<li>`
* **表格**, **表格行**, **表格列** 分别是 `<table>`, `<tr>` 和 `<td>`

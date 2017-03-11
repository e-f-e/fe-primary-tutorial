---
layout: post
title: "HTML <strong>Links</strong>"
subtitle: "The <strong>core</strong> of the Web"
section: html
---

**链接**是HTML中必不可少的, 当网站一开始被设计用作文档信息网络时，**链接**无处不在。

_“超文本”_是HTML的一部分，定义了我们使用链接的方式：_超文本_链接，又称为**超链接**。

在HTML中，链接是**内联元素**，写做`<a>`标签。

`href` 属性（超文本引用）用于定义链接的 **目标** （跳转到你点击的地址）。

{% highlight html %}
<p>
  如果你想要搜索某个东西，请访问谷歌 <a href="http://www.google.com">Google</a>.
</p>
{% endhighlight %}

<div class="result">
  <p>
    如果你想要搜索某个东西，请访问谷歌 <a href="http://www.google.com">Google</a>.
  </p>
</div>

链接是**主要的**网页交互：通过点击链接实现从一个网页到另一个网页的浏览。

有**3**种类型的跳转目标可以定义。

* **锚点**目标, 用于浏览_同一个页面_的内容
* **相对的**URL，通常用于浏览_同一网站_内的内容
* **绝对的**URL, 通常用于浏览_不同的_网站

### 锚点目标

**锚点**目标用于浏览**同一**页面_以内_的内容。通过在你的超链接中加入`#`前缀，你可以跳转到一个使用`id`属性定义的HTML元素。

例如，`<a href="#footer">`将要跳转到当前HTML内的`<div id="footer">`元素。这一类的超链接通常用于跳转到页面的顶部。

### 相对的URL

如果你想要定义一个跳转到_同一_网站内其它页面的链接，你可以使用**相对的**URL。

但是相对于是什么呢？相对于**当前的页面**。

让我们使用一个简单的示例，`my-first-website`目录下包含2个HTML文件：

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
        <i class="fa fa-file-code-o"></i>
        contact.html
      </li>
    </ul>
  </li>
</ul>

在`home.html`中，你可以定义一个链接指向`contact.html`。

当这两个文件**在同一个文件夹内**，你可以简单的写成`home.html`：

{% highlight html %}
<p>
  跳转到<a href="contact.html">联系人页面</a>.
</p>
{% endhighlight %}

<div class="result">
  <p>
    跳转到 <a href="contact.html">联系人页面</a>.
  </p>
</div>

在一个实际的网站中，这个过程是相似的。

假如你有一个网站叫`http://ireallylovecats.com`，其中有两个页面：`index.html`和`gallery.html`：

<ul class="files">
  <li>
    <i class="fa fa-folder-o"></i>
    ireallylovecats.com
    <ul>
      <li>
        <i class="fa fa-file-code-o"></i>
        index.html
      </li>
      <li>
        <i class="fa fa-file-code-o"></i>
        gallery.html
      </li>
    </ul>
  </li>
</ul>

在`index.html`页面你可以写入如下链接：

{% highlight html %}
<p>
  请访问<a href="gallery.html">Gallery</a>!
</p>
{% endhighlight %}

记住：网站就存在于我们通常使用的**电脑**中。它们被称为**“服务器”**，因为它们唯一的目的是用作网站主机。但是它们像“常规的”电脑一样仍然有**文件**和**文件夹**。

{: .info}

### 绝对的URL

如果你想要和朋友分享你的猫相册，你不能只发送`gallery.html`页面给他，因为这类**相对的**地址只能服务同一**电脑**或者同一**域名**下的HTML文档。

你的HTML文档需要_完整的_URL：`http://ireallylovecats.com/gallery.html`。

这个URL可以被分为3部分：

* **协议** `http://`
* **域名** `ireallylovecats.com`
* **文件路径** `gallery.html`

**绝对的URL**是**无依赖的**：无论你在哪里使用链接，它都能在正确的域名和协议下找到正确的文件，因为它包含_全部的_必要信息。

你通常使用绝对的URL定义一个从_你的_网站到_另一个_网站的链接。

在你的`http://ireallylovecats.com/gallery.html`文件中，你可以这样写：

{% highlight html %}
<p>
  找到更多关于猫的图片<a href="https://twitter.com/ireallylovecats">Twitter账户</a>!
</p>
{% endhighlight %}

### 使用相对的还是绝对的链接？

假设你想要从第一个目标链接到第二个目标，最直接的方法是使用绝对的URL。因此你可以在你的`index.html`文件中添加：`<a href="http://ireallylovecats.com/gallery.html">跳转到第二个页面</a>`。

如果两个文件在同一个目录下，你可以使用**相对的**URL：`<a href="first-blog-post.html">`。这很有用，假如你决定移动你的目录：这样你的链接不会受到破坏，因为链接目标相对位置没有变，只要你同时移动所有的文件并且保持它们都在同一个目录下。这种相对的方式在切换域名时特别有用。

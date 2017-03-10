---
layout: post
title: "HTML <strong>Links</strong>"
subtitle: "The <strong>core</strong> of the Web"
section: html
---

**链接** 是网页中必不可少的, 当网站一开始被设计用作文档信息网络时，**链接** 无处不在。

_“超文本”_ 是网页的一部分，定义了我们使用链接的方式： _超文本_ 链接, 又称为 **超链接**。

在网页中， 链接是 **内联元素** ，写做 `<a>` 标签。

`href` 属性（超文本引用）用于定义链接的 **目标** （跳转到你点击的地址）。

{% highlight html %}
<p>
  如果你想要搜索某个东西，请访问谷歌 <a href="http://www.google.com">Google</a>.
</p>
{% endhighlight %}

<div class="result">
  <p>
    To search for something, visit <a href="http://www.google.com">Google</a>.
  </p>
</div>

链接是 **主要的** 页面交互：你从一个网页浏览到另一个网页，通过点击链接完成跳转。

有 **3** 种类型的跳转目标可以定义。

* **锚点** 目标, 用于浏览 _同一个页面_ 的内容
* **相对的** 网址，通常用于浏览 _同一网站_ 内的内容
* **绝对的** 网址, 通常用于浏览 _另一个_ 网站

### 锚点 目标

**锚点** 目标用于浏览 **同一** 页面 _以内_ 的内容。通过在你的超链接中加入`#`前缀，你可以跳转到一个使用`id`定义的网页元素。

例如，`<a href="#footer">` 将要跳转到当前页面内的`<div id="footer">`元素。这种类型的超链接通常用于跳转到页面的顶部。

### 相对的 网址

如果你想要定义一个跳转到 _同一_ 网站内其它页面的链接，你可以使用 **相对的** 网址。

但是相对于是什么呢？相对于 **当前的页面**。

让我们使用一个简单的示例，`我的第一个网站`目录下包含2个网页：

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

In `home.html`, you want to define a link to `contact.html`.

As the two files are **in the same folder**, you can simply write in `home.html`:

{% highlight html %}
<p>
  Go to the <a href="contact.html">contact page</a>.
</p>
{% endhighlight %}

<div class="result">
  <p>
    Go to the <a href="contact.html">contact page</a>.
  </p>
</div>

On an actual website, the process is similar.

Let's say you have a website called `http://ireallylovecats.com` on which you have 2 webpages: `index.html` and `gallery.html`:

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

In `index.html` you could write the following link:

{% highlight html %}
<p>
  Visit the <a href="gallery.html">Gallery</a>!
</p>
{% endhighlight %}

Remember: websites are hosted on **computers** just like the one you're currently using. They are simply called **"servers"** because their sole purpose is to host websites. But they still have **files** and **folders** like "regular" computers.
{: .info}

### Absolute URLs

If you wanted to share your cats gallery with a friend, you wouldn't be able to just send `gallery.html`, as this **relative** URL only works for HTML documents that are on the same **computer** or same **domain**.

You need the _complete_ URL to your HTML document: `http://ireallylovecats.com/gallery.html`.

This URL can be segmented in 3 parts:

* **protocol** `http://`
* **domain** `ireallylovecats.com`
* **file path** `gallery.html`

This **absolute URL** is **self-sufficient**: no matter where you use the link form, it contains _all_ the information required to find the correct file, on the correct domain, with the correct protocol.

You usually use absolute URLs defining a link from _your_ website to _another_ website.

In your `http://ireallylovecats.com/gallery.html` file, you could write:

{% highlight html %}
<p>
  Find more images of my cats on my <a href="https://twitter.com/ireallylovecats">Twitter account</a>!
</p>
{% endhighlight %}

### Relative or absolute links?

Let's say you want to link from the first to the second. The most direct approach is to use the absolute URL. So you add `<a href="http://ireallylovecats.com/gallery.html">Go the second page</a>` in your `index.html` file.

Because the two files are in the same directory, you could use the **relative** URL by using `<a href="first-blog-post.html">`. This is useful if you decide to move your directory: your links won't be broken because the link targets are relative to each other, as long as you move both files simultaneously and keep them in the same directory. This relative approach is particularly useful when switching domains.

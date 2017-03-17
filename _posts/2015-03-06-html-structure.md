---
layout: post
title: "HTML <strong>结构</strong>"
subtitle: "To <strong>organize</strong> the <strong>main</strong> parts of your webpage"
section: html
---


编写HTML代码的时候，经常会写一些段落、列表、链接，一般都是给_文本_赋予一些**含义**。但是怎么才能把分组呢?



举个例子，一个博客的页面可以被分成四个部分：

* 头部，一个网站的每一个页面可能都会有一个共同的头部，上面有这个网站的导航。
* 主体部分，每一个页面的主体部分可能不一样，可能是文章列表，也可能是一篇文章和评论，或者一个介绍页面。
* 侧边，防止一些归档或者栏目供访客选择。
* 底部，添加一些友情链接、版权以及网站其它不重要的页面。

这里有一些**结构化页面的HTML元素**可供选择，用来当做其它元素的**容器**


### Header

`header` 通常是HTML文档中的 **第一个** HTML元素，它的作用是为网站提供一些**介绍**，可能包括Logo、标语、导航链接等。

{% highlight html %}
<header>
  <p>
    <a>
      <img src="my-logo.jpg" alt="Tibitaco logo">
    </a>
    <em>A cool website</em>
  </p>
  <ul>
    <li>
      <a href="home.html">Home</a>
      <a href="about.html">About</a>
      <a href="contact.html">Contact</a>
    </li>
  </ul>
</header>
{% endhighlight %}

### Footer

和 `header` 相反， `footer`，通常是**最后一个**元素，这里可能把重要的导航重新展示一次，或者添加一些次要的内容。


{% highlight html %}
<footer>
  <p>MarkSheet.io | Copyright 2015</p>
  <ul>
    <li>
      <a href="home.html">Home</a>
    </li>
    <li>
      <a href="about.html">About</a>
    </li>
    <li>
      <a href="contact.html">Contact</a>
    </li>
  </ul>
  <ul>
    <li>
      <a href="privacy-policy.html">Privacy Policy</a>
    </li>
    <li>
      <a href="terms-of-use.html">Terms of use</a>
    </li>
  </ul>
</footer>
{% endhighlight %}

### Main

`main`元素，顾名思义，**这个页面中最重要的内容**，这里定义这个页面的主要目的。

所有的页面都包括一些公共的元素（比如 header、nav、footer）,但是`main`元素内的内容在该网站下是**唯一**的。

例如，你现在阅读的内容呈现在`main`元素内，这个内容在这个网站是独一无二的。

### Aside


`aside` 元素通常在 `main`的旁边来补充一些与主要内容相关的_额外_的信息。


### Section

### Section

`section` 元素 可以用来给内容 **分组**


Sections 并没有什么特殊含义。它通常是_连接它的子元素_，形成页面中的一个分组。


The [Fe Primary Tutorial](http://fe-primary-tutorial.itlutoushe.com/) 有3个 Section:

* **头部** (标题)
* **简介** (_"短"_, _"简单"_)
* **章节** (_"Web"_, _"HTML"_, _"CSS"_)

它们都包含在`main`元素里面，但是它们按照有逻辑的将页面按照内容分割成了几个组，让页面更加结构化。



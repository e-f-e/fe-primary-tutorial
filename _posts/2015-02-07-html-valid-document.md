---
layout: post
title: "一个 <strong>合法的</strong> HTML 文档"
subtitle: "Some boilerplate"
section: html
---

直到这里，我们看到的都是一些代码片段，**HTML 文档** 需要包含一套具体的结构才会**合法**。

为什么我们要关注HTML文档的合法性？

* **正确**：一个合法的HTML文档会被浏览器_正确显示_
* **易调试**：不合法的HTML代码容易产生Bug并且不好调试
* **可维护**：一个合法的HTML文档更容易被_更新_，多人协作也不会有问题

### Doctype


第一个需要提供的信息是HTML的文档_类型_，我们需要：**Doctype**。


你可以把**Doctype**看成Iphone手机的版本，10年大家买的都是Iphone4, 17年大家都买Iphone8了。


曾经HTML有很多的版本（XHTML和HTML 4.01 一直是标准），现在**HTML 5*是最新规范。



告诉浏览器HTML文档的版本是HTML 5，你仅需要在文档的开头第一行写：

{% highlight html %}
<!DOCTYPE html>
{% endhighlight %}


就酱紫。


你一定奇怪为什么HTML 5的 Doctype 里面没有 “5”，W3C觉得以前的版本太混乱了，就趁这个机会把它变得简单了，所以移除了 Doctype 里的所有版本号。
{: .info}

### <html> 元素


除了 Doctype ，**所有**的HTML必须在`<html>`元素内：

{% highlight html %}
<!DOCTYPE html>
<html>
  <!-- The rest of your HTML code is here -->
</html>
{% endhighlight %}


`<html>` 是所有HTML元素的**祖先**元素。

### <head>


我们需要给HTML文档添加一些附加信息，`<head>`元素就是为了给**整个**网页添加属性。



比如，页面的**标题**就是在`<header>`内：


{% highlight html %}
<head>
  <title>My fabulous blog</title>
</head>
{% endhighlight %}


其他HTML元素可以并**只能**写在`<head>`内。

* `<link>`
* `<meta>`
* `<style>`

### <body>


而`<head>`只包含元数据，而不是在任何地方显示（除了`<title>`），`<body>`元素是我们写页面内容的地方。 在浏览器中，包含在`<body>`会被**显示**。


### 一个完整合法的HTML文档


结合上面所有的信息，我们写一个简单的合法的HTML文档。

{% highlight html %}
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>挨踢路透社</title>
    <meta name="description" content="挨踢路透社 Future FE!">
  </head>
  <body>
    <p>Future FE!</p>
  </body>
</html>
{% endhighlight %}

如果你在浏览器中查看你将会看到：

* _"挨踢路透社"_ 被展示在了浏览器的tab标签上
* _"Future Fe!"_ 只有这一串文字被展示在了页面上，因为`<body>`标签中只写了这些内容。


<p> <abbr title="World Wide Web Consortium">W3C</abbr> 提供了一个 <a href="http://validator.w3.org/#validate_by_input">Markup Validation Service</a>来检查HTML文档合法性</p>
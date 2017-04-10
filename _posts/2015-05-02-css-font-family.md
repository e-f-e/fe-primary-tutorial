---
layout: post
title: "CSS <strong>字体</strong>"
subtitle: "Choosing a <strong>font</strong>"
section: css
---

CSS 提供了几个影响文本渲染的 **font** 属性。`font-family`属性定义文本的字体。

### 通用字体

有五个通用的字体：

* `serif` 衬线字体
* `sans-serif` 非衬线字体
* `monospace`
* `cursive`
* `fantasy`

`cursive` 和 `fantasy` 基本不会被用到。
{: .info}

因为 `font-family` 是可以被子元素继承的，所以你可以给整个 HTML 文档内容的祖先元素设置字体：给 `<body>` 元素设置字体。

{% highlight css %}
body{ font-family: sans-serif;}
{% endhighlight %}

根据这个 CSS 规则，这个网页将会使用 **sans-serif** 作为首选字体。

### Web安全字体

使用通用字体名称的问题是，你的网页的设计将依赖用户在其设置中设置的字体。

你很可能想让你的网页在每个人的技术机上看起来一致，所以你需要**明确**你使用的字体。因此，你只需使用字体的**名字**。

{% highlight css %}
body{ font-family: Arial;}
{% endhighlight %}

你的网页将使用 Arial **只要它被安装在用户的计算机上**。如果 Arial 没有被安装在用户的计算机上，它将自动使用浏览器的默认衬线字体（通常是这样）。

Arial 是一个安全的选项，因为它被安装在所有的 Windows 、Mac 计算机以及大多数的Linux系统上。所以 Arial 被称作是 **web安全** 字体：你可以安全的在 CSS 中使用这些字体，因为大多数用户的电脑上都安装了这些字体。


这里有**9**个web安全字体：

* Arial
* Arial Black
* Comic Sans MS
* Courier New
* Georgia
* Impact
* Times New Roman
* Trebuchet MS
* Verdana

### 定义一个字体列表

虽然使用使用_这些_ `font-family` 属性是安全的，你可以定义 **fallback**（这个的确不知道咋翻译，反正就是备胎的意思） 通过写**一组字体**。

{% highlight css %}
body{ font-family: Arial, Verdana, sans-serif;}
{% endhighlight %}

通过给 `font-family` 定义**多个值**，浏览器可以找到第一个值 `Arial` 并且使用它，如果它不能被使用，浏览器将会去使用 `Verdana`，以此类推。直到找到一个可以用的字体，如果前面两个字体都不能用，那么只能使用 sans-serif 了。

最佳实践是使用一个**通用字体**来作为最后一个值。如果你不定义一些明确的字体，你可以定义你想要的字体类型。

因为设计师想使用更贴合主题的字体，但是又想让所有的用户看到的页面保持一致，所以可能需要在网页中引入一个字体。这样，它们确保了字体可用，即使不在用户的计算机上，但也能被显示出来，因为网站提供了这个字体。

我们需要查看 `@font-face` 事件，看看 Google Fonts 和 Typekit 这些服务可以帮助你。
---
layout: post
title: "CSS <strong>继承</strong>"
subtitle: "Using the HTML <strong>hierarchy</strong>"
section: css
---

假如我们想修改网页的**文字颜色**，为_每一个_ HTML 元素指定颜色是相当没意思的。

{% highlight css %}
p,
ul,
ol,
li,
h1,
h2,
h3,
h4,
h5,
h6{ color: grey;}
{% endhighlight %}

### 值的传递

文字颜色 `color` 的值可以继承他的**祖先元素**的。考虑到我们想修改_整个_网页，我们选择所有HTML元素的祖先元素，`body` 标签：

{% highlight css %}
body{ color: grey;}
{% endhighlight %}

所有的子元素和后代元素将会**继承**他们共同的祖先`body`上的颜色值`grey`。

我们也可以使用 `html` 标签。
{: .info}

### 可以继承的属性

可以继承自祖先元素的 CSS 属性并不多。他们主要是一些**文本**属性：

* text color
* font (family, size, style, weight)
* line-height

一些HTML元素不能继承于他的祖先元素。比如超链接，就不能继承他的祖先元素的`color`属性。
{: .info}

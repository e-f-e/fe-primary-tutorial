---
layout: post
title: "CSS <strong>优先级</strong>"
subtitle: "When several rules <strong>collide</strong>"
section: css
---

一个HTML元素可以被 **多个CSS** 命中，让我们用一个简单的段落举例：


{% highlight html %}
<p class="message" id="introduction">
  This is a free HTML and CSS tutorial.
</p>
{% endhighlight %}

我们可以通过 **标签名** 修改这个段落：

{% highlight css %}
p{ color: blue;}
{% endhighlight %}

或者我们可以使用 **类名**：

{% highlight css %}
.message{ color: green;}
{% endhighlight %}

或者我们可以使用 **id**：

{% highlight css %}
#introduction{ color: red;}
{% endhighlight %}

因为浏览器只能给一个段落赋予**一种颜色**，他的颜色决定于CSS中**优先级**最高的。这是 CSS 的优先级。

在我们的例子中，这个段落将会被渲染成**红色**，因为`id`选择器是最_明确_的，比其他选择器**权重**更高。

### CSS 选择器的排序

如果 CSS 中有相同的选择器作用于一个元素，最后一个将会被优先使用。

{% highlight css %}
p{ color: green;}
p{ color: red;}
/* Paragraphs will be red */
{% endhighlight %}

### 100分制

一个快速判断 CSS 权重的方式，通过度量**选择器**的明确性。

* `#id` 100分
* `.class` 10分
* `tag` 1分

无论 CSS 出现的顺序怎样，“得分”最高的将会起作用。

{% highlight css %}
#introduction{ color: red;}
.message{ color: green;}
p{ color: blue;}
{% endhighlight %}

{% highlight html %}
<p class="message" id="introduction">
  MarkSheet is a free HTML and CSS tutorial.
</p>
{% endhighlight %}

<div class="result">
  <p style="color: red;">
    MarkSheet is a free HTML and CSS tutorial.
  </p>
</div>

`#introduction{ color: red;}` 是最明确的，因为 id 必须是整个页面唯一的，并且只会对应页面中的**一个**元素。

`.message{ color: green;}` 可以作用于_任何_属性有 `class="message"` 的HTML元素，因此没有id那么明确。同样的`p{ color: blue;}`可以作用于_任何_HTML段落。

### 如何避免冲突

在写CSS的时候，在几个地方使用相同的属性作用于一个元素的时候，很容易产生冲突。

避免做以下的事情：

* 仅适用 **类选择器**：使用 `.introduction` 替代 `#introduction`，即使这个元素仅在页面中出现一次。
* 避免给一个元素设置**多个类名**：不要写`<p class="big red important">`，可以使用 `<p class="title">`替代，使用更语义化的描述。
* 不要使用**行内样式** 像`<div style="background: blue;">`
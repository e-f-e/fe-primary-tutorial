---
layout: post
title: "HTML <strong>内联</strong> 语义"
subtitle: "The small parts <em>within</em> a block of text"
section: html
---


段落和列表可以给**一块**区域定义，有事我们会给一个词语或几个词语来定义。

### Strong

**重要** 的词语, 使用 `<strong>` 标签:

{% highlight html %}
<p>
  这里很 <strong>重要</strong> 这里并没有.
</p>
{% endhighlight %}

<div class="result">
  <p>
    这里很 <strong>重要</strong> 这里并没有.
  </p>
</div>


通常，`<strong>`元素的字体被展的更**粗**，但是这仅仅是浏览器的默认表现。不要_仅仅_使用`<strong>`来给文字设置粗体，更重要的是让它变的更重要。

### 强调

强调词语本身, 使用 `<em>` 标签:

{% highlight html %}
<p>
  这里 <em>着重强调</em> 这里并没有.
</p>
{% endhighlight %}

<div class="result">
  <p>
    这里 <em>着重强调</em> 这里并没有.
  </p>
</div>


通常，`<em>`元素被展示成_斜体_，但这跟`<strong>`被显示成粗体一样，都只是浏览器的默认表现。我们要使用`<em>`元素来强调文字的重要性。


### 缩写

像 W3C 或者 CD 这种缩写都可以用`<abbr>`标签来包含：

{% highlight html %}
<p>
  我想买一个 <abbr>CD</abbr>.
</p>
{% endhighlight %}


你可以使用`title`属性给缩写的元素一个介绍，当鼠标移入元素一段时间后会显示。

{% highlight html %}
<p>
 我想买一个 <abbr title="Compact Disc">CD</abbr>.
</p>
{% endhighlight %}

<div class="result">
  <p>
    我想买一个 <abbr title="Compact Disc">CD</abbr>.
  </p>
</div>

### 行内引用


`<blockquote>`元素是**块级引用**，他有一个用于**行内**的版本 `<q>`:

{% highlight html %}
<p>
  他刚刚说 <q>“Hello World”</q>.
</p>
{% endhighlight %}

<div class="result">
  <p>
    他刚刚说 <q>“Hello World”</q> .
  </p>
</div>


### 其他的内联元素

这里有大量的内联元素可供参考 [inline semantic elements](https://developer.mozilla.org/en/docs/Web/HTML/Element#Inline_text_semantics) 在这里就不多做示例。

*[CD]: Compact Disc
*[W3C]: World Wide Web Consortium

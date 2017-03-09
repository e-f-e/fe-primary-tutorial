---
layout: post
title: "HTML <strong>家族</strong>"
subtitle: "It's a big family <strong>tree</strong>"
section: html
---


一个HTML文档像一个**大家族**，这个大家族中有各种家族成员。

他们根据自己的职能进行嵌套组合。

###嵌套

下面我们使用一个段落来嵌套两个内联元素来演示HTML的嵌套规则。

{% highlight html %}
<p>
   <strong>鲁迅</strong>先生曾经说过：<q>"时间就像海绵里的水,只要愿挤,总还是有的。"</q>.
</p>
{% endhighlight %}

<div class="result"><p>
   <strong>鲁迅</strong>先生曾经说过：<q>"时间就像海绵里的水,只要愿挤,总还是有的。"</q>.
</p></div>



* `<strong>` 元素给“鲁迅”这个关键字更重的语气
* `<q>` 元素用来表明这句话是一个引用。

实际上`<strong>` 显示出来的 **加粗** 样式 仅仅是**浏览器的默认行为**。我们选择使用某个HTML元素，是要表明他所包含内容的意义和能力，而不是他的外观。

在这个例子中:

* `<p>` 是 `<strong>` 和 `<q>` 的 **父元素**。
* `<strong>` 和 `<q>` 是  `<p>` 的 **子元素**。
* `<strong>` 和 `<q>` 互为 **兄弟元素**

### 规则

嵌套主要依靠的是开始标签和闭合标签。

因为一个HTML元素有开始和闭合标签，并且开始和闭合标签内有其他元素，才会成为父元素。一个_子元素_必须在它的父元素闭合**之前**闭合。


{% highlight html %}
<!-- 这是一段不合法的代码! :-( -->
<p>
  这段HTML代码不合法，因为“strong”的开始标签在这里开始 <strong>但是他在“p”的闭合标签后闭合了.
</p></strong>
{% endhighlight %}

因为  `<strong>` 在 `<p>` 标签之后，(`<strong>`元素将是 `<p>`元素的子元素),  `<strong>` 则必须在 `<p>`标签闭合之前闭合。

{% highlight html %}
<!-- 这是一段合法的代码 :-) -->
<p>
 这段代码是正确的，“strong” 在这里开始<strong>并且在“p”的闭合标签前闭合</strong>.
</p>
{% endhighlight %}

### 深层嵌套


因为元素可以包含其他的元素，所以子元素也可以包含自己的子元素，所以一个HTML文档的嵌套可能会非常深。

下面这个例子可能是博客的一部分：

{% highlight html %}
<article>
  <h1>Famous football quotes</h1>
  <p>
    Sir <strong>Alex Ferguson</strong> once said about Filipo Inzaghi:<q>"That lad must have been born offside"</q>.
  </p>
  <p>
    When criticized by John Carew, <strong>Zlatan Ibrahimovic</strong> replied: <q>"What Carew does with a football, I can do with an orange"</q>.
  </p>
  <p>
    <strong>George Best</strong> said <q>"I spent a lot of money on booze, birds and fast cars. The rest I just squandered."</q> when asked about his lifestyle.
  </p>
</article>
{% endhighlight %}

<div class="result">
  <article>
    <h1>Famous football quotes</h1>
    <p>
      Sir <strong>Alex Ferguson</strong> once said about Filipo Inzaghi:<q>"That lad must have been born offside"</q>.
    </p>
    <p>
      When criticized by John Carew, <strong>Zlatan Ibrahimovic</strong> replied: <q>"What Carew does with a football, I can do with an orange"</q>.
    </p>
    <p>
      <strong>George Best</strong> replied <q>"I spent a lot of money on booze, birds and fast cars. The rest I just squandered"</q> when asked about his lifestyle.
    </p>
  </article>
</div>


* `<article>`是所有元素的**祖先元素**。
* `<article>` 是`<h1>`和3个 `<p>`的**父元素**
* `<h1>` 和3个 `<p>` 是 **兄弟元素**
* 每一个 `<p>` 是它所包含的`<strong>` 和 `<q>` 的**父元素**
* 所有的 `<h1>`, `<p>`, `<strong>` 和 `<q>` 都是 `<article>`的 **后代元素**

用家族来比喻HTML嵌套还是比较合适的。

* 后代元素：一个元素包含的所有元素都是他的后代元素。
* 子元素：子元素是一个元素直接包含的元素，中间没有隔层，就像父亲和儿子。
* 祖先元素：所有包含这个元素的元素都是这个元素的祖先元素。
* 父元素：直接包含这个元素的元素，中间没有隔层。
* 兄弟元素：有相同父元素的元素，互为兄弟元素，这里必须是亲兄弟。


###块级元素和内联元素的嵌套


**块级元素**可以包含块级元素和内联元素。

然而，**内联元素**只能包含其他的内联元素[^1]。

{% highlight html %}
<!-- 这是一段不合法的代码! :-( -->
<strong>
  <p>不能使用strong元素来包含p元素
</strong>
{% endhighlight %}

请记住 祖先元素/后代元素，父元素/子元素和兄弟元素。他们的关系在CSS中将会很有用。

[^1]: 超链接 `<a>` 是一个例外。

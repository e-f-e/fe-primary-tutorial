---
layout: post
title: "HTML <strong>格式</strong>"
subtitle: "When <strong>whitespace</strong> doesn't matter"
section: html
---

人类**书写**出来的HTML代码和浏览器**展现**出来的样子是完全不同的。

通过以前的文章我们已经知道，像HTML**标签**仅仅被浏览器所**阅读**（用来知道你的内容属于什么类型），但是不会被**展示**到页面上。

我们也知道，我们可以在我们的代码中写一些**注释**来帮助其他人读懂代码。但这些注释都不会被浏览器展示到页面上。

还有一些其他的内容也是会被浏览器_忽略_的：

* 换行符
* 空行
* 制表符（或多个空格）

### 换行

在HTML代码中，换行和空行（由多个换行形成的空行）都会被浏览器所**忽略**。他们只会被视作**一个**空格。

{% highlight html %}
<blockquote>
The original idea of the web was that it should be a collaborative


space


where you can communicate through sharing information.
</blockquote>
{% endhighlight %}

<div class="result">
  <blockquote>
  The original idea of the web was that it should be a collaborative space where you can communicate through sharing information.
  </blockquote>
</div>

如果你想在文档中**强制**添加一个换行，你需要使用`<br>` HTML 元素：

{% highlight html %}
<p>At its best, life is completely<br>unpredictable.</p>
{% endhighlight %}

<div class="result">
  <p>At its best, life is completely<br>unpredictable.</p>
</div>

### 制表符

制表符是通过_"Tab"_键输入的特殊的字符。它通常让光标置于下一个制表位，但是有时候它被转成两个空格。

Anyway，像连续的空格或者制表符在网页中都是**不可见**的，他们会被浏览器所忽略：

{% highlight html %}
<p>
  Let's push      this text
  with tabulations.
</p>
{% endhighlight %}

如果你想在文字前面添加空格，你可能要用到CSS，那么想你需要在下一章学习啦。

如果你想**闭合**一个元素，首先你要闭合它的子元素。
{: .info}


### 嵌套格式

HTML代码是相互嵌套的，你必须在书写代码的时候保持嵌套规则。


{% highlight html %}
<article><p>这段代码是写在<strong>一行</strong>里的。</p></article>
{% endhighlight %}

<div class="result">
  <article><p>这段代码是写在 <strong>一行</strong> 里的。</p></article>
</div>

像上面这样，如果把代码写在一行，嵌套元素比较多的话，很难记得开始标签和结束标签的位置，容易影响标签的闭合位置，导致页面错乱。。

{% highlight html %}
<article>
  <p>
    这段代码写了
    <strong>多行</strong>
    但是它
    被显示在
    <em>一行</em>
    里
  </p>
</article>
{% endhighlight %}

<div class="result">
  <article>
    <p>
      这段代码写了
      <strong>多行</strong>
      但是它
      被显示在
      <em>一行</em>
      里
    </p>
  </article>
</div>


这种嵌套格式在HTML代码中被很清晰的展现出来，并且能明显展示出元素之间的关系：

* `<article>` 是**祖先元素**
* `<p>` 是 `<strong>`和`<em>`的**父元素**
* `<strong>`和`<em>` 是 **兄弟元素**


### 代码是写给人看的，只是机器偶尔读一读

制表符，空行，连续的空格，换行符都会被机器所忽略，而且都会被一个空格替代。


代码是写给人看的，只是机器偶尔读一读。制表符，空行，连续的空格，换行符不会影响浏览器解析和展示，你需要把你的HTML文档写的更加可读。


HTML没有特殊的格式规则，但是这里有一些潜规则，


* 使用制表符来更好的展示元素的**嵌套**
* 把块级元素的开始和闭合标签分别写在一行
* 把內联元素单独写在一行（包括开始和闭合标签）


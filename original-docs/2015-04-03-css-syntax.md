---
layout: post
title: "CSS <strong>Syntax</strong>"
subtitle: "who{ what: how;}"
section: css
---

CSS的目的是定义HTML元素的布局和样式。 语法很简单：

{% highlight css %}
/* CSS书写规则 */
selector{ property: value;}
{% endhighlight %}

你可以这样理解它:

{% highlight css %}
who{ what: how;}
{% endhighlight %}

CSS的语法分为三部分:

* **选择器**定义目标HTML元素
* **属性**定义要更改的特征
* **值**定义如何更改该特性

整个代码块（选择器/属性/值）是一个**CSS规范**

### 快速举例

假设你想改变所有**blockquote**元素的颜色

{% highlight html %}
<blockquote>Something something</blockquote>
{% endhighlight %}

关注**标签名**（往期尖括号<>和文本）。在这种情况下，剩下的就是_"blockquote"_。标签名和选择器之间有直接联系。

让我们在CSS中使用它作为选择器，并添加一些样式

{% highlight css %}
blockquote{ background: lightgreen;}
{% endhighlight %}

有趣的是。现在，文字颜色与背景颜色不一致。 让我们改进一下：

{% highlight css %}
blockquote{
  background: lightgreen;
  color: darkgreen;
}
{% endhighlight %}

所以发生了两件事情：

* 我们添加了_第二个_键值对，同时只保留_一个_选择器：你可以为任何选择器设定任意数量的属性。
* 我们可以把每个键值对放在_一行_：就像HTML一样。**空格键**并不重要。特殊符号`{}` `:` 和 `;` 很重要。因此，您可以根据需要格式化CSS，使其更易于阅读，只要其语法仍然有效。

`<blockquote>`标签是一个**块级**元素。它有个**行内**元素与其对应。他们都服务于相同的目的（但他们在不同的上下文中），我们希望对他使用相同的样式。我们可以复制粘贴CSS代码，并只改变选择器。但是你可能会用到，一个更快速的方式。

{% highlight css %}
q,
blockquote{
  background: lightgreen;
  color: darkgreen;
}
{% endhighlight %}

现在我们有两个选择器和两个属性。因此，我们有一组选择器和一组属性（具有各自的值）。

我们可以有多个选择器，多个属性，有时（但很少）会有多个值。
{: .info}

### 注释

就像在HTML中一样，可以方便地编写CSS注释：

{% highlight css %}
/* 这是CSS代码注释 */
q,
blockquote{
  background: lightgreen;
  color: darkgreen;
}
/*
注释仅供人阅读
并不会被计算机解析
*/
{% endhighlight %}

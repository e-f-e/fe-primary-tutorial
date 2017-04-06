---
layout: post
title: "CSS <strong>尺寸</strong> 单位"
subtitle: "Sizing for <strong>content</strong> and <strong>space</strong>"
section: css
---

有几种 CSS 属性用到了 **尺寸单位**：

* `font-size` 定义文字大小
* `border-width` 定义边框的宽度
* `margin` 定义元素间的间距
* `left/right/top/bottom` 定位和移动元素

最常用的单位是：

* `px` 像素
* `%` 百分比
* `em` 相对于父级的 `font-size` 来显示尺寸

### 像素

因为计算机屏幕使用像素来展示内容，所以像素是**最常用的尺寸单位**。

它可以用来设置元素的**宽**：

{% highlight css %}
body{ width: 400px;}
{% endhighlight %}

设置**文字大小**：


{% highlight css %}
body{ font-size: 20px;}
{% endhighlight %}

像素在CSS很直观，因为它们定义一个**绝对的值**：它们不受其它CSS属性的影响。

它被广泛的用在设置**定位**和**间距**上。

### 百分比

百分比是**相对单位**：它依赖它的父级或祖先元素。

比如，块级元素像段落，它会占据**整个可用宽度**。使用 CSS 来设置它只占50%可用宽度。

{% highlight css %}
p{ width: 50%;}
{% endhighlight %}

百分比可以设置其它的CSS属性，像文字大小：

{% highlight css %}
strong{ font-size: 150%;}
{% endhighlight %}

{% highlight html %}
<p>There are <strong>important</strong> challenges ahead of us.</p>
{% endhighlight %}

<div class="result">
  <p>There are <strong style="font-size: 150%;">important</strong> challenges ahead of us.</p>
</div>

### Em

`em` 是一个**相对** 单位：它依赖于元素的 `font-size`.

比如，如果父级元素的 `font-size` 是 `20px`，给子元素设置 `font-size: 0.8em`，子元素的 `font-size` 将被渲染成 `16px`。

不要把 `em` CSS 尺寸单位和 CSS 选择器里的 `em` 弄混， `em` 选择器是选择 HTML `<em>` 元素的。
{: .info}

当你根据其它元素定义 HTML 元素文字大小事，`em` 单位就显得非常有意思。设计一个简单令人愉悦的网页，需要统一的视觉深度。你想让 `<h1>` 是正常文字大小的两倍，`<h2>`是1.5倍，而侧边栏偏小。用CSS实现起来很简单：


{% highlight css %}
body{ font-size: 16px;}
h1{ font-size: 2em;}        /* = 32px */
h2{ font-size: 1.5em;}      /* = 24px */
aside{ font-size: 0.75em;}  /* = 12px */
{% endhighlight %}

如果你决定更换页面正常的文字大小，标题和侧边栏的会相应的变化，你的网页将会保持**视觉平衡**，

通过修改一个值，所有的值都会被修改：

{% highlight css %}
body{ font-size: 20px;}
h1{ font-size: 2em;}        /* = 40px */
h2{ font-size: 1.5em;}      /* = 30px */
aside{ font-size: 0.75em;}  /* = 16px */
{% endhighlight %}

### Rem

`rem` 单位和 `em` 相似， 但它不是依赖_父级_的值，而是依赖**根元素**的值，也就是 `<html>` 元素。

{% highlight css %}
html{ font-size: 18px;}
body{ font-size: 1rem;}     /* = 18px */
h1{ font-size: 2rem;}       /* = 36px */
h2{ font-size: 1.5rem;}     /* = 27px */
{% endhighlight %}

`rem` 和 `em`的不同点是，`rem` 的值是**固定**的，`em` 的值在不同元素之间展现出来的尺寸是不同的。

如果你设置 `html{ font-size: 18px;}`：

* `2rem` 它总是和 `36px` 是相等的。不管你在 CSS 的什么位置使用
* `2em` 它总是父元素 `font-size` 的两倍，不一定是 `36px`

简单的例子展示 `2em` 和 `2rem` 的区别：

{% highlight css %}
html{ font-size: 20px;}
p{ font-size: 0.8rem;}        /* = 16px */
p span{ font-size: 2em;}      /* = 16px * 2 = 32px */
p strong{ font-size: 2rem;}   /* = 20px * 2 = 40px */
{% endhighlight %}

`span` 依赖 `p` 的 `font-size` 的值，`strong` 依赖 `html` 的 `font-size`。

### 我们使用哪一种单位？

我推荐**像素**，像那些绝对值以及不依赖其它元素的设置。它很简单，可以用于设置文字大小，图片尺寸，表格宽度，定位...

**百分比**和 **em** 可以用来配合像素，尤其是相对的文字大小。
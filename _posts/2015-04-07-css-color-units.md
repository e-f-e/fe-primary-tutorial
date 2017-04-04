---
layout: post
title: "CSS <strong>颜色</strong> 单位"
subtitle: "Different ways to define <strong>colors</strong>"
section: css
---

**颜色** 在CSS中运用广泛，比如文字颜色、背景颜色、渐变、阴影、边框... 这里有几种定义颜色的方式，他们各有利弊。

`color` 属性定义**文字**颜色。这很简单。本文的重点是多种可使用的**颜色单位**。

### 颜色名字

CSS 提供了 [145个颜色名](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value), from the most basic (black, white, orange, yellow, blue...) 非常具体。

{% highlight css %}
body{ color: black;}
a{ color: orange;}
{% endhighlight %}

因为颜色名并不容易记住，我们需要更加具体的颜色，所以颜色名不经常用。

### rgb

计算机显示器、电视、手机、都是用RGB颜色模式来展示颜色。本质来讲，每一个颜色都是通过红、绿、蓝混合而成，三种颜色分别有256个值。因为计算机计数从0开始255结束。

考虑到一个颜色是红、绿、蓝的混合结果，而每个颜色只有256个值，所以有`256 * 256 * 256 = 16,777,216`个颜色可以使用。

RGB模式成为CSS的颜色单位的主要原因是因为它与颜色的物理渲染直接相关。

举个例子，红色的数值是红色219，绿色78，蓝色是68：

{% highlight css %}
a{ color: rgb(219, 78, 68);}
{% endhighlight %}

黑色没有数值：

{% highlight css %}
body{ color: rgb(0, 0, 0);}
{% endhighlight %}

在色谱的另一边，白色是满值的：

{% highlight css %}
body{ color: rgb(255, 255, 255);}
{% endhighlight %}

### rgba

`rgba`颜色代为是`rgb`颜色单位多了 **alpha** 值（取值范围是0-1之前，是一个小数值），他定义了这个颜色的透明度。

{% highlight css %}
body{ color: rgba(0, 0, 0, 0.8);}
{% endhighlight %}

有一点透明的黑色
{: .info}

颜色透明的目的是与背景融合，因此根据上下文看起来稍有不同。对于**背景颜色**非常有用。

### hsl and hsla

**HSL** is another way to define a color. Think of it as a **color wheel**.

<figure>
<img src="/images/hsl-model.png" alt="HSL model">
<figcaption>
Source: <a href="https://en.wikipedia.org/wiki/HSL_and_HSV#/media/File:Hsl-hsv_models.svg/">Wikipedia</a>
</figcaption>
</figure>

Instead of a color being a combination of Red, Green and Blue, you define:

* the **Hue** a value ranging from 0 to 360, defines _which color_ you want.
* the **Saturation** percentage, ranging from 0% to 100%, defines _how much_ of that color you want.
* the **Lightness** percentage, ranging from 0% to 100%, defines _how bright_ you want that color to be.

Again, the red color of this website is defined this way in HSL:

{% highlight css %}
a{ color: hsl(4, 68%, 56%);}
{% endhighlight %}

`4` indicates it's red
`68%` indicates the red is quite prominent
`56%` indicates it's halfway between black and white

The `hsl` color unit is easier to understand than `rgb` because the expected result is clearer. You basically define a color in 3 separate steps, and can play around with each value to come up with the color you want. If you want a yellow shade, you can start with a value like `hsl(50, 68%, 56%)`, and alter the Saturation and Lightness value to find the specific shade you're looking for.

I consider `hsl` to be **human-readable**, whereas `rgb` is more **computer-readable**.

`hsla` is the same as `hsl`, with the added value of being able to define an **alpha** value:

{% highlight css %}
body{ color: hsla(4, 68%, 56%, 0.5);}
{% endhighlight %}

A transparent red color.
{: .info}

### Hexadecimal

Colors in CSS can also be defined with **hexadecimal values**, like `#db4e44`.

To understand what hexadecimal values are, let's look at how binary and decimal work:

<div class="table">
  <table>
    <tr>
      <th>
        binary
        <em>2 possible values</em>
      </th>
      <td>0</td>
      <td>1</td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <th>
        decimal
        <em>10 possible values</em>
      </th>
      <td>0</td>
      <td>1</td>
      <td>2</td>
      <td>3</td>
      <td>4</td>
      <td>5</td>
      <td>6</td>
      <td>7</td>
      <td>8</td>
      <td>9</td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <th>
        hexadecimal
        <em>16 possible values</em>
      </th>
      <td>0</td>
      <td>1</td>
      <td>2</td>
      <td>3</td>
      <td>4</td>
      <td>5</td>
      <td>6</td>
      <td>7</td>
      <td>8</td>
      <td>9</td>
      <td>A</td>
      <td>B</td>
      <td>C</td>
      <td>D</td>
      <td>E</td>
      <td>F</td>
    </tr>
  </table>
</div>

Consider the 0-9 numbers and the A-F letters as **symbols**.

Humans use the **decimal** system. We have 10 symbols to form numbers.

In **hexadecimal**, we have 16 symbols to form numbers. Because 0-9 are not enough symbols, we also use A-F. And it starts at zero. So:

* the number `4` in hexadecimal is `4`
* the number `12` in hexadecimal is `C`
* the number `16` in hexadecimal is `10` because after you've run out of symbols (the last one being `F`), you add a second symbol to the left and increment (`0` becomes `1`) and the right one starts over (from `F` to `0`)

#### Do I have to remember this?

Not at all! It is here to provide an explanation of how hexadecimal values work. The most important thing to remember is that there are 16 hexadecimal symbols.

Just like RGB, a hexadecimal color value is a combination of Red, Green, and Blue, each of them being represent as a hexadecimal value, like `DB` for Red, `4E` for Green, and `44` for Blue.

Because Red, Green or Blue can only have 2 symbols, their possible values are `16 * 16 = 256`, which mirrors the RGB color unit!

#### Why not use RGB then?

Usually, when choosing colors, you **don't write** them directly. You either use a color picker, or copy/paste it from Photoshop, or choose a [colour palette](http://www.colourlovers.com/palettes) somewhere.

Hexadecimal values are easier to **copy and paste**, as they only comprise 6 characters.

![Photoshop one field for hex](/images/photoshop-color-picker.png)

#### It is easier to copy paste a single field than 3 separate ones.

In CSS, you only need to prepend a hexadecimal color value with a hash `#`.

### Which one to pick?

If you don't intend to use any transparent color, stick to **hexadecimal** values, as they are easier to copy/paste and don't take much space in your code.

If you want some transparency, convert your color from hex to rgba, and use the `rgba` color unit.

If you want to play around with your color directly in the browser, try `hsl`.

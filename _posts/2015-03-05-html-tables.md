---
layout: post
title: "HTML <strong>表格</strong>"
subtitle: "For <strong>multi-dimensional</strong> data"
section: html
---

HTML **表格** 是意义是展示表格数据，仅用来展示可以通过**行**和**列**来展示的内容。

It's like having a **spreadsheet** in Excel.

看起来像Excel电子表格。

### Syntax

### 语法


在 HTML 创建一个表格需要特殊的结构：

* 使用 `<table>`
* 使用 `<tr>` 添加行
* 使用 `<td>` 添加_均匀_的列或者标题

创建表格至少要使用这三个元素。

当我们写码的时候，我们需要从左到右，从上到下来定义表格内容。

{% highlight html %}
<table>
  <tr>
    <td>John Lennon</td>
    <td>Rhythm Guitar</td>
  </tr>
  <tr>
    <td>Paul McCartney</td>
    <td>Bass</td>
  </tr>
  <tr>
    <td>George Harrison</td>
    <td>Lead Guitar</td>
  </tr>
  <tr>
    <td>Ringo Starr</td>
    <td>Drums</td>
  </tr>
</table>
{% endhighlight %}

<div class="result">
  <table>
    <tr>
      <td>John Lennon</td>
      <td>Rhythm Guitar</td>
    </tr>
    <tr>
      <td>Paul McCartney</td>
      <td>Bass</td>
    </tr>
    <tr>
      <td>George Harrison</td>
      <td>Lead Guitar</td>
    </tr>
    <tr>
      <td>Ringo Starr</td>
      <td>Drums</td>
    </tr>
  </table>
</div>


正如你所看到的，HTML里创建一个表格是比较繁琐的：仅仅创建几行数据就用到了那么多的标签。


### thead、 tfoot、 tbody


像网页一样，表格也有 header、foot、body，像HTML一样，这些标签都是纯**语义**的：为表格提供更多的结构。


`<thead>` `<tfoot>`  `<tbody>`  是由**行**组成，都是`<table>`的子元素，并且它的子元素是一个或多个`<tr>`。简而言之，它们是table下的第一级元素。


`<thead>` 和 `<tfoot>` 被用来做每一列的**总览**。


让我们使用head和body升级之前的列表。

{% highlight html %}
<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Instrument</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John Lennon</td>
      <td>Rhythm Guitar</td>
    </tr>
    <tr>
      <td>Paul McCartney</td>
      <td>Bass</td>
    </tr>
    <tr>
      <td>George Harrison</td>
      <td>Lead Guitar</td>
    </tr>
    <tr>
      <td>Ringo Starr</td>
      <td>Drums</td>
    </tr>
  </tbody>
</table>
{% endhighlight %}

<div class="result">
  <table>
    <thead>
      <tr>
        <th>Name</th>
        <th>Instrument</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>John Lennon</td>
        <td>Rhythm Guitar</td>
      </tr>
      <tr>
        <td>Paul McCartney</td>
        <td>Bass</td>
      </tr>
      <tr>
        <td>George Harrison</td>
        <td>Lead Guitar</td>
      </tr>
      <tr>
        <td>Ringo Starr</td>
        <td>Drums</td>
      </tr>
    </tbody>
  </table>
</div>

### tfoot particularity

### tfoot

添加tfoot给表格

{% highlight html %}
<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Instrument</th>
    </tr>
  </thead>
  <tfoot>
    <tr>
      <th>Name</th>
      <th>Instrument</th>
    </tr>
  </tfoot>
  <tbody>
    <tr>
      <td>John Lennon</td>
      <td>Rhythm Guitar</td>
    </tr>
    <tr>
      <td>Paul McCartney</td>
      <td>Bass</td>
    </tr>
    <tr>
      <td>George Harrison</td>
      <td>Lead Guitar</td>
    </tr>
    <tr>
      <td>Ringo Starr</td>
      <td>Drums</td>
    </tr>
  </tbody>
</table>
{% endhighlight %}

<div class="result">
  <table>
    <thead>
      <tr>
        <th>Name</th>
        <th>Instrument</th>
      </tr>
    </thead>
    <tfoot>
      <tr>
        <th>Name</th>
        <th>Instrument</th>
      </tr>
    </tfoot>
    <tbody>
      <tr>
        <td>John Lennon</td>
        <td>Rhythm Guitar</td>
      </tr>
      <tr>
        <td>Paul McCartney</td>
        <td>Bass</td>
      </tr>
      <tr>
        <td>George Harrison</td>
        <td>Lead Guitar</td>
      </tr>
      <tr>
        <td>Ringo Starr</td>
        <td>Drums</td>
      </tr>
    </tbody>
  </table>
</div>


尽管我们把 `<tfoot>` 添加在 `<tbody>` 之前，它仍然出现在了表格的**最后**。



`<tbody>` 可以包含_大量_的数据，但是浏览器想在接收到所有数据之前先渲染foot。这也是为什么我们把`<tfoot>`写在前面的原因。


### colspan（跨列） 和 rowspan（跨行）

`colspan` 允许一个单元格跨越多个列，`rowspan` 允许一个单元格跨越多行。

也就是说，如果你想合并列，你需要使用 `rowspan`，它允许一**列**跨越多_行_。

{% highlight html %}
<table border="1">
  <tr>
    <th colspan="2">Michael Jackson Singles</th>
  </tr>
  <tr>
    <th rowspan="3">1979</th>
    <td>Don't Stop 'Til You Get Enough</td>
  </tr>
  <tr>
    <td>Rock with You</td>
  </tr>
  <tr>
    <td>Off the Wall</td>
  </tr>
</table>
{% endhighlight %}

<div class="result">
  <table border="1">
    <tr>
      <th colspan="2">Michael Jackson Singles</th>
    </tr>
    <tr>
      <th rowspan="3">1979</th>
      <td>Don't Stop 'Til You Get Enough</td>
    </tr>
    <tr>
      <td>Rock with You</td>
    </tr>
    <tr>
      <td>Off the Wall</td>
    </tr>
  </table>
</div>


"Michael Jackson Singles" 行 跨越两列，所以，它下面的一行包括**两**列。


"1979" 跨越了3行，它后面的两行都只有*一个*单元格，并且给"1979"让出了一列。


一般来说，我们很难去创建一个不规则的表格，一种简单的方式是：先创建2*4的表格，然后删除表格以后添加 `colspan` 和 `rowspan` 属性。


在上面这个例子中，我们认为它有**8**个单元格，我们只写了**5**个，但是 `colspan="2"` 和 `rowspan="3"` 带来了**3个单元格**。
{: .info}

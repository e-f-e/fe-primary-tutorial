---
layout: post
title: "HTML <strong>表单</strong>"
subtitle: "To make a page <strong>interactive</strong>"
section: html
---

在单纯的导航网站，用户的交互仅仅是通过**链接**来浏览各个页面。

但是网站很多时候要包含一些可以**输入**的元素。这些交互包括：

* 给网站添加注册登录功能
* 输入用户的信息（姓名、地址、银行卡信息）
* 过滤内容 （下拉菜单，选择框）
* 搜索
* 上传文件

为了满足这些需求，HTML提供了交互方式， **表单控件**：

* 文本输入 （一行或多行）
* 单选按钮
* 复选框
* 下拉
* 上传组件
* 提交按钮

这些工具都是由HTML**标签**来控制，多数都是使用`<input>`标签。因为这是一个自闭和元素，它的_类型_都是通过`type`属性定义的。

{% highlight html %}
<!-- A 文本框 -->
<input type="text">
<!-- A 复选框 -->
<input type="checkbox">
<!-- A 单选按钮 -->
<input type="radio">
{% endhighlight %}

<div class="result">
  <input type="text">
  <br>
  <input type="checkbox">
  <br>
  <input type="radio">
</div>

### 表单元素


`<form>`是一个块级元素，它定义了一个网页内用来**交互**的部分。所有的表单控件元素（`<input>`、 `<textarea>` 或 `<button>`）必须写在`<form>`标签内。

两个HTML属性是`<form>`标签必须包括的：

* `action` 定义这个表单的提交地址，这些内容将会提交到某一个地址。
* `method` 定义表单提交请求的类型，比如GET或者POST。


通常，表单信息被发送到**服务端**。不过这些内容不是这个教程所覆盖的。

一个表单包括了一系列的input，来完成**一个**操作。如果你想写一个登陆表单，你需要3个控件：
 submit button `<input type="submit">`

* a 电子邮箱输入框 `<input type="email">`
* a 密码输入框 `<input type="password">`
* a 提交按钮 `<input type="submit">`


这3个HTML元素需要被`<form action="/login" method="POST">`包裹。


你可以创建一个相似的注册页面，使用一个新的`<form>`元素。


### 文本输入


几乎所有的表单都需要用户输入文本，为了让用户输入用户名、邮箱、密码、地址等，文本表单控件会有一些差异：


<div class="table">
  <table>
    <tr>
      <th>文本</th>
      <td><code>&lt;input type="text"&gt;</code></td>
      <td><input type="text"></td>
      <td>可以输入一些文字</td>
    </tr>
    <tr>
      <th>Email</th>
      <td><code>&lt;input type="email"&gt;</code></td>
      <td><input type="email"></td>
      <td>必须输入Email，如果格式错误会提示。</td>
    </tr>
    <tr>
      <th>密码</th>
      <td><code>&lt;input type="password"&gt;</code></td>
      <td><input type="password"></td>
      <td>将会把字符展示成*号</td>
    </tr>
    <tr>
      <th>数字</th>
      <td><code>&lt;input type="number"&gt;</code></td>
      <td><input type="number"></td>
      <td>文本框里会出现上/下，可以调整数值</td>
    </tr>
    <tr>
      <th>电话</th>
      <td><code>&lt;input type="tel"&gt;</code></td>
      <td><input type="text"></td>
      <td>可以自动补全一些信息</td>
    </tr>
    <tr>
      <th>多行文本呢</th>
      <td><code>&lt;textarea&gt;&lt;/textarea&gt;</code></td>
      <td><textarea></textarea></td>
      <td>可以调整大小</td>
    </tr>
  </table>
</div>


这些输入框看起来相同，都允许用户输入文字，它们的_type_属性给它们提供了一些**语义**，通过定义它的类型，可以设置它所**支持**的信息。


浏览器给这些控件一些默认的外观，来增加交互感或者提醒用户这里需要输入什么类型信息。

比如，密码输入框的字符将会被*提到。

<div class="result">
  <input type="password" value="hunter2">
</div>

数字输入框，可以通过点击上下键增加和减少数字。

<div class="result">
  <input type="number" value="12">
</div>

### Placeholders

### 占位符

文本输入框可以展现一些**占位符**，就是在文本框没有内容的时候自动展示出来的文本。

{% highlight html %}
<input type="text" placeholder="请输入昵称">
{% endhighlight %}

<div class="result">
  <input type="text" placeholder="请输入昵称">
</div>

如果你开始输入内容，你会发现“请输入昵称”消失了。

### Labels

有时候form元素自身是无法描述自己是用来做什么的，所以会给form元素添加一些**label**。

{% highlight html %}
<label>Email</label>
<input type="email">
{% endhighlight %}

<div class="result">
  <label>Email</label>
  <input type="email">
</div>

Placeholders 已经暗示了输入框需要输入什么内容，但是用户输入内容后就会消失，labels可以一直显示，它可以写在form控件的旁边，像复选框或者单选按钮一样。


尽管你你可以使用短的段落去描述form元素，使用`<label>`在于以上更加合法，因为它仅仅在表单里面存在。并且它有`for`属性和 input 上的 `id` 属性是匹配的。

{% highlight html %}
<label for="first_name">名字</label>
<input id="first_name" type="text">
{% endhighlight %}

<div class="result">
  <label for="first_name">名字</label>
  <input id="first_name" type="text">
</div>

点击label将会自动将焦点和光标置于input中。然而这看起来并没什么用，它可以被用在复选框和单选按钮上。

### 复选框

**复选框** 有两个状态：已选 和 未选中。

{% highlight html %}
<input type="checkbox"> 记住我
{% endhighlight %}

<div class="result">
  <input type="checkbox"> 记住我
</div>

因为它太小，所以很容易点不到。所以可以添加一个`<label>`在它旁边来描述。

{% highlight html %}
<label>
  <input type="checkbox"> 我同意
</label>
{% endhighlight %}

<div class="result">
  <label>
    <input type="checkbox"> 我同意
  </label>
</div>

你可以点击“我同意”来切换选择这个复选框。

默认情况下，复选框是未选中状态。你可以使用`checked`属性来设置选中状态。

{% highlight html %}
<label>
  <input type="checkbox" checked> 记住登陆状态
</label>
{% endhighlight %}

<div class="result">
  <label>
    <input type="checkbox" checked> 记住登陆状态
  </label>
</div>

### 单选按钮


你可以通过单选按钮给用户提供一个**选项列表**，供用户挑选。

这个表单控件需要提供**一组**单选按钮。这一组选项按钮的`name`属性必须一致。


{% highlight html %}
<label>Marital status</label>
<label>
  <input type="radio" name="status">
  大一
</label>
<label>
  <input type="radio" name="status">
  大二
</label>
<label>
  <input type="radio" name="status">
  大三
</label>
<label>
  <input type="radio" name="status">
  大四
</label>
{% endhighlight %}

<div class="result">
  <label>Marital status</label>
  <label>
    <input type="radio" name="status">
    大一
  </label>
  <label>
    <input type="radio" name="status">
    大二
  </label>
  <label>
    <input type="radio" name="status">
    大三
  </label>
  <label>
    <input type="radio" name="status">
    大四
  </label>
</div>


因为所有的单选按钮使用了相同的`name`属性，所以选择一个选项后，其它选项将会被取消选中。所以单选按钮是互斥的。


#### 单选按钮 和 复选框 之间的区别


复选框可以是一个， 单选按钮只能是一组选项。


复选框是**可选择的**，单选按钮是**强制选择**的，这也是为什么你必须点击另外一个选项才会取消当前选项的原因。到最后，radio总是被选择的。


### 下拉菜单


如果选项特别多，可以使用`<select>`下拉菜单。


它的工作原理像单选按钮，但展示不一样。

{% highlight html %}
<select>
  <option>January</option>
  <option>February</option>
  <option>March</option>
  <option>April</option>
  <option>May</option>
  <option>June</option>
  <option>July</option>
  <option>August</option>
  <option>September</option>
  <option>October</option>
  <option>November</option>
  <option>December</option>
</select>
{% endhighlight %}

<div class="result">
  <select>
    <option>January</option>
    <option>February</option>
    <option>March</option>
    <option>April</option>
    <option>May</option>
    <option>June</option>
    <option>July</option>
    <option>August</option>
    <option>September</option>
    <option>October</option>
    <option>November</option>
    <option>December</option>
  </select>
</div>


#### 多选下拉菜单

如果你给`<select>`添加`multiple`属性，你可以给它多选的能力。

{% highlight html %}
<label>你有哪些浏览器?</label>
<select multiple>
  <option>Google Chrome</option>
  <option>Internet Explorer</option>
  <option>Mozilla Firefox</option>
  <option>Opera</option>
  <option>Safari</option>
</select>
{% endhighlight %}

<div class="result">
  <label>你有哪些浏览器?</label>
  <br>
  <select multiple>
    <option>Google Chrome</option>
    <option>Internet Explorer</option>
    <option>Mozilla Firefox</option>
    <option>Opera</option>
    <option>Safari</option>
  </select>
</div>


可以通过Ctrl（或者 ⌘）并且点击选择多项。这是一个代替复选框的好方法。


### 例子：一个完整的注册表单

{% highlight html %}
<form action="/signup" method="POST">
  <p>
    <label>标题</label>
    <label>
      <input type="radio" name="title" value="mr">
      先生
    </label>
    <label>
      <input type="radio" name="title" value="mrs">
      夫人
    </label>
    <label>
      <input type="radio" name="title" value="miss">
      小姐
    </label>
  </p>
  <p>
    <label>名字</label>
    <input type="text" value="first_name">
  </p>
  <p>
    <label>姓氏</label>
    <input type="text" value="last_name">
  </p>
  <p>
    <label>Email</label>
    <input type="email" value="email">
  </p>
  <p>
    <label>手机号</label>
    <input type="tel" value="phone">
  </p>
  <p>
    <label>密码</label>
    <input type="password" value="password">
  </p>
  <p>
    <label>再次输入密码</label>
    <input type="password" value="password_confirm">
  </p>
  <p>
    <label>国家</label>
    <select>
      <option>中国</option>
      <option>发过</option>
      <option>德国</option>
      <option>意大利</option>
      <option>日本</option>
      <option>美国</option>
      <option>英国</option>
    </select>
  </p>
  <p>
    <label>
      <input type="checkbox" value="terms">
      我同意 <a href="/terms">声明</a>
    </label>
  </p>
  <p>
    <button>
      注册
    </button>
  </p>
</form>
{% endhighlight %}

<div class="result">
  <form action="/signup" method="POST">
    <p>
      <label>标题</label>
      <label>
        <input type="radio" name="title" value="mr">
        先生
      </label>
      <label>
        <input type="radio" name="title" value="mrs">
        夫人
      </label>
      <label>
        <input type="radio" name="title" value="miss">
        小姐
      </label>
    </p>
    <p>
      <label>名字</label>
      <input type="text" value="first_name">
    </p>
    <p>
      <label>姓氏</label>
      <input type="text" value="last_name">
    </p>
    <p>
      <label>Email</label>
      <input type="email" value="email">
    </p>
    <p>
      <label>手机号</label>
      <input type="tel" value="phone">
    </p>
    <p>
      <label>密码</label>
      <input type="password" value="password">
    </p>
    <p>
      <label>再次输入密码</label>
      <input type="password" value="password_confirm">
    </p>
    <p>
      <label>国家</label>
      <select>
        <option>中国</option>
        <option>发过</option>
        <option>德国</option>
        <option>意大利</option>
        <option>日本</option>
        <option>美国</option>
        <option>英国</option>
      </select>
    </p>
    <p>
      <label>
        <input type="checkbox" value="terms">
        我同意 <a href="/terms">声明</a>
      </label>
    </p>
    <p>
      <button>
        注册
      </button>
    </p>
  </form>
</div>


有很多可以使用的表单控件，这里我们只列出了一些常用的。


可以开始美化我们的页面啦！


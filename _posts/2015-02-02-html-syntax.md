---
layout: post
title: "HTML <strong>语法</strong>"
subtitle: "As any language, HTML has <strong>rules</strong>"
section: html
---

**HTML**  **H**yper**T**ext **M**arkup **L**anguage:（超文本标记语言）

* **超文本(HyperText)**  代表着它通过HTTP协议在网络上传输
* **标记(Markup)** 代表着它的代码是一些可以解释的关键词
* **语言(Language)** 代表它可以被人和机器阅读

HTML 有一套相对于其它语言更简单的规则，HTML通过**边界**来区别什么时候开始和结束。


以下是一个简单的代表段落的HTML代码：

{% highlight html %}
<p>这是一个段落，一般我们将段落写在p标签内。</p>
{% endhighlight %}

<div class="result"><p>这是一个段落，一般我们将段落写在p标签内。</p></div>

上面的尖括号`<`{:.language-html} and `>`{:.language-html} 就是HTML标签，它定义网页内一些内容的开始和结束。

每一个标签都有明确的**意义**，比如说上面这个例子`p`{:.language-html}代表着 **段落**。


标签通常成对出现：

* 开始标签 `<p>`{:.language-html} 定义段落的**开始**
* 闭合标签 `</p>`{:.language-html} 定义段落的**闭合**

开始标签和闭合标签的书写区别在于，闭合标签的标签名前带一个`/`{:.language-html}。

如果你用开始标签和闭合标签包含了一些内容，你将获得一个**HTML 元素**。上面的例子就是通过`<p>`{:.language-html}和`</p>`{:.language-html}创建了一个HTML 元素。

你可以 [在浏览器中查看](/html/sample-paragraph.html)这个例子，你会发现，**HTML标签并没有在页面中显示**。这些标签只用来让浏览器 _识别_ 你写的**内容**的 _类型_。

### 在哪里写HTML

你肯定写过文本文件，文本文件的后缀名是`.txt`。

你可以通过修改后缀名，把`.txt`改为`.html`来创建一个**HTML 文档**。

复制下面的内容到你的文本编辑器

{% highlight html %}
<p>Hello World!</p>
{% endhighlight %}

将它保存为 `my-first-webpage.html` 并且通过浏览器打开它，你可以看到以下内容：

<div class="result"><p>Hello World!</p></div>

注意：
* 使用Notepad++、Sublime Text 等文本编辑器来**创建**HTML文档。
* 使用Chrome、Firefox来**打开**HTML文档。

### 属性


属性可以给HTML元素附加其它信息，属性写在HTML_标签里面_。当然，HTML属性也不会在浏览器上显示出来。


例子：`href`属性用来给`a`标签定义一个**链接**

{% highlight html %}
<a href="http://www.mozilla.com/firefox">下载 Firefox</a>
{% endhighlight %}

<div class="result"><a href="http://www.mozilla.com/firefox">下载 Firefox</a></div>


这里有[通用HTML属性](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes) 可以被用在任意一个HTML元素上，并且这些属性都是可选的。


我们以后主要会用`class`(用于CSS选择器的名字)，`title`（鼠标移入元素后一段时间显示的提示）

有些HTML元素**必选**的属性，比如，插入一张图片，你需要使用`src`（资源）属性给元素提供一个图片的地址。


{% highlight html %}
<img src="#" alt="图片的简介">
{% endhighlight %}

考虑到`<img>`元素是用来展示图片的，所以给他指定一个路径是有必要的。




### 注释

如果你想写一些不需要浏览器展示的内容，可以写使用**注释**。它会被浏览器忽略，这些内容只对编写、查看代码的人有用。


一条注释以`<!--`开始，`-->`结束。

{% highlight html %}
<!-- 这是一条注释，将会被浏览器忽略 -->
<p>Hello World!</p>
{% endhighlight %}


<div class="result"><p>Hello World!</p></div>

### 自闭合标签

有些HTML元素只有开始标签：

{% highlight html %}
<br> <!-- line-break -->
<img src="http://placehold.it/50x50" alt="Description"> <!-- image -->
<input type="text"> <!-- text input -->
{% endhighlight %}

因为自闭合标签没有闭合标签，所以它没有不能包含其他文档内容，只能通过一些属性来设置额外的信息。

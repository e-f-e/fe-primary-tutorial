---
layout: post
title: "A <strong>valid</strong> HTML document"
subtitle: "Some boilerplate"
section: html
---

Up until now, we've been looking at _isolated_ snippets of HTML code. But an **HTML document** (or webpage, it means the same thing) requires a specific structure in order to be **valid**.
直到现在，我们一直着眼于_孤立的_HTML代码片段。但是一个有效的**HTML文档**（或网页，同样的意思）需要一个具体的结构。

Why do we care about _validating_ an HTML document?
为什么我们关心一个HTML文档的有效性呢？

* **correct**: a valid document is _correctly displayed_ by the browser
* **准确性**：一个有效的文档可以被浏览器正确地显示
* **debugging**: invalid HTML code can trigger bugs hard to target
* **可调试**：无效的HTML代码很难触发错误
* **maintenance**: a valid document is easier to _update_ later, even by someone else
* **可维护**：一个有效的文档以后很容易_升级_，即使是任何一个人

### 文档类型

The first information to provide is the _type_ of HTML document we're writing: the **Doctype**.
第一个提供的信息是HTML文档的_类型_，我们称之为：**文档类型**

Think of the doctype as the version of a car throughout the years: a Ford Fiesta bought in 1986 was a Fiesta 2. If you buy one today, it's a Fiesta 7.

There used to be multiple versions of HTML coexisting (XHTML and HTML 4.01 have been competing standards). Nowadays, **HTML 5** is the norm.

To tell the browser that the HTML document is an HTML 5, just start your document with the following line:

{% highlight html %}
<!DOCTYPE html>
{% endhighlight %}

That's it. Just set it and forget it.

You may wonder why this HTML 5 doctype doesn't mention the number "5". The W3C thought the previous doctype definitions were too confusing and took the opportunity to simplify it by removing any mention of the HTML version.
{: .info}

### The <html> element

Apart from the doctype line, **all** your HTML document must be wrapped inside an `<html>` element:

{% highlight html %}
<!DOCTYPE html>
<html>
  <!-- The rest of your HTML code is here -->
</html>
{% endhighlight %}

The `<html>` is technically the **ancestor** of all HTML elements.

### <head>

The same way attributes carry additional information for an HTML element, the `<head>` element carries additional information for the _whole_ webpage.

For example, the **title** of the page (displayed on the tab) is located in the `<head>`:

{% highlight html %}
<head>
  <title>My fabulous blog</title>
</head>
{% endhighlight %}

Other HTML elements can appear in the `<head>`, and _only_ in the `<head>`:

* `<link>`
* `<meta>`
* `<style>`

### <body>

While the `<head>` only contains metadata not meant to be displayed anywhere (apart from the `<title>`), the `<body>` element is where we write all our content. Everything _inside_ the `<body>` will be **displayed** in the browser window.

### A complete valid HTML document

Combining all these requirements, we can write a simple and valid HTML document:

{% highlight html %}
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>MarkSheet</title>
    <meta name="description" content="A simple HTML and CSS tutorial">
  </head>
  <body>
    <p>Hello World!</p>
  </body>
</html>
{% endhighlight %}

If you view this example in your browser, you'll see that:

* _"MarkSheet"_ is written on the browser tab
* _"Hello World!"_ is the only text displayed in the window, because it's the only content _within_ the `<body>`

<p>The <abbr title="World Wide Web Consortium">W3C</abbr> provides a <a href="http://validator.w3.org/#validate_by_input">Markup Validation Service</a> to check any HTML document for errors and warnings.</p>
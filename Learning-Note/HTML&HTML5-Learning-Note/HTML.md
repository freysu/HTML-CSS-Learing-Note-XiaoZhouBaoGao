[toc]

## HTML 介绍

HTML 是用来描述网页的一种语言。

- HTML 指的是**超文本标记语言** (Hyper Text Markup Language)
- **HTML 不是一种编程语言，而是一种标记语言** (markup language)
- 标记语言是一套标记标签 (markup tag)
- HTML 使用**标记标签**来描述网页

## HTML 基本语法

### HTML 标签

HTML 标记标签通常被称为 HTML 标签 (HTML tag)。

- HTML 标签是由**尖括号**包围的关键词，比如 `<html>`
- HTML 标签通常是**成对出现**的，比如 `<b>` 和 `</b>`
- 标签对中的第一个标签是**开始标签**，第二个标签是**结束标签**
- 开始和结束标签也被称为**开放标签**和**闭合标签**

### HTML 文档 = 网页

- HTML 文档**描述网页**
- HTML 文档**包含 HTML 标签**和纯文本
- HTML 文档也被称为**网页**

Web 浏览器的作用是读取 HTML 文档，并以网页的形式显示出它们。浏览器不会显示 HTML 标签，而是使用标签来解释页面的内容：

```html
<html>
  <body>
    <h1>My First Heading</h1>

    <p>My first paragraph.</p>
  </body>
</html>
```

**HTML 文档是由 HTML 元素定义的。**

### HTML 元素

HTML 元素指的是从开始标签（start tag）到结束标签（end tag）的所有代码。

| 开始标签                  | 元素内容            | 结束标签 |
| ------------------------- | ------------------- | -------- |
| `<p>`                     | This is a paragraph | `</p>`   |
| `<a href="default.htm" >` | This is a link      | `</a>`   |
| `<br />`                  |                     |          |

注释：开始标签常被称为开放标签（opening tag），结束标签常称为闭合标签（closing tag）。

### HTML 元素语法

- HTML 元素以**开始标签**起始
- HTML 元素以**结束标签**终止
- **元素的内容**是开始标签与结束标签之间的内容
- 某些 HTML 元素具有**空内容（empty content）**
- 空元素**在开始标签中进行关闭**（以开始标签的结束而结束）
- 大多数 HTML 元素可拥有**属性**

### 嵌套的 HTML 元素

大多数 HTML 元素可以嵌套（可以包含其他 HTML 元素）。

HTML 文档由嵌套的 HTML 元素构成。

#### HTML 文档实例

```html
<html>
  <body>
    <p>This is my first paragraph.</p>
  </body>
</html>
```

上面的例子包含三个 HTML 元素。

### [行内元素与块级元素对比](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Inline_elements#行内元素与块级元素对比)

- 内容

  一般情况下，行内元素只能包含数据和其他行内元素。

  而块级元素可以包含行内元素和其他块级元素。这种结构上的包含继承区别可以使块级元素创建比行内元素更” 大型 “的结构。

- 格式

  默认情况下，行内元素不会以新行开始，而块级元素会新起一行。

#### 块级元素

以下是 HTML 中所有的块级元素列表（虽然” 块级 “在新的 HTML5 元素中没有明确定义）

`<address>`
联系方式信息。
`<article>` HTML5
文章内容。
`<aside>` HTML5
伴随内容。
`<audio>` HTML5
音频播放。
`<blockquote>`
块引用。
`<canvas>` HTML5
绘制图形。
`<dd>`
定义列表中定义条目描述。
`<div>`
文档分区。
`<dl>`
定义列表。
`<fieldset>`
表单元素分组。
`<figcaption>` HTML5
图文信息组标题
`<figure>` HTML5
图文信息组 (参照 `<figcaption>`)。
`<footer>` HTML5
区段尾或页尾。
`<form>`
表单。
`<h1>` (en-US), `<h2>` (en-US), `<h3>` (en-US), `<h4>` (en-US), `<h5>` (en-US), `<h6>` (en-US)
标题级别 1-6.
`<header>` HTML5
区段头或页头。
`<hgroup>` HTML5
标题组。
`<hr>`
水平分割线。

`<noscript>`
不支持脚本或禁用脚本时显示的内容。
`<ol>`
有序列表。
`<output>` HTML5
表单输出。
`<p>`
行。
`<pre>`
预格式化文本。
`<section>` HTML5
一个页面区段。
`<table>`
表格。
`<tfoot>`
表脚注。
`<ul>`
无序列表。
`<video>` HTML5
视频。

#### 行内元素

下面的元素都是行内元素：

`<b>`
`<big>`
`<i>`
`<small>`
`<tt>`
`<abbr>`
`<acronym>`
`<cite>`
`<code>`
`<dfn>`
`<em>`
`<kbd>`
`<strong>`
`<samp>`
`<var>`
`<a>`
`<bdo>`
`<br>`
`<img>`
`<map>`
`<object>`
`<q>`
`<script>`
`<span>`
`<sub>`
`<sup>`
`<button>`
`<input>`
`<label>`
`<select>`
`<textarea>`

### HTML 注释

可以将注释插入 HTML 代码中，这样可以提高其可读性，使代码更易被人理解。浏览器会忽略注释，也不是显示它们。

注释是这样写的：

#### 实例

```html
<!-- This is a comment -->
```

_注释：开始括号之后（左边的括号）需要紧跟一个叹号，结束括号之前（右边的括号）不需要。_

_提示：合理地使用注释可以对未来的代码编辑工作产生帮助。_

## HTML 属性

**属性为 HTML 元素提供附加信息。**

### HTML 属性

HTML 标签可以拥有**属性**。属性提供了有关 HTML 元素的**更多的信息**。

属性总是以名称/值对的形式出现，比如：**name="value"**。

属性总是在 HTML 元素的**开始标签**中规定。

### 属性实例

HTML 链接由 `<a>` 标签定义。链接的地址在 href 属性中指定：

```html
<a href="http://www.w3school.com.cn">This is a link</a>
```

下面列出了适用于大多数 HTML 元素的属性：

| 属性  | 值                 | 描述                                     |
| ----- | ------------------ | ---------------------------------------- |
| class | _classname_        | 规定元素的类名（classname）              |
| id    | _id_               | 规定元素的唯一 id                        |
| style | _style_definition_ | 规定元素的行内样式（inline style）       |
| title | _text_             | 规定元素的额外信息（可在工具提示中显示） |

## HTML 速查手册

### HTML Basic Document

```html
<html>
  <head>
    <title>Document name goes here</title>
  </head>
  <body>
    Visible text goes here
  </body>
</html>
```

### Text Elements

```html
<p>This is a paragraph</p>
<br />
(line break)
<hr />
(horizontal rule)
<pre>This text is preformatted</pre>
```

### Logical Styles

```html
<em>This text is emphasized</em>
<strong>This text is strong</strong>
<code>This is some computer code</code>
```

### Physical Styles

```html
<b>This text is bold</b> <i>This text is italic</i>
```

### Links, Anchors, and Image Elements

```html
<a href="http://www.example.com/">This is a Link</a>
<a href="http://www.example.com/"><img src="URL" alt="Alternate Text" /></a>
<a href="mailto:webmaster@example.com">Send e-mail</a>A named anchor:
<a name="tips">Useful Tips Section</a>
<a href="#tips">Jump to the Useful Tips Section</a>
```

### Unordered list

```html
<ul>
  <li>First item</li>
  <li>Next item</li>
</ul>
```

### Ordered list

```html
<ol>
  <li>First item</li>
  <li>Next item</li>
</ol>
```

### Definition list

```html
<dl>
  <dt>First term</dt>
  <dd>Definition</dd>
  <dt>Next term</dt>
  <dd>Definition</dd>
</dl>
```

### Tables

```html
<table border="1">
  <tr>
    <th>someheader</th>
    <th>someheader</th>
  </tr>
  <tr>
    <td>sometext</td>
    <td>sometext</td>
  </tr>
</table>
```

### Frames

```html
<frameset cols="25%,75%">
  <frame src="page1.htm">
  <frame src="page2.htm">
</frameset>
```

### Forms

```html
<form action="http://www.example.com/test.asp" method="post/get">
  <input type="text" name="lastname" value="Nixon" size="30" maxlength="50" />
  <input type="password" />
  <input type="checkbox" checked="checked" />
  <input type="radio" checked="checked" />
  <input type="submit" />
  <input type="reset" />
  <input type="hidden" />
  <select>
    <option>Apples</option>
    <option selected>Bananas</option>
    <option>Cherries</option>
  </select>

  <textarea name="Comment" rows="60" cols="20"></textarea>
</form>
```

### Entities

```html
&lt; is the same as < &gt; is the same as > &#169; is the same as ©
```

### Other Elements

```html
<!-- This is a comment -->
<blockquote>Text quoted from some source.</blockquote>
<address>
  Address 1<br />
  Address 2<br />
  City<br />
</address>
```

## HTML 标签

### 标题 h1~h6

标题（Heading）是通过 `<h1>` - `<h6>` 等标签进行定义的。

`<h1>` 定义最大的标题。`<h6>`定义最小的标题。

#### 实例

```html
<h1>This is a heading</h1>
<h2>This is a heading</h2>
<h3>This is a heading</h3>
```

_注释：浏览器会自动地在标题的前后添加空行。_

_注释：默认情况下，HTML 会自动地在块\*\*\*\*级元素前后添加一个额外的空行，比如段落、标题元素前后。_

#### 标题很重要

请确保将 HTML heading 标签只用于标题。不要仅仅是为了产生粗体或大号的文本而使用标题。

搜索引擎使用标题为您的网页的结构和内容编制索引。

因为用户可以通过标题来快速浏览您的网页，所以用标题来呈现文档结构是很重要的。

应该将 h1 用作主标题（最重要的），其后是 h2（次重要的），再其次是 h3，以此类推。

### 分区 div

```html
<div class="adiv"></div>
```

### 段落 p

**可以把 HTML 文档分割为若干段落。**

注释：浏览器会自动地在段落的前后添加空行。（`<p>` 是块级元素）

提示：使用空的段落标记 ` <p>``</p> ` 去插入一个空行是个坏习惯。用 `<br />` 标签代替它！（但是不要用 `<br />` 标签去创建列表。不要着急，您将在稍后的篇幅学习到 HTML 列表。）

```html
<p>This is a paragraph</p>
<p>This is another paragraph</p>
```

### 图像 img

```html
<img src="./images/xxx.png" alt="这是一张图片" />
```

### 水平线 hr

`<hr />` 标签在 HTML 页面中创建水平线。

hr 元素可用于分隔内容。

#### 实例

```html
<p>This is a paragraph</p>
<hr />
<p>This is a paragraph</p>
<hr />
<p>This is a paragraph</p>
```

提示：使用水平线 (`<hr>` 标签) 来分隔文章中的小节是一个办法（但并不是唯一的办法）。

## HTML 标签参考手册

| 标签            | 描述             |
| --------------- | ---------------- |
| `<html>`        | 定义 HTML 文档。 |
| `<body>`        | 定义文档的主体。 |
| `<h1>`to `<h6>` | 定义 HTML 标题   |
| `<hr>`          | 定义水平线。     |
| `<!-- -->`      | 定义注释。       |




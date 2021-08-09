# HTML & CSS 总结笔记的思路

[toc]

## HTML

HTML 是用来描述网页的一种语言。

- HTML 指的是**超文本标记语言** (Hyper Text Markup Language)
- **HTML 不是一种编程语言，而是一种标记语言** (markup language)
- 标记语言是一套标记标签 (markup tag)
- HTML 使用**标记标签**来描述网页

### HTML 基本语法

#### HTML 标签

HTML 标记标签通常被称为 HTML 标签 (HTML tag)。

- HTML 标签是由**尖括号**包围的关键词，比如 `<html>`
- HTML 标签通常是**成对出现**的，比如 `<b>` 和 `</b>`
- 标签对中的第一个标签是**开始标签**，第二个标签是**结束标签**
- 开始和结束标签也被称为**开放标签**和**闭合标签**

#### HTML 文档 = 网页

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

#### HTML 元素

HTML 元素指的是从开始标签（start tag）到结束标签（end tag）的所有代码。

| 开始标签                  | 元素内容            | 结束标签 |
| ------------------------- | ------------------- | -------- |
| `<p>`                     | This is a paragraph | `</p>`   |
| `<a href="default.htm" >` | This is a link      | `</a>`   |
| `<br />`                  |                     |          |

注释：开始标签常被称为开放标签（opening tag），结束标签常称为闭合标签（closing tag）。

##### HTML 元素语法

- HTML 元素以**开始标签**起始
- HTML 元素以**结束标签**终止
- **元素的内容**是开始标签与结束标签之间的内容
- 某些 HTML 元素具有**空内容（empty content）**
- 空元素**在开始标签中进行关闭**（以开始标签的结束而结束）
- 大多数 HTML 元素可拥有**属性**

##### 嵌套的 HTML 元素

大多数 HTML 元素可以嵌套（可以包含其他 HTML 元素）。

HTML 文档由嵌套的 HTML 元素构成。

HTML 文档实例

```html
<html>
  <body>
    <p>This is my first paragraph.</p>
  </body>
</html>
```

上面的例子包含三个 HTML 元素。

#### [行内元素与块级元素对比](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Inline_elements#行内元素与块级元素对比)

**行内元素特征：**

  **1. 设置宽高无效**
  **2. 对margin和padding仅设置左右方向有效，上下无效**
  **3. 不会自动进行换行**

- 内容

  一般情况下，行内元素只能包含数据和其他行内元素。

  而块级元素可以包含行内元素和其他块级元素。这种结构上的包含继承区别可以使块级元素创建比行内元素更” 大型 “的结构。

- 格式

  默认情况下，行内元素不会以新行开始，而块级元素会新起一行。

##### 块级元素

以下是 HTML 中所有的块级元素列表（虽然” 块级 “在新的 HTML5 元素中没有明确定义）

| 块级元素                                       | 作用                             | 块级元素             | 作用           |
| ---------------------------------------------- | -------------------------------- | -------------------- | -------------- |
| `<address>`                                    | 联系方式信息                     | `<blockquote>`       | 块引用         |
| `<h1>`, `<h2>`, `<h3>`, `<h4>`, `<h5>`, `<h6>` | 标题级别 1-6                     | `<form>`             | 表单           |
| `<dl>`                                         | 定义列表                         | `<hr>`               | 水平分割线     |
| `<dd>`                                         | 定义列表中定义条目描述           | `<ul>`               | 无序列表       |
| `<fieldset>`                                   | 表单元素分组                     | `<div>`              | 文档分区       |
| `<noscript>`                                   | 不支持脚本或禁用脚本时显示的内容 | `<ol>`               | 有序列表       |
| `<pre>`                                        | 预格式化文本                     | `<p>`                | 行             |
| `<table>`                                      | 表格                             | `<tfoot>`            | 表脚注         |
| `<header>` HTML5                               | 区段头或页头                     | `<footer>` HTML5     | 区段尾或页尾   |
| `<article>` HTML5                              | 文章内容                         | `<canvas>` HTML5     | 绘制图形       |
| `<aside>` HTML5                                | 伴随内容                         | `<audio>` HTML5      | 音频播放       |
| `<figure>` HTML5                               | 图文信息组 (参照 `<figcaption>`) | `<figcaption>` HTML5 | 图文信息组标题 |
| `<output>` HTML5                               | 表单输出                         | `<hgroup>` HTML5     | 标题组         |
| `<section>` HTML5                              | 一个页面区段                     | `<video>` HTML5      | 视频           |

##### 行内元素

下面的元素都是行内元素：

|            |              |             |            |
| ---------- | ------------ | ----------- | ---------- |
| `<b>`      | `<big>`      | `<i>`       | `<small>`  |
| `<tt>`     | `<abbr>`     | `<acronym>` | `<cite>`   |
| `<code>`   | `<dfn>`      | `<em>`      | `<kbd>`    |
| `<samp>`   | `<var>`      | `<a>`       | `<bdo>`    |
| `<br>`     | `<img>`      | `<map>`     | `<object>` |
| `<q>`      | `<script>`   | `<span>`    | `<sub>`    |
| `<sup>`    | `<button>`   | `<input>`   | `<label>`  |
| `<select>` | `<textarea>` |             |            |

#### HTML 注释

可以将注释插入 HTML 代码中，这样可以提高其可读性，使代码更易被人理解。浏览器会忽略注释，也不是显示它们。

注释是这样写的：

实例

```html
<!-- This is a comment -->
```

_注释：开始括号之后（左边的括号）需要紧跟一个叹号，结束括号之前（右边的括号）不需要。_

_提示：合理地使用注释可以对未来的代码编辑工作产生帮助。_

### HTML & HTML5 一些注意的地方

### HTML 属性

**属性为 HTML 元素提供附加信息。**

HTML 标签可以拥有**属性**。属性提供了有关 HTML 元素的**更多的信息**。

属性总是以名称/值对的形式出现，比如：**name="value"**。

属性总是在 HTML 元素的**开始标签**中规定。

属性实例

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

### HTML 速查手册

#### HTML Basic Document

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

#### Text Elements

```html
<p>This is a paragraph</p>
<br />
(line break)
<hr />
(horizontal rule)
<pre>This text is preformatted</pre>
```

#### Logical Styles

```html
<em>This text is emphasized</em>
<strong>This text is strong</strong>
<code>This is some computer code</code>
```

#### Physical Styles

```html
<b>This text is bold</b> <i>This text is italic</i>
```

#### Links, Anchors, and Image Elements

```html
<a href="http://www.example.com/">This is a Link</a
><a href="http://www.example.com/"><img src="URL" alt="Alternate Text" /></a
><a href="mailto:webmaster@example.com">Send e-mail</a>A named anchor:<a
  name="tips"
  >Useful Tips Section</a
><a href="#tips">Jump to the Useful Tips Section</a>
```

#### Unordered list

```html
<ul>
  <li>First item</li>
  <li>Next item</li>
</ul>
```

#### Ordered list

```html
<ol>
  <li>First item</li>
  <li>Next item</li>
</ol>
```

#### Definition list

```html
<dl>
  <dt>First term</dt>
  <dd>Definition</dd>
  <dt>Next term</dt>
  <dd>Definition</dd>
</dl>
```

#### Tables

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

#### Frames

```html
<frameset cols="25%,75%">  <frame src="page1.htm">  <frame src="page2.htm"></frameset>
```

#### Forms

```html
<form action="http://www.example.com/test.asp" method="post/get">
  <input type="text" name="lastname" value="Nixon" size="30" maxlength="50" />
  <input type="password" /> <input type="checkbox" checked="checked" />
  <input type="radio" checked="checked" /> <input type="submit" />
  <input type="reset" /> <input type="hidden" />
  <select>
    <option>Apples</option>
    <option selected>Bananas</option>
    <option>Cherries</option>
  </select>
  <textarea name="Comment" rows="60" cols="20"></textarea>
</form>
```

#### Entities

```html
&lt; is the same as < &gt; is the same as > &#169; is the same as ©
```

#### Other Elements

```html
<!-- This is a comment -->
<blockquote>Text quoted from some source.</blockquote>
<address>
  Address 1<br />
  Address 2<br />
  City<br />
</address>
```

## CSS

### CSS 基本语法

#### CSS 语法

**CSS 语法由三部分构成：选择器、属性和值：**

```css
selector {property: value}
```

选择器 (selector) 通常是你希望定义的 HTML 元素或标签，属性 (property)  是你希望改变的属性，并且每个属性都有一个值。属性和值被冒号分开，并由花括号包围，这样就组成了一个完整的样式声明（declaration）：

```CSS
body {color: blue}
```

上面这行代码的作用是将 body 元素内的文字颜色定义为蓝色。在上述例子中，body  是选择器，而包括在花括号内的的部分是声明。声明依次由两部分构成：属性和值，color 为属性，blue 为值。

#### 值的不同写法和单位

除了英文单词 red，我们还可以使用十六进制的颜色值 #ff0000：

```CSS
p { color: #ff0000; }
```

为了节约字节，我们可以使用 CSS 的缩写形式：

```CSS
p { color: #f00; }
```

我们还可以通过两种方法使用 RGB 值：

```CSS
p { color: rgb(255,0,0); }
p { color: rgb(100%,0%,0%); }
```

请注意，当使用 RGB 百分比时，即使当值为 0 时也要写百分比符号。但是在其他的情况下就不需要这么做了。比如说，当尺寸为 0 像素时，0 之后不需要使用  px 单位，因为 0 就是 0，无论单位是什么。

#### 记得写引号

提示：如果值为若干单词，则要给值加引号：

```CSS
p {font-family: "sans serif";}
```

#### 多重声明：

提示：如果要定义不止一个声明，则需要用分号将每个声明分开。下面的例子展示出如何定义一个红色文字的居中段落。最后一条规则是不需要加分号的，因为分号在英语中是一个分隔符号，不是结束符号。然而，大多数有经验的设计师会在每条声明的末尾都加上分号，这么的好处是，当你从现有的规则中增减声明时，会尽可能的减少出错的可能性。就像这样：

```CSS
p {text-align:center; color:red;}	
```

你应该在每行只描述一个属性，这样可以增强样式定义的可读性，就像这样：

```CSS
p {
  text-align: center;
  color: black;
  font-family: arial;
}
```

#### 空格和大小写

大多数样式表包含不止一条规则，而大多数规则包含不止一个声明。多重声明和空格的使用使得样式表更容易被编辑：

```CSS
body {
  color: #000;
  background: #fff;
  margin: 0;
  padding: 0;
  font-family: Georgia, Palatino, serif;
  }
```

是否包含空格不会影响 CSS 在浏览器的工作效果，同样，与 XHTML 不同，CSS 对大小写不敏感。不过存在一个例外：如果涉及到与 HTML  文档一起工作的话，class 和 id 名称对大小写是敏感的。

#### 选择器的分组

你可以对选择器进行分组，这样，被分组的选择器就可以分享相同的声明。用逗号将需要分组的选择器分开。在下面的例子中，我们对所有的标题元素进行了分组。所有的标题元素都是绿色的。

```CSS
h1,h2,h3,h4,h5,h6 {
  color: green;
  }
```

#### 继承及其问题

根据 CSS，子元素从父元素继承属性。但是它并不总是按此方式工作。看看下面这条规则：

```CSS
body {
     font-family: Verdana, sans-serif;
     }
```

根据上面这条规则，站点的 body 元素将使用 Verdana 字体（假如访问者的系统中存在该字体的话）。

通过 CSS 继承，子元素将继承最高级元素（在本例中是 body）所拥有的属性（这些子元素诸如 p, td, ul, ol, ul, li, dl,  dt,和 dd）。不需要另外的规则，所有 body 的子元素都应该显示 Verdana  字体，子元素的子元素也一样。并且在大部分的现代浏览器中，也确实是这样的。

但是在那个浏览器大战的血腥年代里，这种情况就未必会发生，那时候对标准的支持并不是企业的优先选择。比方说，Netscape 4  就不支持继承，它不仅忽略继承，而且也忽略应用于 body 元素的规则。IE/Windows 直到 IE6  还存在相关的问题，在表格内的字体样式会被忽略。我们又该如何是好呢？

#### 友善地对待Netscape 4

幸运地是，你可以通过使用我们称为 "Be Kind to Netscape 4" 的冗余法则来处理旧式浏览器无法理解继承的问题。

```CSS
body  {
     font-family: Verdana, sans-serif;
     }

p, td, ul, ol, li, dl, dt, dd  {
     font-family: Verdana, sans-serif;
     }
```

4.0 浏览器无法理解继承，不过他们可以理解组选择器。这么做虽然会浪费一些用户的带宽，但是如果需要对 Netscape 4  用户进行支持，就不得不这么做。

#### 继承是一个诅咒吗？

如果你不希望 "Verdana, sans-serif" 字体被所有的子元素继承，又该怎么做呢？比方说，你希望段落的字体是  Times。没问题。创建一个针对 p 的特殊规则，这样它就会摆脱父元素的规则：

```CSS
body  {
     font-family: Verdana, sans-serif;
     }

td, ul, ol, ul, li, dl, dt, dd  {
     font-family: Verdana, sans-serif;
     }

p  {
     font-family: Times, "Times New Roman", serif;
     }
```

### CSS & CSS3 要注意的地方

---

# 学习路线

## HTML

### HTML 常用属性

1. type
2. src
3. alt
4. href
5. rel
6. border
7. 等等

### HTML 常用标签

1. h1~h6

2. p

3. div

4. span

5. img

6. a

7. title

8. head

9. body

10. html

11. !doctype html

12. meta
    . lang
    . charset
13. style

14. script

### HTML5 常用标签

1. header H5
2. footer H5
3. aside H5
4. nav H5
5. article H5
6. video H5
7. audio H5
8. section H5

### Semantic(语义化) HTML

## CSS

### CSS 常用属性

- 背景颜色
- 文本
- 标签属性
- 等等

### CSS 常用选择器

- 类选择器
- 标签选择器
- ID 选择器
- 子代选择器
- 组合选择器
- 层级选择器
- 等等

### CSS 文档流

- 标准文档流
- 浮动文档流
- 定位文档流

### CSS 盒子模型

- 边框
- 外边距
- 内边距

### CSS3 新特性

- CSS3 动画
- CSS3 过渡
- 边框圆角
- 边框阴影
- 等等

### CSS 布局

- CSS Flex
- CSS Grid
- CSS Rem
- CSS 定位、浮动
- CSS 响应式布局

## 定位

![img](https://i.loli.net/2021/08/08/co8bJ34iAfvI5WU.png)

top,left,bottom,right

元素设置了position属性之后，就会激活4个css属性。

 **top,left,right,bottom,这些属性，不设置的时候默认值是auto，会尽量保持原来的位置，而且，top，left的优先级要大于bottom和right**

### 定位 position 的属性

1. position: static

   static是position默认的取值。

2. position: absolute

   绝对定位

   **相对于它的第一个position不为static的父元素，如果没有，就相对于body**，你问我什么叫**第一个**?第一个的意思是，如果这个元素的父元素的父元素，也就是**这个元素的爷爷元素的position不是static，但是父元素是static，那么这个元素的top相对于爷爷元素定位**
   
   **设置absolute的元素会脱离文档流。**
   
   **设置absolute的元素在同时设置top和bottom的情况下，以top的取值来设定竖直方向的布局。**
```html
<div class = "yellow">
  <div class="red">
    <div class = "blue"></div>
  </div>
</div>
```
```css
body {
	background-color: white;
}

.yellow {

  margin-left: 100px;
  margin-top: 100px;
  /**爷爷元素position为absolute**/
  position: absolute;
	background-color: #E6A23C;
  width: 400px;
  height:400px;
}

.red {
  /**父元素position为static**/
  position:static;
  margin-left: 100px;
  margin-top: 100px;
	background-color: #F56C6C;
  width: 200px;
  height:200px;
}

/**css中注释的方式和html不一样，这种方式才能写css的注释，不要写错了**/
.blue {
  position: absolute;
  top: 50px;
  left: 50px;
	background-color: #409EFF;
  width: 100px;
  height:100px;
}
```
![image-20210808232605101](https://i.loli.net/2021/08/08/MJpQTPgIxiGCwyf.png)

3. position: relative

   相对定位，和absolute差不太多，但是有一个**特异性**——**移动元素后，元素本来占有的位置会保留，然后会相对原来的位置定位**

   ```html
   <div id="box1"></div>
   <div id="box2"></div>
   <div id="box3"></div>
   ```

   ```css
   * {
     background: white;
     margin: 0;
   }
   
   #box1 {
     width: 100px;
     height: 100px;
     background: red;
   }
   
   #box2 {
     width: 100px;
     height: 100px;
     background: yellow;
     position:relative;
     top:100px;
     left:100px;
   }
   
   #box3 {
     width: 100px;
     height: 100px;
     background: blue;
   }
   ```

   ![image-20210808233046480](https://i.loli.net/2021/08/08/LAK9G1dh8VrP47u.png)

4. position: fixed

   相对浏览器窗口定位

   无论你怎么滚动页面，调戏滚动条和鼠标滚轮，它都在浏览器的那个位置，就是不动。

## 浮动

**float属性有三个取值：1.none；2.right；3.left；**

**float**属性就俩常用的值（left和right），把元素浮到页面的左边或者右边



## Flex布局

**flex布局**——一种**弹性盒模型布局**，它可以把「块」元素变得有弹性，一举解决大部分布局问题

flex布局的元素会把自己的一级子元素排成一行，并将他们变成可以伸缩，易排列的盒子

**父元素是默认充满宽度的**

**display: flex**，激活flex布局

flex控制横向延展还是纵向延展的属性是flex-direction

```html
<div class="box-container">
  <div id="box1"></div>
  <div id="box2"></div>
  <div id="box3"></div>
</div>
```

```css
body {
  background: white;
  margin: 0;
}

.box-container {
  display:flex;
}

#box1 {
  width: 100px;
  height: 100px;
  background: red;
}

#box2 {
  width: 100px;
  height: 100px;
  background: yellow;
}

#box3 {
  width: 100px;
  height: 100px;
  background: blue;
}
```
![image-20210808234044065](https://i.loli.net/2021/08/08/zFA3VMC5OTwsdmL.png)
![img](https://i.loli.net/2021/08/08/5vYFPgeL6WnAUER.png)



### 两个用的最多的属性（都是设置在父元素上）

1. justify-content

   这个元素就是设置红黄蓝3个色块的flex主轴方向（横向）位置

   它常用的取值有5个

   **1. flex-start**：左对齐
   **2. flex-end**：右对齐
   **3. center**：居中
   **4. space-between**：两端对齐，元素之间的间隔都相等
   **5. space-around**：每个项目两侧的间隔相等。所以，元素之间的间隔比元素与边框的间隔大一倍

2. align-items

   align-items属性定义项目在交叉轴（纵向上）上如何对齐
   
   常用的取值就只有3个
   
   **1. flex-start**：上对齐
   **2. flex-end**：下对齐
   **3. center**：居中
   
   align-items的属性值不包含，space-between，space-around


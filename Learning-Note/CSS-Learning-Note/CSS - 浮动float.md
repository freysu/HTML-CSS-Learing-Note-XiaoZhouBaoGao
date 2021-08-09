## HTML 元素的分类

### 块元素

可以设置宽度和高度，独立成行。如 h1-6，p,div,ul,li。

### 行内元素

又称内联元素、行级元素，

不可以设置宽度和高度，不独立成行。如 a，span。

### 行内块元素

可以设置宽度和高度，不独立成行。如 img,input,button。

## display 属性

block:转换为块元素

inline:转换为行内元素

inline-block:转换为行内块元素

none:隐藏元素

## 两个 DIV 在同一行显示

将元素设置为浮动元素（float），块元素可以在同一行显示。

**float属性有三个取值：**

*1.none；2.right；3.left；**

**float**属性就俩常用的值（left和right），把元素浮到页面的左边或者右边

```css
float: left;

float: right;

float: none;
```

## 浮动元素的特性

脱离文档流

## 空 div 清除浮动

```css
clear: both;
```

## 伪元素清除浮动

```css
/* ② 两个空的div清楚浮动 伪元素清楚浮动 */
.clear::before,
.clear::after {
  /* 空内容 */
  content: "";
  /* 转换成块元素 */
  display: block;
  clear: both;
}
```

## 示例代码

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <style>
      a,
      #h1-1 {
        width: 100px;
        height: 100px;
        border: 1px solid red;
        display: none;
      }
      img {
        width: 100px;
      }
    </style>
  </head>
  <body>
    <a id="h1-1">hello h1-1</a>
    <a>hello h1-2</a>
    <img src="http://img.xiaozhoubg.com/FnhSmWuOhn90sV3WHSFTMsXKm5n9" alt="" />
    <img src="http://img.xiaozhoubg.com/FnhSmWuOhn90sV3WHSFTMsXKm5n9" alt="" />
  </body>
</html>
```

```html
<!-- 
①：空div清楚浮动
②：伪元素清楚浮动：两个空的div清楚浮动
-->
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <style>
      /* ② 两个空的div清楚浮动 伪元素清楚浮动 */
      .clear::before,
      .clear::after {
        /* 空内容 */
        content: "";
        /* 转换成块元素 */
        display: block;
        clear: both;
      }
      .content {
        width: 300px;
        height: 200px;
        border: 1px solid red;
        /* 设置元素浮动 */
        float: left;
      }
      .aside {
        width: 100px;
        height: 200px;
        border: 1px solid blue;
        /* 设置元素浮动 */
        float: left;
      }
      .box {
        width: 400px;
        height: 400px;
        background-color: yellow;
      }
      /* ①
        .clear{
            空div清楚浮动，清楚之前浮动的不良影响
            clear:both;
        } */
    </style>
  </head>
  <body>
    <!-- ② 容器加个Clear -->
    <div class="container clear">
      <div class="content">内容</div>
      <div class="aside">边栏</div>
    </div>
    <!-- ① 空div清楚浮动
    <div class="clear"></div> -->
    <div class="box"></div>
  </body>
</html>
```

## 作业 1

### html 文件

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <link rel="stylesheet" href="style/css-浮动布局-作业.css" />
  </head>
  <body>
    <ul class="list">
      <li class="clear">
        <div class="pic">
          <img
            src="http://img.xiaozhoubg.com/FiOyW_stqM9JdK9dg0Ou0jKb2rFG"
            alt=""
          />
        </div>
        <div class="title"></div>
        <h3>前端学习开发手册</h3>
        <p>2021年7月18日</p>
        <a href="">阅读</a>
      </li>
      <li class="clear">
        <div class="pic">
          <img
            src="http://img.xiaozhoubg.com/FiOyW_stqM9JdK9dg0Ou0jKb2rFG"
            alt=""
          />
        </div>
        <div class="title"></div>
        <h3>前端学习开发手册</h3>
        <p>2021年7月18日</p>
        <a href="">阅读</a>
      </li>
    </ul>
  </body>
</html>
```

### css 文件

css-浮动布局-作业.css

```css
* {
  margin: 0px;
  padding: 0px;
}
.list .pic img {
  width: 200px;
  height: 150px;
}
.pic {
  width: 200px;
  float: left;
}
.title {
  width: 300px;
  float: left;
}
.clear::after,
.clear::before {
  content: "";
  display: block;
  clear: both;
}
.title a {
  display: block;
  width: 80px;
  height: 30px;
  background-color: green;
  color: white;
  text-align: center;
  text-decoration: none;
  line-height: 30px;
}
```

## 作业 2

### html 文件

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <link rel="stylesheet" href="style/css-浮动布局-作业2.css" />
  </head>
  <body>
    <div class="thhead">
      <p class="selected">精选手册 <a href=""></a></p>
      <a href="/book" class="seemore">查看更多</a>
      <img class="seemore_img" src="../../images/右箭头.png" alt="" />
    </div>
    <ul>
      <li class="web">
        <a href="/book/bookDetail/79">
          <img
            class="javascript"
            src="http://img.xiaozhoubg.com/FiOyW_stqM9JdK9dg0Ou0jKb2rFG"
            alt=""
          />
          <div class="web_container">
            <p class="web-book">前端开发学习手册</p>
            <p class="data">2020-06-09</p>
            <button class="read">阅读</button>
          </div>
        </a>
      </li>
      <li class="web">
        <a href="/book/bookDetail/77">
          <img
            class="javascript"
            src="http://img.xiaozhoubg.com/FkUt9OW9MqOXUed2HWJMJzN3Ppv3"
            alt=""
          />
          <div class="web_container">
            <p class="web-book">Java 开发学习手册基础篇</p>
            <p class="data">2020-06-09</p>
            <button class="read">阅读</button>
          </div>
        </a>
      </li>
      <li class="web">
        <a href="/book/bookDetail/82">
          <img
            class="javascript"
            src="http://img.xiaozhoubg.com/FnhSmWuOhn90sV3WHSFTMsXKm5n9"
            alt=""
          />
          <div class="web_container">
            <p class="web-book">程序员面试题</p>
            <p class="data">2020-08-12</p>
            <button class="read">阅读</button>
          </div>
        </a>
      </li>
    </ul>
  </body>
</html>
```

### css 文件

css-浮动布局-作业 2.css

```css
* {
  margin: 0;
  padding: 0;
}
.thhead .selected {
  float: left;
  flex: 11;
  margin-left: 16px;
  font-size: 20px;
  width: 100px;
}
.thhead .seemore {
  float: right;
  flex: 1;
  color: rgb(158, 158, 158);
  font-size: 16px;
  width: 120px;
}
.seemore_img {
  opacity: 0.5;
  margin-top: 2px;
  margin-right: 26px;
}
.thhead {
  display: flex;
  align-items: center;
  width: 953px;
  height: 50px;
  background-color: #ffffff;
  /* margin-left: 100px; */
}
.web {
  width: 953px;
  height: 200px;
  /* border: 1px solid red; */
  float: left;
  margin-top: 10px;
  background-color: #ffffff;
  /* margin-left: 100px; */
}
li {
  list-style-type: none;
}
a {
  /* display: block; */
  /* width: 100%; */
  /* display: inline-flex; */
  text-decoration: none;
  color: #000000;
  -webkit-tap-highlight-color: rgba(255, 255, 255, 0);
  -webkit-user-select: none;
  -moz-user-focus: none;
  -moz-user-select: none;
}
a:link {
  text-decoration: none;
}
.web .javascript {
  width: 230px;
  height: 150px;
  float: left;
  margin-top: 25px;
  margin-left: 16px;
}
.web_container {
  display: flex;
  width: 670px;
  overflow: hidden;
  flex-direction: column;
  margin-left: 25px;
  float: left;
}
.web .web-book {
  font-size: 18px;
  margin-top: 35px;
}
.web .data {
  margin-top: 11px;
  color: #c9c9c9;
}
.web .read {
  width: 88px;
  height: 40px;
  margin-top: 36px;
  border-radius: 5px;
  background-color: #e3f0fc;
  border: 1px solid #e3f0fc;
  color: #7db4fe;
}
```

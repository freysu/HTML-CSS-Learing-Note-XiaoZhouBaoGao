## 还原设计稿

## VsCode 中使用 Emmet 神器快速编写 HTML 代码

语法基本规则如下:

```Emmet
E 代表HTML标签。
E#id 代表id属性。
E.class 代表class属性。
E[attr=foo] 代表某一个特定属性。
E{foo} 代表标签包含的内容是foo。
E>N 代表N是E的子元素。
E+N 代表N是E的同级元素。
E^N 代表N是E的上级元素。
```

例如，

- 生成 ul 代码，类名为 nav

  ```Emmet
  ul.nav
  ```

- 生成一个包含 li 的 ul

  ```Emmet
  ul>li
  ```

- 生成 5 个 li

  ```Emmet
  li*5
  ```

- 生成指定内容的 p

  ```Emmet
  p{指定内容}
  ```

- 把以上结合起来如下

  ```Emmet
  ul.nav>li*5>a
  ```

## 示例代码

### index.html

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <link rel="stylesheet" href="css/index.css" />
  </head>
  <body>
    <!-- 头部导航栏 -->
    <div class="header">
      <div class="header_content">
        <div class="logo">
          <img src=".\images\logo.jpg" alt="" />
        </div>
        <!-- VsCode 中使用 Emmet 神器快速编写 HTML 代码-->
        <!-- ul.nav生成ul代码，类名为nav -->
        <!-- ul>li 生成一个包含li的ul -->
        <!-- li*5 生成5个li -->
        <!-- ul.nav>li*5>a -->
        <ul class="nav">
          <li><a href="#">首页</a></li>
          <li><a href="#">学习手册</a></li>
          <li><a href="#">技术博客</a></li>
          <li><a href="#">教学视频</a></li>
          <li><a href="#">资源下载</a></li>
        </ul>
      </div>
    </div>
    <!-- 内容 -->
    <div class="container">
      <!-- 主内容 -->
      <div class="content">
        <h1>你好</h1>
        <h1>你好</h1>
        <h1>你好</h1>
        <h1>你好</h1>
        <h1>你好</h1>
      </div>
      <!-- 侧边栏 -->
      <div class="slider">
        <h1>你好</h1>
        <h1>你好</h1>
        <h1>你好</h1>
        <h1>你好</h1>
        <h1>你好</h1>
      </div>
    </div>
  </body>
</html>
```

### index.css

```css
*{
    margin:0;
    padding:0;
}
.header{
    /* 导航栏高度 */
    height:60px;s
    /* 初学者建议先加背景色 后期熟练可以不用写 */
    /* background-color:yellow; */
}
.header .header_content{
    width:1260px;
    /* background-color:green; */
    margin:0 auto;
    height:100%;
}
.header .header_content .logo{
    margin-top:16px;
    float:left;
}
.header .header_content .nav li{
    list-style: none;
    float:left;
    width:114px;
    height:60px;
    line-height:60px;
    text-align:center;
}
/* 伪类选择器的应用 选择鼠标指针浮动在其上的元素 */
.header .header_content .nav li:hover{
    border-bottom: 2px solid #0084ff;
    /* 边框在盒子的内部显示，防止内容部分被挤散 */
    box-sizing: border-box;
}
.header .header_content .nav li a{
    color:black;
    text-decoration: none;
}
.container{
    /* height不用设置 */
    /* 一般设计师都会设成整数 */
    width:1260px;
    /* background-color: blue; */
    /* 设宽度之后才可以用这个方法居中 */
    margin:0 auto;
}
.container .content{
    width:956px;
    float:left;
}
.container .slider{
    width:290px;
    float:right;
}
```

## 作业

### index.html

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <link rel="stylesheet" href="css/index.css" />
  </head>
  <body>
    <!-- 头部 -->
    <div class="header">
      <div class="header_logo">
        <img src="images/logo.jpg" alt="" />
      </div>
      <ul class="nav">
        <li><a href="#">首页</a></li>
        <li><a href="#">学习手册</a></li>
        <li><a href="#">技术博客</a></li>
        <li><a href="#">教学视频</a></li>
        <li><a href="#">资源下载</a></li>
      </ul>
      <div class="header_search">
        <input type="text" placeholder="搜索" />
      </div>
      <div class="header_login">
        <a href="#">登录</a>
      </div>
    </div>
    <!-- 主体 -->
    <div class="container">
      <!-- 主内容 -->
      <div class="content">
        <!-- 精选手册 -->
        <div class="list_title">
          <p class="list_title_p">精选手册</p>
          <a href="#">查看更多 ></a>
        </div>
        <ul class="list_description">
          <li class="list clear">
            <img class="list_description_img" src="images/fepic.png" alt="" />
            <div class="list_description_text">
              <p class="title">前端开发学习手册</p>
              <p class="time">2019.12.23</p>
              <a href="#">阅读</a>
            </div>
          </li>
          <li class="list clear">
            <img class="list_description_img" src="images/fepic.png" alt="" />
            <div class="list_description_text">
              <p class="title">前端开发学习手册</p>
              <p class="time">2019.12.23</p>
              <a href="#">阅读</a>
            </div>
          </li>
        </ul>
        <!-- 精选博客 -->
        <div class="list_title">
          <p class="list_title_p">精选博客</p>
          <a href="#">查看更多 ></a>
        </div>
        <ul class="list_description">
          <li class="list clear">
            <img class="list_description_img" src="images/fepic.png" alt="" />
            <div class="list_description_text">
              <p class="title">前端开发学习手册</p>
              <p class="time">2019.12.23</p>
              <p class="dsc">
                最近接触比较多的新手程序员和准程序员，和他们交流的过程中，我发现了一些通用问题，今天把这些问题整理出来，希望可以<br />帮助更多的朋友们。
              </p>
            </div>
          </li>
          <li class="list clear">
            <img class="list_description_img" src="images/fepic.png" alt="" />
            <div class="list_description_text">
              <p class="title">前端开发学习手册</p>
              <p class="time">2019.12.23</p>
              <p class="dsc">
                最近接触比较多的新手程序员和准程序员，和他们交流的过程中，我发现了一些通用问题，今天把这些问题整理出来，希望可以<br />帮助更多的朋友们。
              </p>
            </div>
          </li>
        </ul>
        <!-- 精选视频 -->
        <div class="list_title">
          <p class="list_title_p">精选视频</p>
          <a href="#">查看更多 ></a>
        </div>
        <ul class="list_description">
          <li class="list clear">
            <img class="list_description_img" src="images/git.png" alt="" />
            <div class="list_description_text">
              <p class="title">Git</p>
              <p class="time">2019.12.23</p>
              <a href="#">观看</a>
            </div>
          </li>
          <li class="list clear">
            <img class="list_description_img" src="images/git.png" alt="" />
            <div class="list_description_text">
              <p class="title">Git</p>
              <p class="time">2019.12.23</p>
              <a href="#">观看</a>
            </div>
          </li>
        </ul>
        <!-- 更多内容敬请期待 -->
        <div class="list_title">
          <p class="list_title_pmore">更多精彩内容敬请期待~</p>
        </div>
      </div>
      <!-- 右侧栏 -->
      <div class="slider">
        <div class="slider_part1">
          <!-- 轮播图 -->
          <div class="lunbo">
            <img src="images/fepic.png" alt="" class="slider_photo" />
          </div>
          <!-- 精选 -->
          <p class="rcm_title">精选</p>
          <ul class="rcm_list">
            <li class="rcm_list_one">
              <img class="rcm_list_pic" src="images/fepic2.png" alt="" />
              <div class="rcm_list_dsc">
                <p class="title">前端开发学习手册</p>
                <a href="#">阅读</a>
              </div>
            </li>
          </ul>
          <!-- 问题 -->
          <ul class="faq_list">
            <li class="faq_dsc">
              <a href="#">编程学习的五大误区，你占了几点？</a>
            </li>
            <li class="faq_dsc">
              <a href="#">编程学习的五大误区，你占了几点？</a>
            </li>
            <li class="faq_dsc faq_dsc_3">
              <a href="#">编程学习的五大误区，你占了几点？</a>
            </li>
          </ul>
        </div>
        <div class="right_footer">
          <p class="footer_p">晓舟报告 | 移动端</p>
          <p class="footer_p">团队介绍</p>
          <p class="footer_p">晓舟报告官方网站</p>
          <p class="footer_p">©2019 冀ICP备18023262号-4</p>
        </div>
      </div>
    </div>
    <div class="fixed_btn">
      <img class="contact" src="images/联系人.png" alt="" title="联系人" />
      <img class="wechat" src="images/微信.png" alt="" title="微信" />
      <a href="#">
        <img class="btu" src="images/返回顶部.png" alt="" title="返回顶部" />
      </a>
    </div>
  </body>
</html>
```

### index.css

```css
* {
  margin: 0;
  padding: 0;
}
.container .content .clear::after,
.container .content .clear::before {
  content: "";
  display: block;
  clear: both;
}
.header {
  height: 60px;
  width: 1262px;
  margin: 0 auto;
}
.header .header_logo {
  float: left;
  line-height: 60px;
}
.header .nav {
  float: left;
}
.header .nav li {
  list-style: none;
  float: left;
  line-height: 60px;
  text-align: center;
  width: 116px;
}
.header .nav li a {
  text-decoration: none;
  color: black;
}
.header .nav li:hover {
  border-bottom: 1px solid blue;
  box-sizing: border-box;
}
.header .header_search {
  float: left;
  margin-left: 125px;
  line-height: 60px;
}
.header .header_login a {
  margin-left: 68px;
  float: left;
  text-decoration: none;
  color: white;
  background-color: blue;
  text-align: center;
  line-height: 60px;
}

/* 主体 */
.container {
  width: 1262px;
  margin: 0 auto;
}
/* 左边主内容 */
.container .content {
  float: left;
  margin-top: 15px;
  width: 957px;
  margin-right: 14px;
}
/* 列表标题 */
.container .content .list_title {
  float: left;
  width: 957px;
  height: 50px;
  border: 1px solid blue;
  padding-right: 20px;
  padding-left: 25px;
  /* margin-top:10px; */
  margin-bottom: 10px;
  text-align: center;
  line-height: 50px;
  box-sizing: border-box;
}
.container .content .list_title .list_title_p {
  float: left;
}
.container .content .list_title .list_title_pmore {
  font-size: 16px;
  color: #808080;
}
/* 查看更多 */
.container .content .list_title a {
  float: right;
  text-decoration: none;
  color: #808080;
}
/* 列表内容 */
.container .content .list_description {
  width: 957px;
  float: left;
  list-style: none;
}
.container .content .list_description .list {
  margin-bottom: 10px;
  border: 1px solid blue;
}
/* 封面图 */
.container .content .list_description .list_description_img {
  /* border:1px solid red; */
  float: left;
  padding-bottom: 25px;
  margin-top: 25px;
  margin-left: 15px;
}
/* 名字时间按钮 */
.container .content .list_description .list_description_text {
  /* border:1px solid blue; */
  /* background-color: blue; */
  float: left;
  /* padding-bottom:25px; */
  margin-left: 25px;
  padding-top: 35px;
}
.container .content .list_description .list_description_text .title {
  font-size: 18px;
  margin-bottom: 15px;
}
.container .content .list_description .list_description_text .time {
  font-size: 16px;
  color: #b2b2b2;
  margin-bottom: 23px;
}
.container .content .list_description .list_description_text a {
  display: block;
  /* box-sizing: border-box; */
  font-size: 14px;
  color: #0084ff;
  width: 90px;
  height: 41px;
  text-align: center;
  line-height: 41px;
  background-color: #e3f0fc;
  text-decoration: none;
}
.container .content .list_description .list_description_text .dsc {
  width: 660px;
  font-size: 16px;
  color: #666666;
}

/* 右侧栏 */
.container .slider {
  width: 291px;
  float: right;
  /* border:1px solid blue; */
  box-sizing: border-box;
  margin-top: 15px;
}
.container .slider_part1 {
  float: left;
  border: 1px solid blue;
}
.container .slider .lunbo .slider_photo {
  width: 290px;
  height: 180px;
}
.container .slider .rcm_title {
  padding-left: 22px;
  padding-bottom: 15px;
}
.container .slider .rcm_list .rcm_list_one {
  list-style: none;
  border-top: 1px solid #e5e5e5;
  margin-left: 10px;
  margin-right: 10px;
}
.container .slider .rcm_list_pic {
  float: left;
  margin-left: 12px;
  margin-top: 15px;
  margin-bottom: 10px;
}
.container .slider .rcm_list_dsc {
  float: left;
  margin-left: 15px;
  margin-top: 25px;
  margin-bottom: 10px;
}
.container .slider .rcm_list_dsc .title {
  margin-bottom: 25px;
}
.container .slider .rcm_list_dsc a {
  display: block;
  /* box-sizing: border-box; */
  font-size: 14px;
  color: #0084ff;
  width: 58px;
  height: 27px;
  text-align: center;
  line-height: 27px;
  background-color: #e3f0fc;
  text-decoration: none;
}
.container .slider .faq_list {
  width: 270px;
  height: 46px;
  margin: 0 auto;
}
.container .slider .faq_list .faq_dsc {
  list-style: none;
  border-top: 1px solid #e5e5e5;
  margin-left: 12px;
  margin-right: 10px;
  float: left;
}
.container .slider .faq_list .faq_dsc a {
  font-size: 14px;
  color: black;
  text-align: center;
  line-height: 46px;
}
.container .slider .faq_list .faq_dsc_3 {
  padding-bottom: 30px;
}
.container .slider .right_footer {
  font-size: 13px;
  float: left;
  margin-top: 20px;
}
.container .slider .right_footer .footer_p {
  margin-top: 12px;
  width: 269px;
  height: 20px;
  color: #b2b2b2;
}
.fixed_btn {
  width: 40px;
  height: 40px;
  position: fixed;
  bottom: 100px;
  left: 60%;
  margin-left: 500px;
}
.contact:hover {
  border: 1px solid blue;
}
.wechat:hover {
  border: 1px solid red;
}
```

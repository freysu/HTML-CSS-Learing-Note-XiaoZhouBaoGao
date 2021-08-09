## HTML5 介绍

HTML5 是超文本标记语言（HTML）的第五次重大修改，可以简单的理解为是 HTML 的第五个大版本。

- 某些情况会将 HTML5 简称为 H5。

- 某些情况说 HTML5（H5）表示的是 HTML 的第五个版本。

- 某些情况说 HTML5（H5）表示的是移动端的网页效果。

- 某些情况说 HTML5（H5）表示的是 HTML5、CSS3、以及 HTML5 配套的 JavaScript 接口。例如操作视频，操作画布，获取地理信息等。

- 某些情况说 HTML5（H5）表示的是手机端整屏的轮播图效果。

## HTML5 新特性

1. 布局元素

2. 媒体元素

3. 画布（`<canvas>`），例如刮刮乐。

4. SVG（定义矢量图）

5. 表单新特性

### 布局元素

布局元素相当于一个有语义的 div 。

以下为常用的 HTML5 元素

header：网页头部

nav：导航栏

aside：侧标栏

article：显示文章

section：布局的一部分

footer：网页页脚

### 媒体元素

#### 1. audio 音频

audio 标签

src 属性：音频地址

controls 属性：显示控制面板

muted 属性：静音，新版音频、视频先静音才能自动播放，旧版的可以直接自动播放

```html
<!-- 音频播放器默认效果 -->
<audio src="media/again.mp3" controls></audio>
```

#### 2. video 视频

video 标签

src 属性：视频地址

controls 属性：显示控制面板

autoplay 属性：视频自动播放

muted 属性：静音，新版音频、视频先静音才能自动播放，旧版的可以直接自动播放

```html
<video src="media/video.mp4" controls autoplay muted></video>
```

#### 媒体元素属性

一、controls 显示控制面板

二、autoplay 视频自动播放

三、muted 静音

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
      header {
        width: 800px;
        border: 1px solid red;
        margin: 0 auto;
      }
      video {
        width: 50%;
      }
    </style>
  </head>
  <body>
    <header>logo</header>
    <!-- 播放器默认效果 -->
    <audio src="media/again.mp3" controls></audio>
    <video src="media/video.mp4" controls autoplay muted></video>
  </body>
</html>
```

## 作业 晓舟报告视频页

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="css/videobrowserpage.css">
</head>

<body>
    <!-- 头部 -->
    <div class="header">
        <div class="header_logo">
            <img src="images/logo.jpg" alt="">
        </div>
        <ul class="nav">
            <li><a href="#">首页</a></li>
            <li><a href="#">学习手册</a></li>
            <li><a href="#">技术博客</a></li>
            <li><a href="#">教学视频</a></li>
            <li><a href="#">资源下载</a></li>
        </ul>
        <div class="header_search">
            <input type="text" placeholder="搜索">
        </div>
        <div class="header_account">
            <a href="#">
                <img src="images/头像.png" alt="">
            </a>
        </div>
    </div>
    <!-- 主体 -->
    <div class="container">
        <!-- 主内容 -->
        <div class="content">
            <div class="video_part ">
                <div class="video_dsc clear">
                    <p class="video_title">Git（标题）</p>
                    <p class="video_favour">收藏</p>
                </div>
                <p class="video_time">2019.12.23</p>
                <video class="video_v" src="media/video.mp4" controls></video>
                <!-- 更多内容敬请期待 -->
                <div class="video_more ">
                    <p class="video_pmore">更多精彩内容敬请期待~</p>
                </div>
            </div>
        </div>
        <!-- 右侧栏 -->
        <div class="slider">
            <div class="slider_part1">
                <!-- VIP -->
                <div class="vip_isnot">
                    <a href="" class="vip_watch">开通VIP观看</a>
                </div>
                <!-- 视频集数列表 -->
                <div class="video_jishulist">
                    <div class="clear">
                        <p class="video_jishulist_title">选集</p>
                        <p class="video_jishulist_pernumber">1/15</p>
                    </div>
                    <div>
                        <img src="images/教学视频滚动条_03.jpg" alt="" class="scroll_button">
                        <p class="video_jishulist_number_now">
                            <img class="play_now_img" src="images/play_button_now.png" alt="">
                            Git（标题）
                        </p>
                        <p class="video_jishulist_number">Git（标题）</p>
                        <p class="video_jishulist_number">Git（标题）</p>
                        <p class="video_jishulist_number">Git（标题）</p>
                        <p class="video_jishulist_number">Git（标题）</p>
                        <p class="video_jishulist_number">Git（标题）</p>
                        <p class="video_jishulist_number">Git（标题）</p>
                        <p class="video_jishulist_number">Git（标题）</p>
                        <p class="video_jishulist_number">Git（标题）</p>
                        <p class="video_jishulist_number">Git（标题）</p>
                    </div>
                </div>
            </div>
            <div class="slider_part2">
                <!-- 轮播图 -->
                <div class="lunbo">
                    <img src="images/fepic.png" alt="" class="slider_photo">
                </div>
                <!-- 精选 -->
                <p class="rcm_title">推荐视频</p>
                <ul class="rcm_list ">
                    <li class="rcm_list_one clear">
                        <img class="rcm_list_pic" src="images/git1.png" alt="">
                        <div class="rcm_list_dsc">
                            <p class="title">Git</p>
                            <!-- <a href="#">阅读</a> -->
                        </div>
                    </li>
                    <li class="rcm_list_one clear">
                        <img class="rcm_list_pic" src="images/git1.png" alt="">
                        <div class="rcm_list_dsc">
                            <p class="title">Git</p>
                            <!-- <a href="#">阅读</a> -->
                        </div>
                    </li>
                    <li class="rcm_list_one clear">
                        <img class="rcm_list_pic" src="images/git1.png" alt="">
                        <div class="rcm_list_dsc">
                            <p class="title">Git</p>
                            <!-- <a href="#">阅读</a> -->
                        </div>
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
        <div class="fixed_btn">
            <img class="contact" src="images/联系人.png" alt="" title="联系人">
            <img class="wechat" src="images/微信.png" alt="" title="微信">
            <a href="#">
                <img class="btu" src="images/返回顶部.png" alt="" title="返回顶部">
            </a>
        </div>
</body>

</html>
```

```css
* {
  margin: 0;
  padding: 0;
}
.clear::before,
.clear::after {
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
  margin-top: 10px;
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
.header .header_account {
  margin-left: 20px;
  margin-top: 10px;
  float: left;
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
.container .content .video_part {
  border: 1px solid red;
}
.container .content .video_part .video_dsc .video_title {
  float: left;
  margin-top: 20px;
  margin-left: 20px;
  font-size: 18px;
}
.container .content .video_part .video_dsc .video_favour {
  font-size: 16px;
  color: #b2b2b2;
  float: right;
  margin-top: 20px;
  margin-right: 30px;
}
.container .content .video_part .video_time {
  float: left;
  font-size: 16px;
  margin-top: 7px;
  margin-left: 20px;
  color: #b2b2b2;
}
.container .content .video_part .video_v {
  width: 915px;
  margin-top: 22px;
  margin-left: 20px;
  margin-bottom: 20px;
  margin-right: 20px;
}
.container .content .video_part .video_more {
  float: left;
  width: 957px;
  height: 50px;
  border: 1px solid blue;
  padding-right: 20px;
  padding-left: 25px;
  margin-top: 10px;
  margin-bottom: 10px;
  text-align: center;
  line-height: 50px;
  box-sizing: border-box;
}
.container .content .video_part .video_pmore {
  font-size: 16px;
  color: #808080;
}

/* 右侧栏 */
.container .slider {
  width: 291px;
  float: right;
  box-sizing: border-box;
  margin-top: 15px;
}
.container .slider_part1 .vip_isnot {
  background-color: #0084ff;
  width: 290px;
  height: 50px;
  margin-bottom: 10px;
}
.container .slider_part1 .vip_watch {
  display: block;
  color: white;
  text-decoration: none;
  text-align: center;
  line-height: 50px;
}
.container .slider_part1 .video_jishulist {
  width: 290px;
  box-sizing: border-box;
  border: 1px solid red;
  margin-bottom: 10px;
  position: relative;
}
.container .slider_part1 .video_jishulist .scroll_button {
  position: absolute;
  top: 50px;
  left: 285px;
}
.container .slider_part1 .video_jishulist .video_jishulist_title {
  float: left;
  font-size: 18px;
  margin-top: 15px;
  margin-left: 22px;
  font-size: 18px;
}
.container .slider_part1 .video_jishulist .video_jishulist_pernumber {
  float: right;
  font-size: 14px;
  color: #b2b2b2;
  margin-top: 17px;
  margin-right: 18px;
}
.container .slider_part1 .video_jishulist .video_jishulist_number_now {
  color: #0084ff;
  font-size: 16px;
  margin-top: 20px;
  margin-bottom: 20px;
  margin-left: 23px;
}
.container
  .slider_part1
  .video_jishulist
  .video_jishulist_number_now
  .play_now_img {
  margin-right: 10px;
}
.container .slider_part1 .video_jishulist .video_jishulist_number {
  color: #808080;
  font-size: 16px;
  margin-top: 20px;
  margin-bottom: 20px;
  margin-left: 23px;
}

.container .slider_part2 {
  float: left;
  border: 1px solid blue;
}
.container .slider .lunbo .slider_photo {
  width: 290px;
  height: 180px;
}
.container .slider .rcm_list {
  padding-bottom: 20px;
}
.container .slider .rcm_title {
  margin-top: 14px;
  padding-left: 22px;
  padding-bottom: 15px;
  border-bottom: 1px solid #e5e5e5;
  margin-left: 10px;
  margin-right: 10px;
}
.container .slider .rcm_list .rcm_list_one {
  list-style: none;

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
  margin-top: 20px;
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
.container .slider .right_footer {
  font-size: 13px;
  float: left;
  margin-top: 5px;
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

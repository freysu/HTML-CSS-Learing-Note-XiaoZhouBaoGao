## 常用的 html 标签以及属性

1. div 标签：

   无语义标签，划分整体、多个标签的区域

2. span 标签：

   无语义标签，可以把一行文字划分成多个区域

   ```html
   <h1>我的<span>第一篇文章</span></h1>
   ```

3. h1 ~ h6 标签：标题标签

   ```html
   <h1>我的第一篇文章</h1>
   <h2>我的第一篇文章</h2>
   <h3>我的第一篇文章</h3>
   <h4>我的第一篇文章</h4>
   <h5>我的第一篇文章</h5>
   <h6>我的第一篇文章</h6>
   ```

4. p 标签：段落标签

    ```html
    <p>这是我的第一个段落</p>
    ```

5. ul 标签：无序列表

   列表元素: li 配合使用

   标题标签最好不要放到列表里面，放到列表里面会缩进

   ```html
   <h1>水果列表</h1>
   <!--最好不要放到列表里面，放到列表里面会缩进 -->
   <ul>
     <li>苹果</li>
     <li>香蕉</li>
     <li>鸭梨</li>
   </ul>
   ```

6. a 标签：

   href 属性：可以指定跳转的地址

   ```html
   <a href="http://www.baidu.com">跳转到百度</a>
   <a href="/login">登录</a>
   <a href="#">返回顶部</a>
   ```

7. img 标签：图片标签

   src 属性：图片地址

   alt 属性：当图片没加载成功就会显示出来

   title 属性：给图片命名

   ```html
   <img src="./images/coder.jpg" alt="图片加载失败。。。" />
   <img src="./images/logo.jpg" alt="图片加载失败。。。" title="晓舟报告Logo" />
   ```

8. 通过 id 属性给标签定一个唯一值。类似名字

   ```html
   <h1 id="title2">hello world</h1>
   ```

9. class 属性分类，分类之后可以为标签指定不同的样式

   ```html
   <p class="cool">green</p>
   ```

## 作业

```html
<h1><span>h1</span>标题标签</h1>
<h2>h2标题标签</h2>
<h3>h3标题标签</h3>
<h4>h4标题标签</h4>
<h5>h5标题标签</h5>
<h6>h6标题标签</h6>

<p class="colour">red</p>
<p class="colour">green</p>
<p class="colour">blue</p>
<p class="colour">yellow</p>

<div>
  <a href="http://www.baidu.com">跳转到百度</a>
  <br />
  <a href="cover.html">跳转到自带的链接</a>
  <br />
  <a href="#footer">跳转到底部</a>
  <br />
  <img src="logo.jpg" alt="图片加载失败。。。" title="晓舟报告Logo" />
  <img src="logo1.jpg" alt="图片加载失败。。。" />
</div>

<h1>(无序列表)水果列表：</h1>
<ul>
  <li>苹果</li>
  <li>香蕉</li>
  <li>鸭梨</li>
</ul>
<h1>（有序列表）今天要做的事：</h1>
<ol>
  <li>学习</li>
  <li>吃饭</li>
  <li>睡觉</li>
</ol>

<ul>
  <li><a href="http://baidu.com">百度</a></li>
  <li><a href="http://163.com">网易</a></li>
  <li><a href="http://qq.com">腾讯</a></li>
</ul>

<p id="footer">(p段落标签)<span>到底啦</span></p>
```

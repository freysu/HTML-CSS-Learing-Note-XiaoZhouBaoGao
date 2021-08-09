> 做过渡效果之前，先把布局想好。

## 过渡效果

`transition`：

- `transition-property` 过渡属性（例如 transform）

- `transition-duration` 过渡持续时间（例如 1s）

- `transition-timing-function` 过渡函数

- `transition-delay` 过渡延迟时间

简写：

transition: 属性 秒数 函数 延迟;

```css
/* transition-property: transform; */
/* transition-duration:1s; */
transition: transform 1s ease 1s;
/* transition-property: transform; */
/* transition-duration:1s; */
transition: transform 1s;
```

设置多个值：

transition: 属性 秒数，属性 秒数;

```css
/* transition-property: transform; */
/* transition-duration:1s; */
/* transition-timing-function:ease; */
transition: transform 1s, width 1s, height 1s;
```

### 过渡属性

```css
/*  形变 */
transition-property：transform;
/*  宽度 */
transition-property：width;
/*  外边距 */
transition-property：margin;
```

### 过渡持续时间

s 为秒，单位

```css
transition-duration: 1s;
```

### 过渡函数

transition-timing-function

- ease: 开始和结束慢，中间快。默认值。

- linear: 匀速。

- ease-in：开始慢。

- ease-out: 结束慢。

- ease-in-out: 和 ease 类似，但比 ease 幅度大。

### 过渡延迟时间

例如：transition-delay: 1s;（s 为秒，单位）

## 设置形变旋转原点

```css
transform-origin: 0 0;
```

以动画的形式从 0 到 45 度，这就是过渡效果。

## overflow 属性

正常情况下内容超出容器，会溢出。

- 设置成 hidden。会把溢出的内容隐藏。

  ```css
  overflow: hidden;
  ```

- 设置成 auto，如果哪边溢出就显示哪边滚动条

  ```css
  overflow: auto;
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
      .box {
        width: 100px;
        height: 100px;
        border: 1px solid red;
        margin: 100px auto;
        /* 设置形变旋转原点 */
        transform-origin: 0 0;
        /* transition-property: transform; */
        /* transition-duration:1s; */
        /* transition-timing-function:ease; */
        transition: transform 1s, width 1s, height 1s;
      }
      .box:hover {
        transform: rotate(360deg);
        width: 200px;
        height: 200px;
      }
    </style>
  </head>
  <body>
    <div class="box">
      <h1>hello</h1>
    </div>
  </body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <style>
      .box {
        width: 100px;
        height: 100px;
        border: 1px solid red;
        overflow: auto;
      }
    </style>
  </head>
  <body>
    <div class="box">
      123 123231321312312 123231321312312 123231321312312 123231321312312
      123231321312312
    </div>
  </body>
</html>
```

## 作业

### 下拉菜单

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <style>
      * {
        margin: 0px;
        padding: 0px;
      }
      li {
        list-style: none;
      }
      /* 只要子级的li不会包括更下层的 */
      .menu > li {
        float: left;
        border: 1px solid red;
        height: 30px;
      }
      .sub-menu > li {
        height: 0px;
        overflow: hidden;
        background-color: blue;
        transition: height 0.5s ease;
        color: white;
      }
      .menu > li:hover > .sub-menu > li {
        height: 30px;
      }
    </style>
  </head>
  <body>
    <div class="box">
      <ul class="menu">
        <li>
          书籍
          <ul class="sub-menu">
            <li>js高级程序设计</li>
            <li>js高级程序设计</li>
            <li>js高级程序设计</li>
          </ul>
        </li>
        <li>
          书籍
          <ul class="sub-menu">
            <li>js高级程序设计</li>
            <li>js高级程序设计</li>
            <li>js高级程序设计</li>
          </ul>
        </li>
        <li>
          书籍
          <ul class="sub-menu">
            <li>js高级程序设计</li>
            <li>js高级程序设计</li>
            <li>js高级程序设计</li>
          </ul>
        </li>
      </ul>
    </div>
  </body>
</html>
```

### 滚动菜单

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <style>
      * {
        margin: 0;
        padding: 0;
      }
      .menu {
        margin-top: 100px;
      }
      .menu li {
        width: 80px;
        height: 30px;
        text-align: center;
        line-height: 30px;
        list-style: none;
      }
      .menu > li {
        float: left;
        overflow: hidden;
      }
      .show {
        background-color: red;
        transition: margin 0.5s;
      }
      .click {
        background-color: yellow;
        transition: margin 0.5s;
      }
      .menu > li:hover > .show {
        margin-top: -30px;
      }
    </style>
  </head>
  <body>
    <ul class="menu">
      <li>
        <p class="show">首页</p>
        <p class="click">首页</p>
      </li>
      <li>
        <p class="show">视频</p>
        <p class="click">视频</p>
      </li>
      <li>
        <p class="show">电影</p>
        <p class="click">电影</p>
      </li>
    </ul>
  </body>
</html>
```

### 百度菜单

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <style>
      * {
        margin: 0;
        padding: 0;
      }
      /* 把菜单固定到右下角 */
      .menu {
        position: fixed;
        bottom: 100px;
        right: 100px;
      }
      /* 设置第一层li的样式*/
      .menu > li {
        list-style: none;
        width: 50px;
        height: 50px;
        border: 1px solid blue;
        /* click使用定位的时候要配合父级元素的定位 */
        position: relative;
        /* 把多出的.click内容隐藏 */
        overflow: hidden;
      }
      /* 设置宽高的目的是为了设置隐藏多余的内容 */
      .show {
        width: 50px;
        height: 50px;
      }
      .click {
        width: 50px;
        height: 50px;
        background-color: red;
        position: absolute;
        top: 0px;
        left: 0px;
        transform: rotate(45deg);
        transform-origin: -50px 50px;
        transition: transform 0.5s;
      }
      .menu > li:hover > .click {
        transform: rotate(0deg);
      }
    </style>
  </head>
  <body>
    <ul class="menu">
      <li>
        <p class="show">首页</p>
        <p class="click">首页</p>
      </li>
      <li>
        <p class="show">视频</p>
        <p class="click">视频</p>
      </li>
      <li>
        <p class="show">电影</p>
        <p class="click">电影</p>
      </li>
    </ul>
  </body>
</html>
```

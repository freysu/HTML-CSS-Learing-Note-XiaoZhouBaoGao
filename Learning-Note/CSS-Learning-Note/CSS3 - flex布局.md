## flex 布局

flex 是 flexible Box 的缩写，意为"弹性布局”，用来为盒状模型提供最大的灵活性，任何一个容器都可以指定为 flex 布局。这是一种更先进的布局方式，可以让网页布局更简洁，更易于维护。

flex布局的元素会把自己的一级子元素排成一行，并将他们变成可以伸缩，易排列的盒子。

当我们为父盒子设为 flex 布局以后，子元素的 float、clear 和 vertical-align 属性将失效。

伸缩布局=弹性布局=伸缩盒布局=弹性盒布局=flex 布局

## flex 布局原理

就是通过给父盒子添加 flex 属性，来控制子盒子的位置和排列方式

## 基本概念

将元素设置为 display：flex；元素会变为一个 flex 容器。容器内部的元素为 flex 元素或者叫 flex 项目（flex-item）。

- main axis：主轴
  cross axis：交叉轴

## flex 容器中的默认效果

**父元素是默认充满宽度的**

1. flex 项目在 flex 容器中延主轴排列。
   我的理解：flex 项目默认是横向显示左对齐。
2. flex 项目高度适应 flex 容器高度（同行内元素）
   我的理解：flex 项目不设高度时是自动撑满的。

## 设置 flex 容器

### 关于主轴的属性

- flex-direction:

  设置 flex 项目排列方向，设置 **主轴** 的方向

  flex-direction是flex控制横向延展还是纵向延展的属性。

  值：

  - row(默认值)： 主轴为**水平方向**，起点在**左端**。 **从左到右**

    row-reverse: 主轴为**水平方向**，起点在**右端**。 **从右到左**
    column: 主轴为**垂直方向**，起点在**上沿**。 **从上到下**
    column-reverse： 主轴为**垂直方向**，起点在**下沿**。 **从下到上**

  _注意：使用这个属性之前一定要确定好主轴是哪个_

  

- justify-content:

  flex 项目 主轴 排列方式

  设置 **主轴** 上的子元素排列方式

  值：

  - flex-start(默认值)： **左对齐** **从头部开始** **如果主轴是 x 轴，则从左到右**
    flex-end： **右对齐** **从尾部开始排列**
    center: **居中** **在主轴居中对齐**（如果主轴是 x 轴则水平居中）
    space-between: **两端对齐**，项目之间的**间隔都相等** **平分剩余空间**
    space-around： **每个项目两侧的间隔相等**。所以，项目之间的间隔比项目与边框的间隔大一倍。**先两边贴边 再平分剩余空间（重要）** 类似于每个项目的 margin-left、margin-right 相等。

### 关于交叉轴的属性

- align-items:

  flex 项目在 **交叉轴** 的排列方式

  _设置侧轴上的子元素排列方式在子项为单项（**单行**）时使用_

  值：

  - flex-start: **交叉轴的起点对齐**。
    flex-end: **交叉轴的终点对齐**。
    center: **交叉轴的中点对齐**。
    stretch(延申)（默认值）：如果项目未设置高度或设为 auto ,将占满整个容器的高度。

- align-content:

  _设置**交叉轴**上的子元素排列方式（**多行**）只能用于子项出现换行的情况（多行），在单行下是没有效果的。_

  值：

  - flex-start(默认值)： **左对齐** **从头部开始** **如果主轴是 x 轴，则从左到右**
    flex-end： **右对齐** **从尾部开始排列**
    center: **居中** **在主轴居中对齐**（如果主轴是 x 轴则水平居中）
    space-between: **两端对齐**，项目之间的**间隔都相等** **平分剩余空间**
    space-around： **每个项目两侧的间隔相等**。所以，项目之间的间隔比项目与边框的间隔大一倍。**先两边贴边 再平分剩余空间（重要）** 类似于每个项目的 margin-left、margin-right 相等。

### 其他属性

- flex-wrap:

  设置子元素是否**换行**

  如果不设置换行，如果一行要满了，则项目的宽度会缩小。

  默认的子元素是不换行的，如果装不开，会缩小子元素的宽度，放到父元素里面。

  值：

  - nowrap:不换行；

    wrap:换行。

- flex-flow:

  **复合属性**，相当于设置了 flex-direction 和 flex-wrap.

  `flex-flow: row wrap;` = `flow-direction: row;` + `flow-wrap: wrap;`

## 设置 flex 项目

- flex:

  综合上面的三个样式。flex 属性定义子项目分配 剩余空间 ，用 flex 来表示占多少份数(fraction)。

  如果不设每个项目(3 个)的宽度只设容器宽度，那么

  ```css
  /* 1 份 */
  flex: 1;
  /* 1 份 2 份 1 份 */
  flex: 1;
  flex: 2;
  flex: 1;
  ```

- flex-grow:

  属性定义项目的放大比例，默认为 0 ，空间充足，等比例补全。

- flex-shrink:

  定义了项目的缩小比例，默认为 1 ，即如果空间不足，该项目将缩小。

- flex-basis:

  主轴排列为宽度，交叉轴排列为高度，设置 px ，默认值为 auto。

- align-self：

  flex 项目的对齐方式控制子项自己在侧轴上的排列方式。

  align-self 属性允许单个项目有与其他项目不一样的对齐方式，可覆盖 align-items 属性。默认值为 auto，表示继承父元素的 align-items 属性，如果没有父元素，则等同于 stretch.

  值：

  - auto
    flex-start
    flex-end
    center
    baseline
    stretch

- order 属性：

  定义项目的排列顺序

  数值越小，排列越靠前，默认为 0

  **注意: 与 z-index 不一样。**

## 写 flex 布局的大概思路

1. 将容器转换为 flex 容器。
   display: flex;
2. 先设置主轴方向

   (默认的) x 轴

   flex-direction: row;

   y 轴

   flex-direction: column;

3. 设置主轴上子元素的排列方式(水平居中)
   justify-content: flex-start / flex-end / center / space-between / space-around

4. 设置侧轴上子元素的排列方式（垂直居中）
   单行找 align-items 多行找 align-content
   （单行）
   align-items: flex-start / flex-end / center / stretch
   （多行） 前提是要换行 flex-wrap:wrap;
   align-content: flex-start / flex-end / center / space-around / space-between / stretch

## 示例代码

```HTML
 <!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .container {
            display: flex;
            background-color: yellow;
            width: 800px;
            height: 300px;
        }

        .item {
            background-color: red;
            border: 1px solid blue;
            /* flex-grow、flex-shrink、flex-basis都为默认值 */
            /* flex:0 1  auto; */
            /* flex-grow:1; flex-shrink、flex-basis都为默认值 */
            flex: 1;
        }

        .big {
            flex: 2;
            height: 100px;
            align-self: center;
        }
    </style>
</head>

<body>
    <div class="container">
        <div class="item">123</div>
        <div class="item">456</div>
        <div class="item big">789</div>
        <div class="item ">134</div>
        <div class="item">234</div>
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
      .wrap {
        height: 600px;
        border: 20px solid antiquewhite;
        display: flex;
        flex-direction: row;
        /* justify-content: center;  */
        /* align-content:center; */
        flex-wrap: wrap;
      }

      .box {
        height: 200px;
        width: 400px;
        color: white;
        font-size: 40px;
      }

      .box-1 {
        background: darkslategray;
        flex: 1;
      }

      .box-2 {
        background: darkcyan;
        order: -1;
        flex: 2;
      }

      .box-3 {
        background: slategrey;
        flex: 1;
        align-self: center;
      }

      /* .box-4 {
            background: slategrey;
        }

        .box-5 {
            background: darkcyan;
        } */
    </style>
  </head>

  <body>
    <div class="wrap">
      <div class="box box-1">1</div>
      <div class="box box-2">2</div>
      <div class="box box-3">3</div>
      <!-- <div class="box box-4">4</div>
        <div class="box box-5">5</div> -->
    </div>
  </body>
</html>
```

## 作业

### 1. 设置一个元素在容器中水平垂直居中。

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

      /* 如何让一个元素在屏幕中100%显示，需要让这个元素的父级都占100% */
      body,
      html {
        height: 100%;
      }

      .container {
        background-color: yellow;
        height: 100%;
        display: flex;
        justify-content: center;
        /* 一个容器的所有元素都垂直居中 */
        /* align-items: center; */
      }
      .box {
        width: 100px;
        height: 100px;
        background-color: red;
        /* 如果设置一个元素垂直居中 */
        align-self: center;
      }
    </style>
  </head>
  <body>
    <div class="container">
      <div class="box"></div>
    </div>
  </body>
</html>
```

### 2. 制作右侧网页的底部菜单。

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
      body,
      html {
        height: 100%;
      }
      .list {
        width: 100%;
      }
      li {
        list-style: none;
      }
      .list-block {
        display: flex;
        justify-content: space-between;
      }
      .list-block img {
        border: 1px solid green;
      }
      .list-dsc {
        border: 1px solid black;

        margin-top: 15px;
      }
      .list-dsc .title {
        font-size: 18px;
        margin-bottom: 10px;
      }
      .list-dsc .time {
        font-size: 12px;
        color: #b2b2b2;
      }
      .enter {
        align-self: center;
        border: 1px solid red;
        text-decoration: none;
        background-color: rgba(2, 2, 252, 0.541);
        line-height: 30px;
        text-align: center;
        color: white;
        width: 60px;
        height: 30px;
        border-radius: 30%;
      }
    </style>
  </head>
  <body>
    <ul class="list">
      <li>
        <div class="list-block">
          <img
            src="D:\Frey\Documents\CodeStudy\WebStorm_Projects\test\晓舟报告学习笔记\css\css-还原设计稿-作业\images\fepic.png"
            alt=""
          />
          <div class="list-dsc">
            <p class="title">前端开发学习手册</p>
            <p class="time">2021年7月30日</p>
          </div>
          <a href="" class="enter">进入</a>
        </div>
      </li>
    </ul>
  </body>
</html>
```

### 3. 制作右侧红色边框内的布局

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
      .menu {
        position: fixed;
        background-color: yellow;
        bottom: 0px;
        display: flex;
        width: 100%;
        height: 70px;
        align-items: center;
      }
      .sub {
        flex: 1;
        text-align: center;
      }
      .sub img {
        height: 30px;
      }
    </style>
  </head>
  <body>
    <div class="menu">
      <div class="sub">
        <img
          src="D:\Frey\Documents\CodeStudy\FE\前端教程\晓舟报告 - 《前端开发学习手册》配套案例\第02章：网页重构\第15节：flex布局\images\home.png"
          alt=""
        />
        <p>首页</p>
      </div>
      <div class="sub">
        <img
          src="D:\Frey\Documents\CodeStudy\FE\前端教程\晓舟报告 - 《前端开发学习手册》配套案例\第02章：网页重构\第15节：flex布局\images\home.png"
          alt=""
        />
        <p>手册</p>
      </div>
      <div class="sub">
        <img
          src="D:\Frey\Documents\CodeStudy\FE\前端教程\晓舟报告 - 《前端开发学习手册》配套案例\第02章：网页重构\第15节：flex布局\images\home.png"
          alt=""
        />
        <p>首页</p>
      </div>
      <div class="sub">
        <img
          src="D:\Frey\Documents\CodeStudy\FE\前端教程\晓舟报告 - 《前端开发学习手册》配套案例\第02章：网页重构\第15节：flex布局\images\home.png"
          alt=""
        />
        <p>首页</p>
      </div>
      <div class="sub">
        <img
          src="D:\Frey\Documents\CodeStudy\FE\前端教程\晓舟报告 - 《前端开发学习手册》配套案例\第02章：网页重构\第15节：flex布局\images\home.png"
          alt=""
        />
        <p>首页</p>
      </div>
    </div>
  </body>
</html>
```

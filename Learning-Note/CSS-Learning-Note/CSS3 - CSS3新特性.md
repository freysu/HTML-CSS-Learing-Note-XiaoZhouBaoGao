## CSS3 概述

- 我们之前讲解过的所有 CSS 知识，都是 CSS2 版本的功能。
- CSS3 在 CSS2 版本的基础上，新增了很多特性，例如边框圆角、动画效果。
- 在 CSS2 的时代，实现圆角必须要用图片才能实现，而 CSS3 只要一行样式就能实现圆角。
- 在 CSS3 的时代，动画效果一定要使用 JavaScript 配合复杂的 CSS 样式操作才能实现（或者用 jQuery 这种第三方库）。CSS3 同样可以简单地实现动画效果，而且效果更佳。
- 早些年头，因为浏览器的兼容问题，并未广泛引用，但是近几年，随着随着各大浏览器厂商的标准化，大家可以畅快第使用 CSS3 了。

## CSS3 新特性

1. 边框圆角
2. 阴影
3. 形变：旋转、缩放、位移
4. 过渡效果
5. 动画效果
6. 媒体查询
7. flex 布局
8. grid 布局

等等（选择器、字体）......

### 边框圆角

- `border-radius`:左上 右上 右下 左下

- 如果设置两个值，第一个值表示左上和右下，第二个值表示右上和左下。

  ```css
  border: 1px solid red;
  ```

- 四个角是一样的

  ```css
  border-radius: 50px;
  ```

- 左上 右上 右下 左下

  ```css
  border-radius: 10px 20px 30px 40px;
  ```

- 左上右下 右上左下

  ```css
  border-radius: 20px 40px;
  ```

- 高度宽度相同时，边框圆角设成 50%才能设成正圆。

  ```css
  border-radius: 50%;
  ```

### 阴影

- box-shadow: 10px 20px 30px blue;

  参数分别表示：x 轴偏移量，y 轴偏移量，模糊半径，阴影颜色（不设置颜色为黑色）

  ```css
  box-shadow: 10px 20px 30px;
  ```

  蓝色阴影

  ```css
  box-shadow: 10px 20px 30px blue;
  ```

  x 轴偏移量为 100px;

  ```css
  box-shadow: 100px 20px 30px blue;
  ```

  y 轴偏移量为 200px;

  ```css
  box-shadow: 10px 200px 30px blue;
  ```

  模糊半径，越大越模糊

  ```css
  box-shadow: 10px 20px 50px blue;
  ```

### 形变

transform:

- rotate();旋转 deg 单位表示角度

    ```css
    /*顺时针旋转 45° 单位是 deg 角度*/
    transform: rotate(45deg);
    ```

- scale();缩放

    ```css
    /*缩放 0.5 倍*/
    transform: scale(0.5);
    ```

- translate();位移

    ```css
    /*位移 可以设百分数% 具体值单位是 px 横坐标向右位移 50px 纵坐标向下位移 100px*/
    transform: translate(50px, 100px);
    ```

- transform 都是同一个属性，分开写会被覆盖，所以多个形变要这样写

    ```css
    transform: rotate(45deg) translate(50px, 100px);
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
        width: 200px;
        height: 200px;
        background-color: red;
        /* 边框圆角 */
        /* border:1px solid red; */
        /* 四个角是一样的 */
        /* border-radius:50px; */
        /* 左上 右上 右下 左下 */
        /* border-radius: 10px 20px 30px 40px; */
        /* 左上右下 右上左下 */
        /* border-radius:20px 40px; */
        /* 高度宽度相同时，边框圆角设成50%才能设成正圆。 */
        /* border-radius:50%; */

        /* 阴影 */
        /* 默认阴影颜色为黑色 */
        /* box-shadow:10px 20px 30px; */
        /* 蓝色阴影 */
        /* box-shadow:10px 20px 30px blue; */
        /* x轴偏移量为100px; */
        /* box-shadow:100px 20px 30px blue; */
        /* y轴偏移量为200px; */
        /* box-shadow:10px 200px 30px blue; */
        /* 模糊半径，越大越模糊 */
        /* box-shadow:10px 20px 50px blue; */

        /* 形变*/
        /* 顺时针旋转45° 单位是deg 角度*/
        /* transform: rotate(45deg); */
        /* 缩放0.5倍  */
        /* transform: scale(0.5); */
        /* 位移 可以设百分数% 具体值单位是px 横坐标向右位移50px 纵坐标向下位移100px */
        /* transform: translate(50px,100px); */
        /* transform都是同一个属性，分开写会被覆盖，所以多个形变要这样写 */
        /* transform: rotate(45deg) translate(50px,100px); */
      }
      /* 简单的动画，知道就行 */
      /* .box:hover{
            transform: rotate(45deg) scale(0.5);
        } */
    </style>
  </head>
  <body>
    <div class="box">
      <h1>hello</h1>
    </div>
  </body>
</html>
```
### 让一个元素在网页中水平垂直居中

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
        /* 1. 等高度等宽度可以按比例设置形变位移。 */
        /* width:200px;
            height:200px;
            background-color: red;
            margin:0 auto;
            position:absolute;
            top:50%;
            left:50%;
            transform: translate(-100px,-100px); */

        /* 2.不同高度宽度时用百分数可以实现 */
        width: 500px;
        height: 200px;
        background-color: red;
        margin: 0 auto;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
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


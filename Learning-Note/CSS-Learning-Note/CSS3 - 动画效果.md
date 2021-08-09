> 先布局再想动画

## 动画与过渡的区别：

过渡效果通常用户与浏览器进行交互（例如 hover）

动画效果，可以交互，也可以在网页加载时直接执行，并且可以让效果更复杂。

## 动画属性(animation)

- `animation-name`: 规定需要绑定到选择器的 keyframe 名称...

- `animation-duration`: 规定完成动画所花费的时间，以秒或毫秒计。

- `animation-timing-function`: 规定动画的速度曲线函数.

- `animation-delay`: 规定在动画开始之前的延迟。

- `animation-iteration-count`: 规定动画应该播放的次数。

  infinite 无限次

## keyframes

定义一个动画

1. 按百分比指定动画
2. from...to...指定动画

注意：开始与结束相同，可以让动画更平滑

```css
@keyframes anim {
  0% {
    transform: translate(0px, 0px);
  }

  100% {
    transform: translate(900px, 100px);
  }
}
```

## 停止动画效果

```css
animation-play-state: paused；;
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
      /* keyframes定义一个动画 */
      @keyframes anim {
        /* 1. 按百分比指定动画 */
        /* 0%-50% 会转过去再转回来 类似过渡效果*/
        /* 0%-100% 完整*/
        /* 注意：开始与结束相同，可以让动画更平滑 */
        0% {
          transform: rotate(0deg);
        }
        20% {
          width: 200px;
          height: 200px;
          transform: rotate(360deg);
        }
        40% {
          background-color: yellow;
          width: 300px;
          height: 300px;
        }
        100% {
          width: 100px;
          height: 100px;
        }
        /* 2. from...to...指定动画 */
        /* from:0%, to:100%  */
        /* from{
                transform: rotate(0deg);
            }
            to{
                transform: rotate(360deg);
            } */
      }
      .box {
        width: 100px;
        height: 100px;
        background-color: red;
        margin: 100px auto;
        /* infinite 无限次 */
        animation: anim 10s linear;
      }
    </style>
  </head>
  <body>
    <div class="box"></div>
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
      @keyframes anim {
        form {
          transform: rotate(0deg);
        }
        to {
          transform: rotate(360deg);
        }
      }
      .box {
        height: 200px;
        width: 200px;
        margin: 100px auto;
        border-radius: 50%;
        overflow: hidden;
        animation: anim 5s linear;
      }
      .box img {
        height: 200px;
        width: 200px;
      }
      .box:hover {
        /* 停止动画效果 */
        animation-play-state: paused;
      }
    </style>
  </head>
  <body>
    <audio src="" controls></audio>
    <div class="box">
      <img src="images/jay.jpg" alt="" />
    </div>
  </body>
</html>
```

## 作业

海盗船

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>海盗船</title>
    <style>
      @keyframes wave {
        50% {
          transform: translate(-50px);
        }
      }
      @keyframes ship {
        50% {
          transform: rotate(15deg);
        }
      }
      @keyframes fish {
        0% {
          transform: rotate(-20deg);
          left: 10px;
          top: 500px;
        }
        10% {
          transform: rotate(-5deg);
          left: 300px;
          top: 300px;
        }
        30% {
          transform: rotate(-20deg);
          left: 500px;
          top: 550px;
        }
        50% {
          transform: rotate(5deg);
          left: 700px;
          top: 300px;
        }
        70% {
          transform: rotate(-20deg);
          left: 800px;
          top: 550px;
        }
        90% {
          transform: rotate(5deg);
          left: 1100px;
          top: 300px;
        }
        100% {
          transform: rotate(5deg);
          left: 1300px;
          top: 500px;
        }
      }

      * {
        margin: 0px;
        padding: 0px;
      }
      .container {
        width: 100%;
        height: 800px;
        overflow: hidden;
      }
      .bg {
        position: absolute;
        top: 0;
        left: 0;
      }
      .fish {
        position: absolute;
        left: 10px;
        top: 500px;
        z-index: 3;
        animation: fish 10s linear 1s infinite;
      }
      .sea {
        margin-top: 450px;
        position: relative;
      }
      .wave1 {
        position: absolute;
        top: 100px;
        left: 0px;
        height: 110px;
        z-index: 100;
        width: 130%;
        animation: wave 2s ease-in infinite;
      }
      .wave2 {
        position: absolute;
        top: 50px;
        left: 0px;
        height: 110px;
        width: 130%;
        z-index: 10;
        animation: wave 3s ease-in infinite;
      }
      .wave3 {
        position: absolute;
        top: 0px;
        left: 0px;
        height: 110px;
        width: 130%;
        z-index: 0;
        animation: wave 5s ease-in infinite;
      }
      .ship {
        position: absolute;
        left: 30%;
        z-index: 5;
        animation: ship 5s ease infinite;
      }
    </style>
  </head>
  <body>
    <div class="container">
      <img src="images/bg.png" alt="" class="bg" />
      <img src="images/ship.png" alt="" class="ship" />
      <img src="images/fish.png" alt="" class="fish" />
      <div class="sea">
        <img class="wave1" src="images/wave1.png" alt="" />
        <img class="wave2" src="images/wave2.png" alt="" />
        <img class="wave3" src="images/wave3.png" alt="" />
      </div>
    </div>
  </body>
</html>
```

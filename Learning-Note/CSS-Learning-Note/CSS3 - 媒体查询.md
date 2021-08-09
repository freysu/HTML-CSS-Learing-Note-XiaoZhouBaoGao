## 响应式页面

响应式页面是根据宽度高度等变换页面样式。移动端和响应式页面是区别的。

### 优点：

一套页面适应多端设备，提升开发效率。

### 缺点：

页面效果不及单独为某一终端定制的页面效果;性能问题;维护成本提升

### 总结：

大部分项目不会整体才有响应式页面的解决方案。

## 媒体查询

```css
@media screen and (max-width: 600px) {
  .box {
    width: 200px;
    height: 200px;
    background-color: red;
  }
}
```

```css
/* 浏览器宽度600<x<900 变换样式 */
@media screen and (min-width: 600px) and (max-width: 900px) {
  .box {
    width: 200px;
    height: 200px;
    background-color: red;
  }
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
      * {
        margin: 0px;
        padding: 0px;
      }
      .box {
        width: 100px;
        height: 100px;
        background-color: yellow;
      }
      @media screen and (max-width: 600px) {
        .box {
          width: 200px;
          height: 200px;
          background-color: red;
        }
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
      * {
        margin: 0px;
        padding: 0px;
      }
      .box {
        width: 100px;
        height: 100px;
        background-color: yellow;
      }
      /* 浏览器宽度600<x<900 变换样式 */
      @media screen and (min-width: 600px) and (max-width: 900px) {
        .box {
          width: 200px;
          height: 200px;
          background-color: red;
        }
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
      * {
        margin: 0px;
        padding: 0px;
      }
      .container {
        display: flex;
        width: 800px;
        margin: 0 auto;
        background-color: grey;
        justify-content: center;
      }
      .item {
        width: 200px;
        border: 1px solid red;
        text-align: center;
      }
      @media screen and (max-width: 700px) {
        .container {
          width: 100%;
          flex-direction: column;
        }
        .item {
          width: 100%;
        }
      }
    </style>
  </head>
  <body>
    <div class="container">
      <div class="item">
        <h1>文档</h1>
      </div>
      <div class="item">
        <h1>博客</h1>
      </div>
      <div class="item">
        <h1>视频</h1>
      </div>
    </div>
  </body>
</html>
```


## 作业
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

      .container {
        display: flex;
        width: 800px;
        background-color: grey;
        margin: 0 auto;
        justify-content: center;
      }

      .item {
        width: 200px;
        text-align: center;
        border: 1px solid red;
      }

      @media screen and (max-width: 700px) {
        .container {
          flex-direction: column;
          width: 100%;
        }

        .item {
          width: 100%;
        }
      }
    </style>
  </head>

  <body>
    <div class="container">
      <div class="item">
        <h1>文档</h1>
      </div>
      <div class="item">
        <h1>博客</h1>
      </div>
      <div class="item">
        <h1>视频</h1>
      </div>
    </div>
  </body>
</html>

```
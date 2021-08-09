## CSS 介绍

CSS 全称层叠样式表
网页的内容，由 HTML 控制
网页的样式，有 CSS 控制

## CSS 语法

`h1{ color:red;}`

选择器{

属性名：属性值；

属性名：属性值；

}

## 常用的 CSS 选择器

1. 元素选择器: 如 `h1`,`img`,`p` 标签等等

   ```css
   h1 {
     /* 字体颜色 */
     color: red;
     /* 字体大小:px是像素单位 */
     font-size: 12px;
   }
   ```

2. 类选择器：`.className`

   ```css
   /* 类选择器 .className */
   .test {
     color: red;
   }
   ```

3. id 选择器：`#id`, 一般不用 id 选择器

   ```css
   #test {
     color: red;
   }
   ```

4. 通配符选择器：`\*`, 可以找到全部元素

   ```css
   * {
     color: red;
   }
   ```

## 常用的 CSS 文本属性

1. `font-size`：字体大小

   在 chrome 浏览器：font-size 最小值是 12px

   ```css
   font-size: 12px;
   ```

2. `color`：字体颜色

   ```css
   color: red;
   color: #ffffff;
   ```

3. `width`：宽度

   ```css
   width: 100%;
   width: auto;
   width: 1280px;
   ```

4. `height`：高度

   设置图片的宽度高度时，如果不设置高度，高度是默认自动的，如果强行设置成其他的，可能会图片拉伸等

   ```css
   height: 100%;
   height: auto;
   height: 1280px;
   ```

5. `background-color`：背景色

   ```css
   background-color: red;
   background-color: #ffffff;
   ```

6. `text-align`：文本水平居中

   值：center，居中

   ```css
   text-align: center;
   ```

7. `line-height`：文本行高（垂直居中）

   尽量取和高度（不是所有的高度）一样的值

   ```css
   line-height: 10px;
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
      h1 {
        /* 字体颜色 */
        color: red;
        /* 字体大小:px是像素单位 */
        font-size: 12px;
      }
    </style>
  </head>
  <body>
    <h1>hello world</h1>
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
      /* 类选择器 .className */
      .test {
        color: red;
      }
      /* 一般不用id选择器 */
    </style>
  </head>
  <body>
    <h1 class="test">hello world</h1>
    <p class="test">hello</p>
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
      /* id选择器 #idName */
      #test {
        color: red;
      }
    </style>
  </head>
  <body>
    <h1 id="test">hello world</h1>
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
      /* 通配符选择器：*,可以找到全部元素 */
      * {
        color: red;
      }
    </style>
  </head>
  <body>
    <h1>hello h1</h1>
    <p>hello p</p>
    <a href="">hello a</a>
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
      .test {
        /* 在chrome浏览器：font-size最小值是12px */
        font-size: 12px;
        color: white;
        background-color: black;
        /* 文本水平对齐，center是居中 */
        text-align: center;
        line-height: 100px;
      }
      img {
        width: 500px;
        /* 不设置高度时，高度是默认自动的，如果强行设置成其他的，可能会图片拉伸等 */
        height: auto;
      }
    </style>
  </head>
  <body>
    <h1 class="test">hello world</h1>
    <img src="./simle.png" alt="" />
  </body>
</html>
```

## 作业

按要求完成网页：
1. 设置一个宽度为980px的div容器，背景颜色为黄色。
2. 容器内部显示一篇文章，文章有标题，图片和段落文字和列表。
3. 标题字体16px，居中显示。
4. 标题下方显示作者信息和文章发布日期，字体颜色为#aaaaaa，字体大小为12px
5. 除上述文字外，所有字体颜色为黑色，字体大小为14px;
6. 图片在两个段落间显示，宽度为300px，高度为200px。
7. 列表为无序列表
8. 至少包含2个段落文字。

```html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style type="text/css">
        .article{
            width:980px;
            background-color: yellow;
        }
        .article h1{
            font-size:16px;
            text-align:center;
        }
        .author-time{
            color:#aaaaaa;
            font-size:12px;
        }
        .article img{
            width: 300px;
            height: 200px;
        }
        .nostyle {
            color: black;
            font-size: 14px;
        }
    </style>
</head>
<body>
    <div class="article">
        <h1>hello h1</h1>
        <p class="author-time"> FreySu 2021年7月17日</p>
        <p class="nostyle">This is a paragraph.</p>
        <img src="smile.png" alt="">
        <p class="nostyle">This is a paragraph.</p>
        <ul class="nostyle">
            <li>Apple</li>
            <li>Bear</li>
            <li>Pineapple</li>
        </ul>
    </div> 
</body>
</html>
```


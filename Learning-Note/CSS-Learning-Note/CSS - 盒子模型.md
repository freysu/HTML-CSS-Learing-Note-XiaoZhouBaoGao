## 盒子概述

将 HTML 元素看做是盒子，来实现的网页布局。

## 盒子模型的 CSS 属性

- 边框：`border-width`,`border-style`,`border-color`;

  可以简写的格式：

  ```css
  /* border: border-width border-style border-color; */
  /*
  border-width: 1px;
  border-style: solid;
  border-color:blue; 
  */
  border: 1px solid blue;
  ```

  `border-style` 属性 的值

  | 值     | 描述         |
  | ------ | ------------ |
  | none   | 定义无边框   |
  | dotted | 定义点状边框 |
  | dashed | 定义虚线     |
  | solid  | 定义实线     |
  | double | 定义双线     |

- 外边距：`margin(-top\-right\-bottom\-left)`

  ```css
  margin-left: 100px;
  margin-top: 50px;
  margin-top: 50px;
  ```

  简写 4 个值：上右下左

  ```css
  margin: 100px 0 0 200px;
  ```

  简写 2 个值: 上下 左右

  ```css
  margin: 100px 50px;
  ```

- 内边距：`padding(-top\-right\-bottom\-left)`

  简写 2 个值：上下 左右

  ```css
  /* padding-top:10px;
  padding-left:20px; */
  padding: 10px 20px;
  ```

## 默认情况：元素宽度和高度计算

- 元素的实际宽度：border-left + border-right + width + padding-left + padding-right

- 元素的实际高度：border-top + border-bottom + height + padding-top + padding-bottom

## 设置 box-size:border-box；

- 元素的实际宽度 = width
- 元素的实际高度 = height

```css
box-sizing: border-box;
```

## 清楚元素默认边距

```css
margin: 0;
padding: 0;
```

## 元素水平居中

`margin:0 auto;`

auto:自动 左右设成相同的

容器的元素居中显示

```css
margin: 0 auto;
```

## 列表的样式

- 取消列表样式：`list-style:none`;
- 列表样式在边距之内：`list-style: inside`;

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
        border: 10px solid red;
        margin: 100px 0 0 200px;
        margin: 100px 50px;
        padding: 10px 20px;
        box-sizing: border-box;
      }
    </style>
  </head>
  <body>
    <div class="box">
      <a href="">test</a>
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
      * {
        margin: 0px;
        padding: 0px;
      }
      .container {
        width: 800px;
        height: 300px;
        border: 1px solid red;
        margin: 0 auto;
      }
    </style>
  </head>
  <body>
    <div class="container"></div>
  </body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
     <style>
         *{
             margin:0px;
             padding:0px;
         }
         .fruits{
             border:1px solid red;
             width: 800px;
             margin:0 auto;
             padding-left:30px;
             box-sizing: border-box;
             padding-top:20px;
         }

         .sports{
             border:1px solid blue;
             width:800px;
             margin:0 auto;
             margin-top:50px;
             padding-left:30px;
             box-sizing: border-box;
             padding-top:20px;

         }

         .fruits ul, .sports ul{
             list-style: inside;
         }
     </style>
</head>
<body>
    <div class="fruits">
        <h3>水果列表</h3>
        <ul>
            <li>香蕉</li>
            <li>苹果</li>
            <li>鸭梨</li>
        </ul>
    </div>

    <div class="sports">
        <h3>运动列表</h3>
        <ul>
            <li>篮球</li>
            <li>足球</li>
            <li>排球</li>
        </ul>
    </div>
</body>
</html>
```


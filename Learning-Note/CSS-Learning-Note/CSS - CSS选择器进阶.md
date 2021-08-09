## 更多选择器

- 层级选择器：`selector1 selector2`

  如 `.className` 类选择器 + ` `空格 + 元素选择器

  ```css
  .box1 h1 {
    color: red;
  }
  ```

- 组合选择器：`selector1,selector2`

  如 元素选择器 + `,`+ 元素选择器

  可以和层级选择器嵌套

  如`.className`类选择器 + + 元素选择器 + `,` + 元素选择器

  ```css
  .box1 h1,
  h2 {
    color: red;
  }
  ```

- 伪类选择器（增加行为）：`selector:hover`

  如，类选择器:hover

  鼠标移到 div 容器时，div 变色

  ```css
  .box:hover {
    background-color: blue;
  }
  ```

- 伪元素选择器（增加元素）：`selector::before`，`selector::after`

  如 content 属性：增加内容

  selector::before 选择器的前面

  selector::after 选择器的后面

  ```css
  /* .text::before{
              content:"-----";
          }
          .text::after{
              content:"-----";
          } */

  .text::before,
  .text::after {
    content: "-----";
    color: red;
  }
  ```

- 除此之外还有很多选择器

## 补充知识

浏览器兼容 css2,css3

css2: 伪类选择器和伪元素选择器都是一个冒号

css3：让伪元素选择器增加了一个冒号

## 选择器权重

- 相同选择器：后面的会覆盖前面的
- 不同选择器：ID（100） > CLASS （10）>element（1）
- 层级选择器：按权重累加计算

## 设置最高权重

`!important`

## 引入 CSS 的方法

1. 嵌入样式

   **自学时少量的可以用，用得也少，大部分都是外部样式**

   ```html
   <style>
     h3,
     h1 {
       color: blue;
     }
   </style>
   ```

2. 内联样式

   又称行内样式，**尽量不用要内联样式，权重要高于嵌入样式**

   ```html
   <h1 style="color:red;">hello world</h1>
   ```

3. 外部样式（**实际开发中大部分都使用外部样式**）

   ```html
   <link rel="stylesheet" href="style/css-1-demo05.css" />
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
        background-color: red;
      }

      /* 伪类选择器（增加行为）:.className：hover
        →类选择器:hover
        鼠标移到div容器时，div变色 */
      .box:hover {
        background-color: blue;
      }

      .btn:hover {
        background-color: green;
      }
    </style>
  </head>

  <body>
    <div class="box"></div>
    <input class="btn" type="button" value="按钮" />
  </body>
</html>
```

```HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        /* 层级选择器 selector1 selector2
        如.className 类选择器+ +元素选择器 */
        /* .box1 h1{
            color:red;
        } */

        /* 组合选择器 selector1,selector2
        如元素+，+元素
        可以和层级选择器嵌套，.className选择器+ +元素选择器+，+元素选择器 */
        .box1 h1,h2{
            color:red;
        }


    </style>
</head>
<body>
    <div class="box1">
        <h1>hello h1</h1>
        <h2>hello h2</h2>
    </div>

    <div class="box2">
        <h1>hello h1</h1>
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
      /* .text::before{
            content:"-----";
        }
        .text::after{
            content:"-----";
        } */

      .text::before,
      .text::after {
        content: "-----";
        color: red;
      }
    </style>
  </head>
  <body>
    <h1 class="text">hello world</h1>
    <h2 class="text">hello world</h2>
  </body>
</html>
```

### 引入 CSS 的例程

```css
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <!-- 嵌入样式 自学时少量的可以用,用得也少,大部分都是外部样式 -->
    <style>
        h3,h1{
            color:blue;
        }
    </style>
    <!-- 外部样式 实际开发大部分都是这个 -->
    <link rel="stylesheet" href="style/css-1-demo05.css">

</head>
<body>
    <!-- 内联样式,行内样式  尽量不用要内联样式,权重要高于嵌入样式 -->
    <h1 style="color:red;">hello world</h1>
    <h2>hello h2</h2>
    <h3>hello h3</h3>
</body>
</html>
```

## 作业

优化上一节课后练习的代码，要求如下：

1. 使用层级选择器让所有样式都在 .container 的下级

2. 使用 link 标签引入外部样式

3. 去掉列表元素之前的点，并且将列表设置为红色字体。

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <link rel="stylesheet" href="style/css-1-作业.css" />
  </head>
  <body>
    <div class="container">
      <h1>hello h1</h1>
      <p class="author-time">FreySu 2021年7月17日</p>
      <p class="nostyle">This is a paragraph.</p>
      <img src="smile.png" alt="" />
      <p class="nostyle">This is a paragraph.</p>
      <ul>
        <li>Apple</li>
        <li>Bear</li>
        <li>Pineapple</li>
      </ul>
    </div>
  </body>
</html>
```

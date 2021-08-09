## grid 布局

网格布局

```css
display: grid;
```

## grid 容器属性

- grid-auto-flow

  值：

  - row 默认排列方式(可以不写) 从左到右 从上到下 123 456 789

    colum 竖着排列 从左到右 从上到下 147 258 369

- grid-template-columns

  grid-template-rows:

  按像素来设置单元格 单元格与 grid 项目不一样的

  ```css
  grid-template-columns: 100px 100px 100px;
  grid-template-rows: 100px 100px 100px;
  ```

  按比例来设置单元格

  ```css
  grid-template-columns: 100px 1fr 2fr;
  grid-template-rows: 100px 100px 100px;
  ```

### grid 项目 在 单元格 中的 对齐方式

- justify-items:

  stretch 默认值 水平拉伸 start 单元格开始的位置(左) end 单元格结尾的位置（右） center 单元格居中的位置（中）

  值：

  - start 左
    end 右
    center 中
    stretch 水平拉伸

- align-items:

  stretch 默认值 垂直拉伸 start 单元格开始的位置（上） end 单元格结尾的位置（下） center 单元格居中的位置（中）

  值：

  - start 上

    end 下

    center 中

    stretch 垂直拉伸

### 单元格 在整个 grid 的 容器 中的 对齐方式

- justify-content:

  值：

  - start

    end

    center

    stretch

- align-content:

  值：

  - start

    end

    center

    stretch

- grid-auto-columns:
  溢出列的尺寸

  值：

  - 数字 px;

- grid-auto-rows:

  溢出行的尺寸

  值：

  - 数字 px;

## grid 项目属性

### grid 项目对齐方式

- justify-self:

  值：

  - start 左
    end 右
    center 中
    stretch 水平拉伸

- align-self:

  值：

  - start 上
    end 下
    center 中
    stretch 垂直拉伸

### 单元格合并

- 横向合并单元格

  grid-columns-start: 数字;

  grid-columns-end: 数字;

  简写：

  grid-columns: 数字 / 数字;

- 纵向合并单元格

  grid-rows-start: 数字;

  grid-rows-end: 数字;

  简写：

  grid-rows: 数字 / 数字;

## 示例代码

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <style type="text/css">
      .container {
        display: grid;
        width: 800px;
        height: 500px;
        border: 1px solid red;

        /* (可以不写)默认排列方式 从左到右 从上到下 123 456 789 */
        grid-auto-flow: row;

        /* 按像素来设置单元格 单元格与grid项目不一样的 */
        grid-template-columns: 100px 100px 100px;
        grid-template-rows: 100px 100px 100px;

        /* 溢出列的尺寸 */
        grid-auto-columns: 50px;
        /* 溢出行的尺寸 */
        grid-auto-rows: 50px;
      }

      .item {
        border: 1px solid red;
      }

      .first {
        /* 横向合并单元格 */
        /* grid-column-start: 2;
            grid-column-end:4; */
        grid-column: 2 / 4;
        /* 纵向合并单元格 */
        grid-row: 2 / 4;
        /* grid-row-start: 2; */
        /* grid-row-end:4;  */

        /* 设置grid项目的对齐方式 */
        /* justify-self: center;
            align-self: center; */
      }
    </style>
  </head>

  <body>
    <div class="container">
      <div class="item first">1</div>
      <div class="item">2</div>
      <div class="item">3</div>
      <div class="item">4</div>
      <div class="item">5</div>
      <div class="item">6</div>
      <div class="item">7</div>
      <div class="item">8</div>
      <div class="item">9</div>
      <!-- <div class="item">10</div>
        <div class="item">11</div> -->
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
        display: grid;
        width: 800px;
        margin: 0 auto;
        border: 1px solid blue;
        grid-template-columns: 600px 200px;
        grid-template-rows: 80px 200px 200px 200px 50px;
      }

      .item {
        border: 1px solid red;
      }

      .header {
        grid-column: 1 / 3;
      }

      .aside {
        grid-row: 2 / 5;
        grid-column: 2 / 3;
      }

      .footer {
        grid-column: 1 / 3;
      }
    </style>
  </head>

  <body>
    <div class="container">
      <div class="header item">logo</div>
      <div class="docs item">docs</div>
      <div class="blogs item">blogs</div>
      <div class="videos item">videos</div>
      <div class="aside item">aside</div>
      <div class="footer item">footer</div>
    </div>
  </body>
</html>
```

## css 常用的定位（position）属性

- 绝对定位：absolute

  脱离文档流；

  默认参照物为浏览器视窗的左上角

  **相对于它的第一个position不为static的父元素，如果没有，就相对于body**，你问我什么叫**第一个**?

  第一个的意思是，如果这个元素的父元素的父元素，也就是**这个元素的爷爷元素的position不是static，但是父元素是static，那么这个元素的top相对于爷爷元素定位**

  **设置absolute的元素在同时设置top和bottom的情况下，以top的取值来设定竖直方向的布局。**

- 相对定位：relative

  不脱离文档流；

  默认参照物为此元素元位置；

  和absolute差不太多，但是有一个**特异性**——**移动元素后，元素本来占有的位置会保留，然后会相对原来的位置定位**。

- 固定定位：fixed

  脱离文档流；

  默认参照物为浏览器视窗位置；

  无论你怎么滚动页面，调戏滚动条和鼠标滚轮，它都在浏览器的那个位置，就是不动。

- static是position默认的取值。

## 坐标属性（非定位元素不起作用）

- top，left，right，bottom 属性：

  元素设置了position属性之后，就会激活4个css属性。

   **top,left,right,bottom,这些属性，不设置的时候默认值是auto，会尽量保持原来的位置，而且，top，left的优先级要大于bottom和right**

  ```css
  top: 50px;
  
  left: 80px;
  
  right: 0px;
  
  bottom: 10px;
  ```

- z-index 属性：

  谁在谁之上显示 只能是整数 大小随意

  值为整数；

  数值大则在前方显示。

  负数：置底，会跑到非定位元素的下面.

  ```css
  z-index: -1;
  
  z-index: 9;
  ```

## 居中实现方法
先写宽度再写居中 

```css
width:628px;
margin:0 auto;
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
      body {
        height: 2000px;
      }
      .box {
        width: 100px;
        height: 100px;
        background-color: red;
        border: 1px solid white;
      }
      .pos {
        /* 固定定位 */
        position: fixed;
        top: 50px;
        left: 80px;
        /* 谁在谁之上显示 只能是整数 大小随意 */
        z-index: 9;
      }
      .pos-ab {
        position: absolute;
        top: 50px;
        left: 50px;
        /* 负数：置底，会跑到非定位元素的下面 */
        z-index: -1;
      }
    </style>
  </head>
  <body>
    <div class="box">1</div>
    <div class="box pos">2</div>
    <div class="box pos-ab">3</div>
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
        .pic-box{
            /* 居中实现方法 */
            /* 先写宽度再写居中 */
            width:628px;
            margin:0 auto;
            /* 参照物变成容器 父级>子级是relative>absolute或者absolute>absolute */
            position: relative;
        }
        .list{
            position:absolute;
            top:10px;
            left:500px;
        }
    </style>
</head>
<body>
    <div class="pic-box">
        <img src=".\images\pic.jpg" alt="">
        <ul class="list">
            <li>1</li>
            <li>2</li>
            <li>3</li>
        </ul>
    </div>
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
        body{
            height:2000px;
        }
        .pos{
            position:fixed;
            bottom:100px;
            right: 100px;
        }
    </style>
</head>
<body>
    <h1>hello world</h1>
    <h1>hello world</h1>
    <h1>hello world</h1>
    <h1>hello world</h1>
    <h1>hello world</h1>
    <h1>hello world</h1>

    <button class="pos">
        <!-- a的href属性只写#，返回最上方 -->
        <a href="#">返回顶部</a>
    </button>
</body>
</html>
```

## 作业

1. 制作一个图片之上显示数值列表的功能。
2. 制作一个返回顶部的功能，一直在网页右下角显示。
1. 完成晓舟报告右侧返回顶部的悬浮效果[效果地址](http://www.xiaozhoubg.com/public/demo/frontend/2-9-1.html)。
2. 制作一个在图片上显示图标描述文字的效果，并且图片再网页右下角显示[效果地址](http://www.xiaozhoubg.com/public/demo/frontend/2-9-2.html)。
3. 制作一个标题效果，让标题左右两边各带一个横线（使用伪元素和定位来实现）[效果地址](http://www.xiaozhoubg.com/public/demo/frontend/2-9-3.html)。

```html
<!-- 
    
 -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .pic-box{
            width:700px;
            margin:0 auto;
            position:relative;  
        }
        .list{
            position:absolute;
            top:10px;
            left:20px;
        }
    </style>
</head>
<body>
    <div class="pic-box">
        <img src=".\images\pic.jpg" alt="">
        <ul class="list">
            <li>1</li>
            <li>2</li>
            <li>3</li>
        </ul>
    </div>
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
         body{
             height:2000px;
         }
         .btu{
             position:fixed;
             right:10px;
             bottom:10px;
         }
     </style>
 </head>
 <body>
     <h1>Hello World!</h1>
     <h1>Hello World!</h1>
     <h1>Hello World!</h1>
     <h1>Hello World!</h1>
     <h1>Hello World!</h1>
     <h1>Hello World!</h1>

     <div class="btu">
         <button>
            <a href="#">返回顶部</a>
         </button>
     </div>
 </body>
 </html>
```

```html
-->
 <!DOCTYPE html>
 <html lang="en">
 <head>
     <meta charset="UTF-8">
     <meta http-equiv="X-UA-Compatible" content="IE=edge">
     <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <title>Document</title>
     <style>
         .h1-t h1::after,.h1-t h1::before{
             content:"——";
         }
     </style>
 </head>
 <body>
     <div class="h1-t">
         <h1>hello</h1>
     </div>
 </body>
 </html>
```


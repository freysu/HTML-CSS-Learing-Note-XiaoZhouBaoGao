## 使用 rem 单位设置移动端尺寸

### 移动端的特点

1. 设备尺寸不同

1. 可以通过设置百分比解决

1. 设置百分比计算繁琐

### 单位概述

1. px：

   像素

2. em:

   相对于父级的 font-size 值,父级的 font-size 值越大，子级的 em 就越大

3. rem:

相对于 html 标签的 font-size 值
html font-size: N px; 1rem 代表 N px; 10rem 代表 10N px;

## 根据移动端浏览器宽度通过 js 来自适应 rem 单位

### setFontSize.js

```js
//copy from taobao
!(function (win) {
  function refreshRem() {
    var width = docEl.getBoundingClientRect().width;
    width / dpr > 540 && (width = 540 * dpr),
      (win.rem = width / 16),
      (docEl.style.fontSize = win.rem + "px");
  }

  var dpr,
    scale,
    tid,
    doc = win.document,
    docEl = doc.documentElement,
    metaEl = doc.querySelector('meta[name="viewport"]'),
    flexibleEl = doc.querySelector('meta[name="flexible"]');
  if (metaEl) {
    var match = metaEl
      .getAttribute("content")
      .match(/initial\-scale=(["']?)([\d\.]+)\1?/);
    match && ((scale = parseFloat(match[2])), (dpr = parseInt(1 / scale)));
  } else if (flexibleEl) {
    var match2 = flexibleEl
      .getAttribute("content")
      .match(/initial\-dpr=(["']?)([\d\.]+)\1?/);
    match2 &&
      ((dpr = parseFloat(match2[2])),
      (scale = parseFloat((1 / dpr).toFixed(2))));
  }
  if (!dpr && !scale) {
    var k =
        (win.navigator.appVersion.match(/android/gi),
        win.navigator.appVersion.match(/iphone/gi)),
      devicePixelRatio = win.devicePixelRatio;
    (dpr = k ? (devicePixelRatio >= 3 ? 3 : devicePixelRatio >= 2 ? 2 : 1) : 1),
      (scale = 1 / dpr);
  }
  if ((docEl.setAttribute("data-dpr", dpr), !metaEl))
    if (
      ((metaEl = doc.createElement("meta")),
      metaEl.setAttribute("name", "viewport"),
      metaEl.setAttribute(
        "content",
        "initial-scale=" +
          scale +
          ", maximum-scale=" +
          scale +
          ", minimum-scale=" +
          scale +
          ", user-scalable=no"
      ),
      docEl.firstElementChild)
    ) {
      docEl.firstElementChild.appendChild(metaEl);
    } else {
      var l = doc.createElement("div");
      l.appendChild(metaEl), doc.write(l.innerHTML);
    }
  (win.dpr = dpr),
    win.addEventListener(
      "resize",
      function () {
        clearTimeout(tid), (tid = setTimeout(refreshRem, 300));
      },
      !1
    ),
    win.addEventListener(
      "pageshow",
      function (e) {
        e.persisted && (clearTimeout(tid), (tid = setTimeout(refreshRem, 300)));
      },
      !1
    ),
    "complete" === doc.readyState
      ? (doc.body.style.fontSize = 12 * dpr + "px")
      : doc.addEventListener(
          "DOMContentLoaded",
          function () {
            doc.body.style.fontSize = 12 * dpr + "px";
          },
          !1
        ),
    refreshRem();
})(window);
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
      .pic {
        width: 26.66%;
      }
    </style>
  </head>
  <body>
    <img
      class="pic"
      src="D:\Frey\Documents\CodeStudy\WebStorm_Projects\test\晓舟报告学习笔记\css\css-还原设计稿-作业\images\fepic.png"
      alt=""
    />
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
      /* .em{
             font-size:20px;
         } */
      html {
        font-size: 10px;
      }
      .em-box {
        /* width: 10em;
             height: 10em; */
        width: 10rem;
        height: 10rem;
        background-color: red;
      }
    </style>
  </head>
  <body>
    <div class="em">
      <div class="em-box"></div>
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
        width: 15rem;
        height: 15rem;
        border: 1px solid red;
      }
    </style>
    <script>
      //copy from taobao
      !(function (win) {
        function refreshRem() {
          var width = docEl.getBoundingClientRect().width;
          width / dpr > 540 && (width = 540 * dpr),
            (win.rem = width / 16),
            (docEl.style.fontSize = win.rem + "px");
        }
        var dpr,
          scale,
          tid,
          doc = win.document,
          docEl = doc.documentElement,
          metaEl = doc.querySelector('meta[name="viewport"]'),
          flexibleEl = doc.querySelector('meta[name="flexible"]');
        if (metaEl) {
          var match = metaEl
            .getAttribute("content")
            .match(/initial\-scale=(["']?)([\d\.]+)\1?/);
          match &&
            ((scale = parseFloat(match[2])), (dpr = parseInt(1 / scale)));
        } else if (flexibleEl) {
          var match2 = flexibleEl
            .getAttribute("content")
            .match(/initial\-dpr=(["']?)([\d\.]+)\1?/);
          match2 &&
            ((dpr = parseFloat(match2[2])),
            (scale = parseFloat((1 / dpr).toFixed(2))));
        }
        if (!dpr && !scale) {
          var k =
              (win.navigator.appVersion.match(/android/gi),
              win.navigator.appVersion.match(/iphone/gi)),
            devicePixelRatio = win.devicePixelRatio;
          (dpr = k
            ? devicePixelRatio >= 3
              ? 3
              : devicePixelRatio >= 2
              ? 2
              : 1
            : 1),
            (scale = 1 / dpr);
        }
        if ((docEl.setAttribute("data-dpr", dpr), !metaEl))
          if (
            ((metaEl = doc.createElement("meta")),
            metaEl.setAttribute("name", "viewport"),
            metaEl.setAttribute(
              "content",
              "initial-scale=" +
                scale +
                ", maximum-scale=" +
                scale +
                ", minimum-scale=" +
                scale +
                ", user-scalable=no"
            ),
            docEl.firstElementChild)
          ) {
            docEl.firstElementChild.appendChild(metaEl);
          } else {
            var l = doc.createElement("div");
            l.appendChild(metaEl), doc.write(l.innerHTML);
          }
        (win.dpr = dpr),
          win.addEventListener(
            "resize",
            function () {
              clearTimeout(tid), (tid = setTimeout(refreshRem, 300));
            },
            !1
          ),
          win.addEventListener(
            "pageshow",
            function (e) {
              e.persisted &&
                (clearTimeout(tid), (tid = setTimeout(refreshRem, 300)));
            },
            !1
          ),
          "complete" === doc.readyState
            ? (doc.body.style.fontSize = 12 * dpr + "px")
            : doc.addEventListener(
                "DOMContentLoaded",
                function () {
                  doc.body.style.fontSize = 12 * dpr + "px";
                },
                !1
              ),
          refreshRem();
      })(window);
    </script>
  </head>
  <body>
    <div class="container">
      <div class="box">111</div>
    </div>
  </body>
</html>
```

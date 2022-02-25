# 1 HTML 类型
推荐使用 HTML5 的文档类型申明： .
（建议使用 text/html 格式的 HTML。避免使用 XHTML。XHTML 以及它的属性，比如 application/xhtml+xml 在浏览器中的应用支持与优化空间都十分有限）。

+ 规定字符编码
+ IE 兼容模式
+ 规定字符编码
+ doctype 大写
+ 规定语言lang=en

正例：
```html
<!DOCTYPE html>
<html>
  <head lang="en">
    <meta http-equiv="X-UA-Compatible" content="IE=Edge" />
    <meta charset="UTF-8" />
    <title>Page title</title>
  </head>
  <body>
    <img src="images/company-logo.png" alt="Company" />
  </body>
</html>
```

# 2 减少标签的数量,简化html结构
编写 HTML 代码时，尽量避免多余的父元素。很多时候，这需要迭代和重构来实现。请看下面的案例：
正例：
```html
<img class="avatar" src="...">
```

反例：
```html
<span class="avatar">
  <img src="...">
</span>
```

# 3 书写风格
## 3.1 HTML代码大小写
HTML标签名、类名、标签属性和大部分属性值统一用小写
正例：
```html
<div class="demo"></div>
```

反例：
```html
<div class="DEMO"></div>
	
<DIV CLASS="DEMO"></DIV>
```

## 3.2 类型属性
不需要为 CSS、JS 指定类型属性，HTML5 中默认已包含
正例：
```html
<link rel="stylesheet" href="">
<script src=""></script>
```
反例：
```html
<link rel="stylesheet" type="text/css" href="">
<script type="text/javascript" src=""></script>
```

## 3.3 语义化标签
HTML5 中新增很多语义化标签，所以优先使用语义化标签，避免一个页面都是 div 或者 p 标签

正例：
```html
<header></header>
<footer></footer>
```

反例：
```html
<div>
  <p></p>
</div>
```

## 3.4 代码嵌套
元素嵌套规范，每个块状元素独立一行，内联元素可选
正例：
```html
<div>
  <h1></h1>
  <p></p>
</div>	
<p><span></span><span></span></p>
```
或
```html
<div>
  <h1></h1>
  <p></p>
</div>	
<p>
  <span></span>
  <span></span>
</p>
```

反例：
```html
<div>
  <h1></h1><p></p>
</div>	
<p> 
  <span></span>
  <span></span>
</p>
```

## 3.5 缩进
缩进使用 2 个空格（一个 tab）
嵌套的节点应该缩进。

## 3.6 引号
使用双引号("") 而不是单引号('') 。
正例： ""
反例： ``

## 3.7 属性顺序
HTML 属性应该按照特定的顺序出现以保证易读性。
+ id
+ class
+ name
+ data-xxx
+ src, for, type, href
+ title, alt
+ aria-xxx, role

示例：
```html
<a class="..." id="..." data-toggle="modal" href="#">
  Example link
</a>

<input class="form-control" type="text">

<img src="..." alt="...">
```

# 4 JavaScript 生成的标签
通过 JavaScript 生成的标签让内容变得不易查找、编辑，并且降低性能。能避免时尽量避免。
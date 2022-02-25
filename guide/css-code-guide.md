# 1 代码风格
## 1.1 命名
+ 类名使用小写字母，以下划线分隔
  正例：
  ```css
  .header_menu {

  }
  ```
  反例：
  ```css
  .header-menu {

  }
  .HeaderMenu {

  }
  ```

+ id 采用驼峰式命名
  正例：
  ```css
  #headerMenu {

  }
  ```
  反例：
  ```css
  #header-menu {

  }
  #HeaderMenu {

  }
  ```

+ scss 中的变量、函数、混合、placeholder 采用驼峰式命名

+ ID 和 class 的名称总是使用可以反应元素目的和用途的名称，或其他通用的名称，代替表象和晦涩难懂的名称
  正例：
  ```css
  .banner {

  }
  ```
  反例：
  ```css
  .lb {

  }
  ```

  
## 1.2 代码格式化
样式书写一般有两种：紧凑格式 (Compact)、展开格式（Expanded），我们这里采用展开格式（Expanded）。

正例：
```css
.jdc {
  display: block;
  width: 50px;
}
```

反例：
```css
.jdc { display: block; width: 50px;}
```

## 1.3 代码大小写
样式选择器，属性名，属性值关键字全部使用小写字母书写，属性字符串允许使用大小写。
正例：
```css
.jdc {
  display: block;
}
```

反例：
```css
.JDC {
	DISPLAY: BLOCK;
}
```

## 1.4 缩进
缩进使用 2 个空格（一个 tab）。

正例：
```css
.jdc {
  display: block;
}
```
反例：
```css
.jdc {
    display: block;
}
```

## 1.5 样式区块格式
+ 为了代码的易读性，在每个声明块的左花括号前添加一个空格。
  正例：
  ```css
  .jdc {
    display: block;
  }
  ```
  反例：
  ```css
  .jdc{
    display: block;
  }
  ```

+ 声明块的右花括号应当单独成行。
  正例：
  ```css
  .jdc {
    display: block;
  }
  ```
  反例：
  ```css
  .jdc {
    display: block;}
  ```

+ 每条声明语句的 : 后应该插入一个空格。
  正例：
  ```css
  .jdc {
    display: block;
  }
  ```
  反例：
  ```css
  .jdc {
    display:block;
  }
  ```

+ 为了获得更准确的错误报告，每条声明都应该独占一行。
  正例：
  ```css
  .jdc {
    display: block;
    width: 30px;
  }
  ```
  反例：
  ```css
  .jdc {
    display: block; width: 30px;
  }
  ```

+ 为选择器分组时，将单独的选择器单独放在一行。
  正例：
  ```css
  .selector,
  .selector-secondary,
  .selector[type="text"] {
    padding: 15px;
  }
  ```
  反例：
  ```css
  .selector, .selector-secondary, .selector[type=text] {
    padding:15px;
  }
  ```

+ 避免为 0 值指定单位。
  正例：
  ```css
  .selector {
    padding: 0;
  }
  ```
  反例：
  ```css
  .selector {
    padding: 0px;
  }
  ```

+ 对于以逗号分隔的属性值，每个逗号后面都应该插入一个空格。
  正例：
  ```css
  .selector {
    box-shadow: 0 1px 2px #ccc, inset 0 1px 0 #fff;
  }
  ```
  反例：
  ```css
  .selector {
    box-shadow: 0 1px 2px #ccc,inset 0 1px 0 #fff;
  }
  ```

+ 对于属性值或颜色参数，省略小数前面的 0
  正例：
  ```css
  .selector {
    width: .5vw;
  }
  ```
  反例：
  ```css
  .selector {
    width: 0.5vw;
  }
  ```

+ 十六进制值应该全部小写，尽量使用简写形式。
  正例：
  ```css
  .selector {
    color: #fff;
  }
  ```
  反例：
  ```css
  .selector {
    color: #FFFFFF;
  }
  ```

+ 择器中的属性，为了代码的一致性，建议都加上单引号。
  ```css
  .input[type='text'] {

  }
  ```
  反例：
  ```css
  .input[type="text"] {

  }
  ```

+ css属性值需要用到引号时，统一使用单引号
  ```css
  .jdc { 
    font-family: 'Hiragino Sans GB';
  }
  ```
  反例：
  ```css
  .jdc { 
    font-family: "Hiragino Sans GB";
  }
  ```

## 1.6 避免使用ID选择器及全局标签选择器防止污染全局样式
正例：
```css
#header {
  padding-bottom: 0px;
  margin: 0em;
}
```
反例：
```css
#header {
  padding-bottom: 0px;
  margin: 0em;
}
```

## 1.7 CSS3浏览器私有前缀写法
示例：
```css
.jdc {
  -webkit-border-radius: 10px;
  -moz-border-radius: 10px;
  -o-border-radius: 10px;
  -ms-border-radius: 10px;
  border-radius: 10px;
}
```

## 1.8 属性书写顺序
建议遵循以下顺序：
1. 布局定位属性：display / position / float / clear / visibility / overflow
2. 自身属性：width / height / margin / padding / border / background
3. 文本属性：color / font / text-decoration / text-align / vertical-align / white- space / break-word
4. 其他属性（CSS3）：content / cursor / border-radius / box-shadow / text-shadow / background:linear-gradient …

示例：
示例：
```css
.jdc {
  display: block;
  position: relative;
  float: left;
  width: 100px;
  height: 100px;
  margin: 0 10px;
  padding: 20px 0;
  font-family: Arial, 'Helvetica Neue', Helvetica,sans-serif;
  color: #333;
  background: rgba(0,0,0,.5);
  -webkit-border-radius: 10px;
  -moz-border-radius: 10px;
  -o-border-radius: 10px;
  -ms-border-radius: 10px;
  border-radius: 10px;
}
```

## 1.9 >、+、~ 选择器的两边各保留一个空格
正例：
```css
main > nav {
  padding: 10px;
}

label + input {
  margin-left: 5px;
}

input:checked ~ button {
  background-color: #69C;
}
```

反例：
```css
main>nav {
    padding: 10px;
}

label+input {
    margin-left: 5px;
}

input:checked~button {
    background-color: #69C;
}
```

## 1.10 url()
url() 函数中的路径不加引号
正例：
```css
body {
  background: url(./bg.png);
}
```

反例：
```css
body {
  background: url('./bg.png');
}
```

## 1.11 嵌套
使用scss、sass、less 应避免过深的嵌套

# 2 媒体查询（Media query）的位置
将媒体查询放在尽可能相关规则的附近。不要将他们打包放在一个单一样式文件中或者放在文档底部。如果你把他们分开了，将来只会被大家遗忘。下面给出一个典型的实例。
示例：
```css
.element { ... }
.element-avatar { ... }
.element-selected { ... }

@media (min-width: 480px) {
  .element { ...}
  .element-avatar { ... }
  .element-selected { ... }
}
```

# 3 不要使用 @import
与 <link> 相比，@import 要慢很多，不光增加额外的请求数，还会导致不可预料的问题。

替代办法：

+ 使用多个 元素；
+ 通过 Sass 或 Less 类似的 CSS 预处理器将多个 CSS 文件编译为一个文件；
+ 其他 CSS 文件合并工具；
 
# 4 （禁止）使用行内（inline）样式
正例：
```html
<p style="style"></p>
```
```css
.style{
  font-size: 12px;
  color: #fff;
}
```

反例：
```html
<p style="font-size: 12px; color: #fff;"></p>
```

# 5 样式优先级
尽量使用权重去增加样式优先级
尽量不使用 !important 声明

# 6 变换与动画
使用 transition 时应指定 transition-property
正例：
```css
.box {
  transition: color 1s, border-color 1s;
}
```

反例：
```css
.box {
  transition: all 1s;
}
```
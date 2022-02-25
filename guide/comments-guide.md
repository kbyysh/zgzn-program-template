# 1 文件注释
文件开头应包含以下注释:
+ @author 文件创建人姓名
+ @date 创建日期
+ @description 文件说明，说明文件用途、包含哪些类容

javascript:
snippets: 快捷语法 jsHeader
```javascript
/**
 * @author: your name
 * @date: 2022-02-15 15:43:33
 * @description: XXXXXXXXXXXXXXXXXXXXXXXX
 * **/
```

html:
snippets: 快捷语法 htmlHeader
```html
<!--
 * @author: your name
 * @date: 2022-02-15 15:43:33
 * @description: XXXXXXXXXXXXXXXXXXXXXXXX
-->
```


css:
snippets: 快捷语法 cssHeader
```css
/**
 * @author: your name
 * @date: 2022-02-15 15:43:33
 * @description: XXXXXXXXXXXXXXXXXXXXXXXX
 */
```

# 1 HTML注释
## 1.1 单行注释
+ 一般用于简单的描述，如某些状态描述、属性描述等
+ 注释内容前后各一个空格字符，注释位于要注释代码的上面，单独占一行
+ 
推荐：
```html
snippets: 快捷语法 htmlLine
<!-- banner -->
<div class="banner"></div>
```
不推荐：
```html
<div class="banner"></div><!-- banner -->
```

## 1.2 模块注释
html应该分模块注释，这样代码可读性更高，维护起来更加便捷。
+ 注释内容前后各一个空格字符
+ <!-- start Comment Text -->表示模块开始
+ <!-- end Comment Text -->表示模块结束，模块与模块之间相隔一行

snippets: 快捷语法 htmlLine

```html
<!-- start banner -->
<div class="banner"></div>
<!-- end banner -->

<!-- start main -->
<div class="banner"></div>
<!-- end main -->
```

# 2 css 注释
+ 注释以字符 /* 开始，以字符 */ 结束
+ 注释不能嵌套

## 2.1 单行注释
注释内容第一个字符和最后一个字符都是一个空格字符，单独占一行，行与行之间相隔一行
snippets: 快捷语法 cssLine
推荐：
```css
/* Comment Text */
.jdc{}

/* Comment Text */
.jdc{}
```
不推荐：
```css
/*Comment Text*/
.jdc{
  display: block;
}
.jdc{
  display: block;/*Comment Text*/
}
```

## 2.2 模块注释
css应该分模块注释，这样代码可读性更高，维护起来更加便捷。
+ 注释内容前后各一个空格字符
+ /* start module_one */表示模块开始
+ /* end module_one */表示模块结束，模块与模块之间相隔一行

snippets: 快捷语法 cssLine

```css
/* start module_one */
.module_one {}
/* end module_one */
```

# 3 javascript
## 3.1 类注释
类开头应包含以下注释，有一个param就应该包含一个@param的注释
+ @class 类名
+ @author 创建人姓名
+ @param 构造函数参数说明 参数名 类型 描述
+ @description 说明

snippets: 快捷语法 jsClass

```javascript
/**
 * @class: class name
 * @author: your name
 * @param: constructor need param
 * @param: constructor need param
 * @description: XXXXXXXXXXXXXXXXXXXXXXXX
 * **/
```

## 3.2 事件注释
事件开头应包含以下注释，有一个param就应该包含一个@param的注释
+ @event 事件名
+ @author 创建人姓名
+ @param 事件所需参数说明 参数名 类型 描述
+ @description 说明

snippets: 快捷语法 jsEvent

```javascript
/**
 * @event: event name
 * @author: your name
 * @param: event need param
 * @param: event need param
 * @description: XXXXXXXXXXXXXXXXXXXXXXXX
 * **/
```

## 3.3 函数/方法注释
函数/方法开头应包含以下注释，有一个param就应该包含一个@param的注释
+ @method 函数/方法名称
+ @author 创建人姓名
+ @param 函数/方法所需参数说明 参数名 类型 描述
+ @return 返回值说明 （如果没有返回值可省略）
+ @description 说明

snippets: 快捷语法 jsMethod

```javascript
/**
 * @method: event name
 * @author: your name
 * @param: event need param
 * @param: event need param
 * @return: return value description
 * @description: XXXXXXXXXXXXXXXXXXXXXXXX
 * **/
```

## 3.4 细节注释
细节注释遵循单行注释或多行注释的格式。
```javascript
function foo(p1, p2, opt_p3) {
  // 这里对具体内部逻辑进行说明
  // 说明太长需要换行
  for (...) {
    ....
  }
}

function foo(p1, p2, opt_p3) {
  /**
   * 这里对具体内部逻辑进行说明
   * 说明太长需要换行
   * **/
  for (...) {
    ....
  }
}
```

# 4 typescript
参考javascript

## 4.1 类注释
snippets: 快捷语法 jsClass

## 4.2 事件注释
snippets: 快捷语法 jsEvent

## 4.3 函数/方法注释
snippets: 快捷语法 jsMethod

# 5 less/scss
参考css注释

## 5.1 文件头部注释
snippets: 快捷语法 cssHeader

## 5.2 单行注释
snippets: 快捷语法 cssLine

# 6 vue
## 5.1 文件头部注释
snippets: 快捷语法 vHeader

## 5.2 单行注释 (template)
snippets: 快捷语法 vLine

## 5.3 css/js
css/js注释与上面规则一致
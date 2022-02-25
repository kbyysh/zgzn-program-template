# 1 命名规范
## 1.1 命名应具有描述意义, 不能以简写或中文拼音等命名，应该使用具有描述意义的英文单词来命名。
正例：
```javascript
let step = 0;
function add () {
  step++
}
```

反例：
```javascript
let s = 0;
function a () {
  s++
}
```

## 1.2 当命名对象、函数和实例时使用Camel命名规则
正例：
```javascript
let thisIsMyObject = {};
function thisIsMyFunction() {};
let user = new User({
  name: 'Bob Parr'
});
```

反例：
```javascript
let OBJEcttsssss = {};
let this_is_my_object = {};
let this-is-my-object = {};
function c() {};
let u = new user({
  name: 'Bob Parr'
});
```

## 1.3 当命名构造函数或类时使用Pascal规则
正例：
```javascript
function User(options) {
  this.name = options.name;
}

let good = new User({
  name: 'yup'
});
```

反例：
```javascript
function user(options) {
  this.name = options.name;
}

let bad = new user({
  name: 'nope'
});
```

## 1.4 命名私有属性时前面加个下划线 _
正例：
```javascript
this._firstName = 'Panda';
```

反例：
```javascript
this.__firstName__ = 'Panda';
this.firstName_ = 'Panda';
```

## 1.5 处理this指向问题统一使用 self 命名
正例：
```javascript
let self = this
let _self = this
```

反例：
```javascript
let _this_ = this
let _ccc = this
```

## 1.6 枚举变量 使用 Pascal命名法，枚举的属性 使用 全部字母大写，单词间下划线分隔 的命名方式。
正例：
```javascript
let TargetState = {
  READING: 1
  READY: 4,
  READ_STATE
};
```

反例：
```javascript
let targetState = {
  reading: 1,
  ready: 4,
  READSTATE: 2
};
```

## 1.7 常量命名全部大写，单词间用下划线隔开，力求语义表达完整清楚，不要嫌名字长
正例： ```textMAX_COUNT```

反例： ```textmax_count```

## 1.8 method / Promise 方法命名必须是 动词 或者 动词+名词 形式
正例：```textsaveShopCarData /openShopCarInfoDialog```

反例：```textsave / open / show / go```

+ 特此说明，增删查改，详情统一使用如下 5 个单词，不得使用其他
```text
add / update / delete / detail / get
```

+ 函数方法常用的动词
```text
get 获取/set 设置,
add 增加/remove 删除
create 创建/destory 移除
start 启动/stop 停止
open 打开/close 关闭,
read 读取/write 写入
load 载入/save 保存,
create 创建/destroy 销毁
begin 开始/end 结束,
backup 备份/restore 恢复
import 导入/export 导出,
split 分割/merge 合并
inject 注入/extract 提取,
attach 附着/detach 脱离
bind 绑定/separate 分离,
view 查看/browse 浏览
edit 编辑/modify 修改,
select 选取/mark 标记
copy 复制/paste 粘贴,
undo 撤销/redo 重做
insert 插入/delete 移除,
add 加入/append 添加
clean 清理/clear 清除,
index 索引/sort 排序
find 查找/search 搜索,
increase 增加/decrease 减少
play 播放/pause 暂停,
launch 启动/run 运行
compile 编译/execute 执行,
debug 调试/trace 跟踪
observe 观察/listen 监听,
build 构建/publish 发布
input 输入/output 输出,
encode 编码/decode 解码
encrypt 加密/decrypt 解密,
compress 压缩/decompress 解压缩
pack 打包/unpack 解包,
parse 解析/emit 生成
connect 连接/disconnect 断开,
send 发送/receive 接收
download 下载/upload 上传,
refresh 刷新/synchronize 同步
update 更新/revert 复原,
lock 锁定/unlock 解锁
check out 签出/check in 签入,
submit 提交/commit 交付
push 推/pull 拉,
expand 展开/collapse 折叠
begin 起始/end 结束,
start 开始/finish 完成
enter 进入/exit 退出,
abort 放弃/quit 离开
obsolete 废弃/depreciate 废旧,
collect 收集/aggregate 聚集
```

## 1.9 boolean 类型的变量使用 is 或 has 开头
```javascript
let isReady = false;
let hasMoreCommands = false;
```

# 2 文件
JavaScript 文件使用无 BOM 的 UTF-8 编码。
UTF-8 编码具有更广泛的适应性。BOM 在使用程序或工具处理文件时可能造成不必要的干扰。

# 3 结构
## 3.1 缩进
使用 2 个空格 或 tab 字符进行缩进。

## 3.2 空格
### 3.2.1 运算符、对象
+ 一元运算符与操作对象之间不允许有空格
+ 二元运算符、比较运算符两侧必须有一个空格
+ 三元表达式条件与结果之间必须有一个空格
+ 逻辑运算符 && 、 || 前后必须有一个空格

示例：
```javascript
let a = !arr.length;
a++;
a = b + c;

if (a > b) {}

let result = isBoolean ? a : b;

if (a && b) {}

if (a || b) {}
```

### 3.2.2 代码块起始的左花括号 { 前必须有一个空格。
正例：
```javascript
if (condition) {}

while (condition) {}

function funcName() {}
```

反例：
```javascript
if (condition){}

while (condition){}

function funcName(){}
```

### 3.2.3 关键字
if / else / for / while / function / switch / do / try / catch / finally 关键字后，必须有一个空格。
正例：
```javascript
if (condition) {}

while (condition) {}

(function () {})();
```

反例：
```javascript
if(condition) {}

while(condition) {}

(function() {})();
```

### 3.2.4 属性
在对象创建时，属性中的 : 之后必须有空格，: 之前不允许有空格。
正例：
```javascript
let obj = {
  a: 1,
  b: 2,
  c: 3
};
```

反例：
```javascript
let obj = {
  a : 1,
  b:2,
  c :3
};
```

### 3.2.5 函数声明、具名函数表达式、函数调用中，函数名和 ( 之间不允许有空格
正例：
```javascript
function funcName() {}

let funcName = function funcName() {};

funcName();
```

反例：
```javascript
function funcName () {}

let funcName = function funcName () {};

funcName ();
```

### 3.2.6 ,和；
, 和 ; 前不允许有空格。如果不位于行尾，, 和 ; 后必须跟一个空格。
正例：
```javascript
callFunc(a, b);
```

反例：
```javascript
callFunc(a , b) ;
```

### 3.2.7 在函数调用、函数声明、括号表达式、属性访问、if / for / while / switch / catch 等语句中，() 和 [] 内紧贴括号部分不允许有空格
正例：
```javascript
callFunc(param1, param2, param3);

save(this.list[this.indexes[i]]);

needIncrement && (variable += increment);

if (num > list.length) {}

while (len--) {}
```

反例：
```javascript
callFunc( param1, param2, param3 );

save( this.list[ this.indexes[ i ] ] );

needIncrement && ( variable += increment );

if ( num > list.length ) {}

while ( len-- ) {}
```

### 3.2.8 单行声明的数组与对象，如果包含元素，{} 和 [] 内紧贴括号部分不允许包含空格
声明包含元素的数组与对象，只有当内部元素的形式较为简单时，才允许写在一行。元素复杂的情况，还是应该换行书写。
正例：
```javascript
let arr1 = [];
let arr2 = [1, 2, 3];
let obj1 = {};
let obj2 = {name: 'obj'};
let obj3 = {
  name: 'obj',
  age: 20,
  sex: 1
};
```

反例：
```javascript
let arr1 = [ ];
let arr2 = [ 1, 2, 3 ];
let obj1 = { };
let obj2 = { name: 'obj' };
let obj3 = {name: 'obj', age: 20, sex: 1};
```

### 3.2.9 行尾不得有多余的空格

## 3.3 换行

### 3.3.1 每个独立语句结束后必须换行
正例：
```javascript
let arr1 = [];
let arr2 = [1, 2, 3];
```

反例：
```javascript
let arr1 = []; let arr2 = [1, 2, 3];
```

### 3.3.2 为了阅读代码的方便，单行代码长度不宜过长

### 3.3.3 运算符处换行时，运算符必须在新行的行首
正例：
```javascript
if (user.isAuthenticated()
  && user.isInRole('admin')
  && user.hasAuthority('add-admin')
  || user.hasAuthority('delete-admin')
) {
  // Code
}

let result = number1 + number2 + number3
  + number4 + number5;
```

反例：
```javascript
if (user.isAuthenticated() &&
  user.isInRole('admin') &&
  user.hasAuthority('add-admin') ||
  user.hasAuthority('delete-admin')
) {
  // Code
}

let result = number1 + number2 + number3 +
  number4 + number5;
```

### 3.3.4 在函数声明、函数表达式、函数调用、对象创建、数组创建、for 语句等场景中，不允许在 , 或 ; 前换行
正例：
```javascript
let obj = {
  a: 1,
  b: 2,
  c: 3
};

foo(
  aVeryVeryLongArgument,
  anotherVeryLongArgument,
  callback
);
```

反例：
```javascript
let obj = {
  a: 1
  , b: 2
  , c: 3
};

foo(
  aVeryVeryLongArgument
  , anotherVeryLongArgument
  , callback
);
```

### 3.3.5 不同行为或逻辑的语句集，使用空行隔开，更易阅读
示例：
```javascript
function setStyle(element, property, value) {
  if (element == null) {
    return;
  }

  element.style[property] = value;
}
```

### 3.3.6 在语句的行长过长时，根据逻辑条件合理缩进
示例：
```javascript
// 较复杂的逻辑条件组合，将每个条件独立一行，逻辑运算符放置在行首进行分隔，或将部分逻辑按逻辑组合进行分隔。
// 建议最终将右括号 ) 与左大括号 { 放在独立一行，保证与 `if` 内语句块能容易视觉辨识。
if (user.isAuthenticated()
  && user.isInRole('admin')
  && user.hasAuthority('add-admin')
  || user.hasAuthority('delete-admin')
) {
  // Code
}

if (
  user.isAuthenticated()
  &&
  user.isInRole('admin')
  &&
  user.hasAuthority('add-admin')
  ||
  user.hasAuthority('delete-admin')
) {
  // Code
}

// 按一定长度截断字符串，并使用 + 运算符进行连接。
// 分隔字符串尽量按语义进行，如不要在一个完整的名词中间断开。
// 特别的，对于 HTML 片段的拼接，通过缩进，保持和 HTML 相同的结构。
let html = '' // 此处用一个空字符串，以便整个 HTML 片段都在新行严格对齐
  + '<article>'
  +     '<h1>Title here</h1>'
  +     '<p>This is a paragraph</p>'
  +     '<footer>Complete</footer>'
  + '</article>';

// 也可使用数组来进行拼接，相对 `+` 更容易调整缩进。
let html = [
  '<article>',
    '<h1>Title here</h1>',
    '<p>This is a paragraph</p>',
    '<footer>Complete</footer>',
  '</article>'
];
// 模板字符串
let html = `
    <article>
      <h1>Title here</h1>
      <p>This is a paragraph</p>
      <footer>Complete</footer>
    </article>
  `;
let html = `<article>
    <h1>Title here</h1>
    <p>This is a paragraph</p>
    <footer>Complete</footer>
  </article>`;

// 当参数过多时，将每个参数独立写在一行上，并将结束的右括号 ) 独立一行。
// 所有参数必须增加一个缩进。
foo(
  aVeryVeryLongArgument,
  anotherVeryLongArgument,
  callback
);

// 也可以按逻辑对参数进行组合。
// 最经典的是 baidu.format 函数，调用时将参数分为“模板”和“数据”两块
baidu.format(
  dateFormatTemplate,
  year, month, date, hour, minute, second
);

// 当函数调用时，如果有一个或以上参数跨越多行，应当每一个参数独立一行。
// 这通常出现在匿名函数或者对象初始化等作为参数时，如 `setTimeout` 函数等。
setTimeout(
  function () {
    alert('hello');
  },
  200
);

order.data.read(
  'id=' + me.model.id,
  function (data) {
    me.attachToModel(data.result);
    callback();
  },
  300
);

// 链式调用较长时采用缩进进行调整。
$('#items')
  .find('.selected')
  .highlight()
  .end();

// 三元运算符由3部分组成，因此其换行应当根据每个部分的长度不同，形成不同的情况。
let result = thisIsAVeryVeryLongCondition
  ? resultA : resultB;

let result = condition
  ? thisIsAVeryVeryLongResult
  : resultB;

// 数组和对象初始化的混用，严格按照每个对象的 `{` 和结束 `}` 在独立一行的风格书写。
var array = [
  {
    // ...
  },
  {
    // ...
  }
];
```

## 3.4 语句
### 3.4.1 不得省略语句结束的分号
在 if / else / for / do / while 语句中，即使只有一行，也不得省略块 {...}。
正例：
```javascript
if (condition) {
  callFunc();
}
```

反例：
```javascript
if (condition) callFunc();
if (condition)
  callFunc();
```

### 3.4.2 函数定义结束不允许添加分号
正例：
```javascript
function funcName() {}
```

反例：
```javascript
function funcName() {};
```

如果是函数表达式，分号是不允许省略的。
```javascript
let funcName = function () {};
```

# 4 类型
## 4.1 类型检测
类型检测优先使用 typeof。对象类型检测使用 instanceof。null 或 undefined 的检测使用 == null。
示例：
```javascript
// string
typeof variable === 'string'

// number
typeof variable === 'number'

// boolean
typeof variable === 'boolean'

// Function
typeof variable === 'function'

// Object
typeof variable === 'object'

// RegExp
variable instanceof RegExp

// Array
variable instanceof Array

// null
variable === null

// null or undefined
variable == null

// undefined
typeof variable === 'undefined'
```

## 4.2 类型转换
### 4.2.1 转换成 string
推荐：
```javascript
num + '';
String(num);
```
不推荐：
```javascript
new String(num);
num.toString();
```

### 4.2.2 转换成 number
示例：
```javascript
+str;
Number(str);
parseInt(str);
```

### 4.2.3 转换成 boolean 时，使用 !!
示例：
```javascript
let num = 3.14;
!!num;
```

### 4.2.4 number 去除小数点
正例：
```javascript
let num = 3.14;
Math.ceil(num);
```
反例：
```javascript
let num = 3.14;
parseInt(num, 10);
```

# 5 变量
## 5.1 定义变量
+ 使用 const 或者 let 来定义变量
  正例：
  ```javascript
  const superPower = new SuperPower();
  ```

  反例：
  ```javascript
  superPower = new SuperPower();
  ```

+ 使用 const 或者 let 声明每一个变量
  正例：
  ```javascript
  const items = getItems();
  const goSportsTeam = true;
  const dragOnBall = 'z';
  ```

  反例：
  ```javascript
  const items = getItems(),
    goSportsTeam = true,
    dragOnBall = 'z';
  ```

+ 不要链式变量赋值
链式变量赋值会创建隐式全局变量。
  正例：
  ```javascript
  (function example() {
    let a = 1;
    let b = a;
    let c = a;
  }());

  console.log(a); // throws ReferenceError
  console.log(b); // throws ReferenceError
  console.log(c); // throws ReferenceError
  ```

  反例：
  ```javascript
  (function example() {
    // JavaScript 把它解释为
    // let a = ( b = ( c = 1 ) );
    // let 关键词只适用于变量 a ；变量 b 和变量 c 则变成了全局变量。
    let a = b = c = 1;
  }());

  console.log(a); // throws ReferenceError
  console.log(b); // 1
  console.log(c); // 1
  ```


+ 把 const 声明的放在一起，把 let 声明的放在一起
  正例：
  ```javascript
  const goSportsTeam = true;
  const items = getItems();
  let dragOnBall;
  let i;
  let length;
  ```

  反例：
  ```javascript
  let i;
  const items = getItems();
  let dragOnBall;
  const goSportsTeam = true;
  let len;
  ```

+ 在你需要的使用定义变量，但是要把它们放在一个合理的地方
  为什么? let 和 const 是块级作用域而不是函数作用域。
  正例：
  ```javascript
  function checkName(hasName) {
    if (hasName === 'test') {
      return false;
    }

    const name = getName();

    if (name === 'test') {
      this.setName('');
      return false;
    }

    return name;
  }
  ```

  反例：
  ```javascript
  function checkName(hasName) {
    const name = getName();

    if (hasName === 'test') {
      return false;
    }

    if (name === 'test') {
      this.setName('');
      return false;
    }

    return name;
  }
  ```

## 5.2 避免使用不必要的递增和递减 (++, --)
为什么? 在eslint文档中，一元递增和递减语句以自动分号插入为主题，并且在应用程序中可能会导致默认值的递增或递减。它还可以用像 num += 1 这样的语句来改变您的值，而不是使用 num++ 或 num ++ 。不允许不必要的增量和减量语句也会使您无法预先递增/预递减值，这也会导致程序中的意外行为。
正例：
```javascript
const array = [1, 2, 3];
let num = 1;
num += 1;
num -= 1;

const sum = array.reduce((a, b) => a + b, 0);
const truthyCount = array.filter(Boolean).length;
```

反例：
```javascript
const array = [1, 2, 3];
let num = 1;
num++;
--num;

let sum = 0;
let truthyCount = 0;
for (let i = 0; i < array.length; i++) {
  let value = array[i];
  sum += value;
  if (value) {
    truthyCount++;
  }
}
```

## 5.3 避免在赋值语句 = 前后换行
正例：
```javascript
const foo = (
  superLongLongLongLongLongLongLongLongFunctionName()
);

const foo = 'superLongLongLongLongLongLongLongLongString';
```

反例：
```javascript
const foo =
  superLongLongLongLongLongLongLongLongFunctionName();

const foo
  = 'superLongLongLongLongLongLongLongLongString';
```

# 6 条件、比较运算符
## 6.1 使用 === 和 !== 而不是 == 和 !=
使用 === 可以避免等于判断中隐式的类型转换。

## 6.2 条件语句
例如 if 语句使用 ToBoolean 的抽象方法来计算表达式的结果，并始终遵循以下简单的规则：
+ Objects 的取值为： true
+ Undefined 的取值为： false
+ Null 的取值为： false
+ Booleans 的取值为： 布尔值的取值
+ Numbers 的取值为：如果为 +0, -0, or NaN 值为 false 否则为 true
+ Strings 的取值为: 如果是一个空字符串 '' 值为 false 否则为 true

示例：
```javascript
if ([0] && []) {
  // true
  // 一个数组（即使是空的）是一个对象，对象的取值为 true
}
```

## 6.3 对于布尔值使用简写，但是对于字符串和数字进行显式比较
正例：
```javascript
if (isValid) {
  // ...
}

if (name !== '') {
  // ...
}

if (collection.length > 0) {
  // ...
}
```

反例：
```javascript
if (isValid === true) {
  // ...
}

if (name) {
  // ...
}

if (collection.length) {
  // ...
}
```

## 6.4 避免不必要的三目表达式
正例：
```javascript
const foo = a || b;
const bar = !!c;
const baz = !c;
```

反例：
```javascript
const foo = a ? a : b;
const bar = c ? true : false;
const baz = c ? false : true;
```

## 6.5 对于相同变量或表达式的多值条件，用 switch 代替 if
正例：
```javascript
switch (typeof variable) {
  case 'object':
    // ......
    break;
  case 'number':
  case 'boolean':
  case 'string':
    // ......
    break;
}
```

反例：
```javascript
let type = typeof variable;
if (type === 'object') {
  // ......
} else if (
  type === 'number'
  ||
  type === 'boolean'
  ||
  type === 'string'
) {
  // ......
}
```

## 6.6 条件判断和循环最多三层
条件判断能使用三目运算符和逻辑运算符解决的，就不要使用条件判断，但是谨记不要写太长的三目运算符。如果超过 3 层请抽成函数，并写清楚注释。

# 7 字符串
## 7.1 使用单引号 '' 定义字符串
输入单引号不需要按住 shift，方便输入。
实际使用中，字符串经常用来拼接 HTML。为方便 HTML 中包含双引号而不需要转义写法。
正例：
```javascript
const name = 'Capt. Janeway';
let html = '<div class="banner"></div>'
```

反例：
```javascript
const name = "Capt. Janeway";
```

## 7.2 当以编程模式构建字符串时，使用字符串模板代替字符串拼接
正例：
```javascript
function sayHi(name) {
  return `How are you, ${ name }?`;
}
```

反例：
```javascript
function sayHi(name) {
  return 'How are you, ' + name + '?';
}

function sayHi(name) {
  return ['How are you, ', name, '?'].join();
}
```


# 8 对象
## 8.1 使用对象字面量 {} 创建新 Object
正例：
```javascript
let obj = {};
```

反例：
```javascript
let obj = new Object();
```

## 8.2 对象创建时，所有属性均不添加引号，只使用引号标注无效标识符的属性
正例：
```javascript
let info = {
  name: 'someone',
  age: 28,
  'data-blah': 5 // 这样的的属性名称必须加引号
};
```

反例：
```javascript
let info = {
  'name': 'someone',
  'age': 28
};
```

## 8.3 属性访问时，尽量使用 .
属性名符合 Identifier 的要求，就可以通过 . 来访问，否则就只能通过 [expr] 方式访问。

通常在 JavaScript 中声明的对象，属性命名是使用 Camel 命名法，用 . 来访问更清晰简洁。部分特殊的属性（比如来自后端的 JSON ），可能采用不寻常的命名方式，可以通过 [expr] 方式访问。
示例：
```javascript
info.age;
info['more-info'];
```

## 8.4 在创建具有动态属性名称的对象时使用计算属性名
为什么? 它允许你在一个地方定义对象的所有属性。
正例：
```javascript
function getKey(k) {
  return `a key named ${k}`;
}

const obj = {
  id: 5,
  name: 'San Francisco',
  [getKey('enabled')]: true
};
```

反例：
```javascript
function getKey(k) {
  return `a key named ${k}`;
}

const obj = {
  id: 5,
  name: 'San Francisco',
};
obj[getKey('enabled')] = true;
```

## 8.5 使用对象方法的缩写
正例：
```javascript
const atom = {
  value: 1,
  addValue(value) {
    return atom.value + value;
  },
};
```

反例：
```javascript
const atom = {
  value: 1,
  addValue: function (value) {
    return atom.value + value;
  },
};
```

## 8.6 使用属性值的缩写
正例：
```javascript
const lukeSkywalker = 'Luke Skywalker';
const obj = {
  lukeSkywalker,
};
```

反例：
```javascript
const lukeSkywalker = 'Luke Skywalker';
const obj = {
  lukeSkywalker: lukeSkywalker,
};
```

## 8.7 在对象声明的时候将简写的属性进行分组
正例：
```javascript
const anakinSkywalker = 'Anakin Skywalker';
const lukeSkywalker = 'Luke Skywalker';
const obj = {
  lukeSkywalker,
  anakinSkywalker,
  episodeOne: 1,
  twoJediWalkIntoACantina: 2,
  episodeThree: 3,
  mayTheFourth: 4,
};
```

反例：
```javascript
const anakinSkywalker = 'Anakin Skywalker';
const lukeSkywalker = 'Luke Skywalker';
const obj = {
  episodeOne: 1,
  twoJediWalkIntoACantina: 2,
  lukeSkywalker,
  episodeThree: 3,
  mayTheFourth: 4,
  anakinSkywalker,
};
```

## 8.8 使用展开运算符...代替Object.assign()

# 9 数组
## 9.1 使用字面语法创建数组
正例：
```javascript
const items = [];
```

反例：
```javascript
const items = new Array();
```

## 9.2 使用 Array#push 取代直接赋值来给数组添加项
正例：
```javascript
const someStack = [];
someStack.push('abracadabra');
```

反例：
```javascript
const someStack = [];
someStack[someStack.length] = 'abracadabra';
```

## 9.3 使用数组展开方法 ... 来拷贝数组
示例：
```javascript
const itemsCopy = [...items]
```

## 9.4 将一个类数组对象转换成一个数组， 使用展开方法 ... 代替 Array.from
示例：
```javascript
const foo = document.querySelectorAll('.foo');

// good
const nodes = Array.from(foo);

// best
const nodes = [...foo];
```

## 9.5 对于对迭代器的映射，使用 Array.from 替代展开方法 ... ， 因为它避免了创建中间数组
正例：
```javascript
const baz = Array.from(foo, bar);
```

反例：
```javascript
const baz = [...foo].map(bar);
```

## 9.6 如果数组有多行，则在开始的时候换行，然后在结束的时候换行
正例：
```javascript
const arr = [
  [0, 1],
  [2, 3],
  [4, 5]
];

const objectInArray = [
  {
    id: 1,
  },
  {
    id: 2,
  },
];
```

反例：
```javascript
const arr = [[0, 1], [2, 3], [4, 5]];

const objectInArray = [{
  id: 1,
}, {
  id: 2,
}];
```

# 10 函数
## 10.1 匿名函数统一使用箭头函数
正例：
```javascript
[1, 2, 3].map(x => {
  const y = x + 1;
  return x * y;
});
```

反例：
```javascript
[1, 2, 3].map(function (x) {
  const y = x + 1;
  return x * y;
});
```

## 10.2 如果函数体包含一个单独的语句，返回一个没有副作用的 expression ， 省略括号并使用隐式返回。否则，保留括号并使用 return 语句
为什么? 语法糖。 多个函数被链接在一起时，提高可读性。
推荐：
```javascript
[1, 2, 3].map(number => `A string containing the ${number}.`);
```

不推荐：
```javascript
[1, 2, 3].map(number => {
  return `A string containing the ${number}.`;
});
```

## 10.3 如果表达式跨越多个行，用括号将其括起来，以获得更好的可读性
正例：
```javascript
['get', 'post', 'put'].map(httpMethod => (
  Object.prototype.hasOwnProperty.call(
    httpMagicObjectWithAVeryLongName,
    httpMethod,
  )
));
```

反例：
```javascript
['get', 'post', 'put'].map(httpMethod => Object.prototype. hasOwnProperty.call(
    httpMagicObjectWithAVeryLongName,
    httpMethod,
  )
);
```

## 10.4 函数设计规范
+ 函数长度
  应该合理控制函数的长度。
  将过多的逻辑单元混在一个大函数中，易导致难以维护。一个清晰易懂的函数应该完成单一的逻辑单元。复杂的操作应进一步抽取，通过函数的调用来体现流程。
  特定算法等不可分割的逻辑允许例外。
+ 参数设计
  应该合理控制参数的数量。
  + 一个函数的参数控制在 6 个以内
    除去不定长参数以外，函数具备不同逻辑意义的参数建议控制在 6 个以内，过多参数会导致维护难度增大。
    某些情况下，如使用 AMD Loader 的 require 加载多个模块时，其 callback 可能会存在较多参数，因此对函数参数的个数不做强制限制。
  + 通过 options 参数传递非数据输入型参数


# 11 解构
## 11.1 在访问和使用对象的多个属性的时候使用对象的解构
为什么? 解构可以避免为这些属性创建临时引用。
正例：
```javascript
// good
function getFullName(user) {
  const {firstName, lastName} = user;
  return `${firstName} ${lastName}`;
}

// best
function getFullName({firstName, lastName}) {
  return `${firstName} ${lastName}`;
}
```

反例：
```javascript
function getFullName(user) {
  const firstName = user.firstName;
  const lastName = user.lastName;

  return `${firstName} ${lastName}`;
}
```

## 11.2 使用数组解构
正例：
```javascript
const arr = [1, 2, 3, 4];
const [first, second] = arr;
```

反例：
```javascript
const arr = [1, 2, 3, 4];
const first = arr[0];
const second = arr[1];
```

## 11.3 对于多个返回值使用对象解构，而不是数组解构
为什么? 你可以随时添加新的属性或者改变属性的顺序，而不用修改调用方。
正例：
```javascript
function processInput(input) {
  // 处理代码...
  return { left, right, top, bottom };
}

// 调用者只选择他们需要的数据。
const { left, top } = processInput(input);
```

反例：
```javascript
function processInput(input) {
  // 处理代码...
  return [left, right, top, bottom];
}

// 调用者需要考虑返回数据的顺序。
const [left, __, top] = processInput(input);
```

# 12 类和构造器
## 12.1 尽量使用 class， 避免直接操作 prototype
正例：
```javascript
class Queue {
  constructor(contents = []) {
    this.queue = [...contents];
  }
  pop() {
    const value = this.queue[0];
    this.queue.splice(0, 1);
    return value;
  }
}
```

反例：
```javascript
function Queue(contents = []) {
  this.queue = [...contents];
}
Queue.prototype.pop = function () {
  const value = this.queue[0];
  this.queue.splice(0, 1);
  return value;
};
```

## 12.2 使用 extends 来扩展继承
它是一个内置的方法，可以在不破坏 instanceof 的情况下继承原型功能
正例：
```javascript
class PeekQueue extends Queue {
  peek() {
    return this.queue[0];
  }
}
```

反例：
```javascript
const inherits = require('inherits');
function PeekQueue(contents) {
  Queue.apply(this, contents);
}
inherits(PeekQueue, Queue);
PeekQueue.prototype.peek = function () {
  return this.queue[0];
};
```

## 12.3 如果没有指定类，则类具有默认的构造器。 一个空的构造器或是一个代表父类的函数是没有必要的
正例：
```javascript
class Rey extends Jedi {
  constructor(...args) {
    super(...args);
    this.name = 'Rey';
  }
}
```

反例：
```javascript
class Jedi {
  constructor() {}
  getName() {
    return this.name;
  }
}

class Rey extends Jedi {
  constructor(...args) {
    super(...args);
  }
}
```

# 14 迭代器
## 13.1 不要使用迭代器。 你应该使用 JavaScript 的高阶函数代替 for-in 或者 for-of
为什么? 这是我们强制的规则。 拥有返回值得纯函数比这个更容易解释。
使用 map() / every() / filter() / find() / findIndex() / reduce() / some() / ... 遍历数组， 和使用 Object.keys() / Object.values() / Object.entries() 迭代你的对象生成数组。
正例：
```javascript
const numbers = [1, 2, 3, 4, 5];
// good
let sum = 0;
numbers.forEach(num => {
  sum += num;
});
sum === 15;

// best (use the functional force)
const sum = numbers.reduce((total, num) => total + num, 0);
sum === 15;

// good
const increasedByOne = [];
numbers.forEach(num => {
  increasedByOne.push(num + 1);
});

// best (keeping it functional)
const increasedByOne = numbers.map(num => num + 1);
```

反例：
```javascript
const numbers = [1, 2, 3, 4, 5];

let sum = 0;
for (let num of numbers) {
  sum += num;
}
sum === 15;

const increasedByOne = [];
for (let i = 0; i < numbers.length; i++) {
  increasedByOne.push(numbers[i] + 1);
}
```

# 14 动态特性
## 14.1 执行动态代码
+ 避免使用直接 eval 函数
  直接 eval，指的是以函数方式调用 eval 的调用方法。直接 eval 调用执行代码的作用域为本地作用域，应当避免。
+ 使用 new Function 执行动态代码
  通过 new Function 生成的函数作用域是全局使用域，不会影响当当前的本地作用域。如果有动态代码执行的需求，建议使用 new Function。

## 14.2 减少 delete 的使用
如果没有特别的需求，减少或避免使用 delete。delete 的使用会破坏部分 JavaScript 引擎的性能优化。






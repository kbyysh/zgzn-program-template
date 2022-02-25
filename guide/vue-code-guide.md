# 1 组件规范
## 1.1 组件名为多个单词
组件名应该始终是多个单词组成（大于等于 2），且命名规范为KebabCase格式。
这样做可以避免跟现有的以及未来的 HTML 元素相冲突，因为所有的 HTML 元素名称都是单个单词的。
正例：
```javascript
export default {
  name: 'TodoItem'
  // ...
};
```

反例：
```javascript
export default {
  name: 'Todo',
  // ...
}
export default {
  name: 'todo-item',
  // ...
}
```

## 1.2 组件文件名
### 1.2.1 统一使用 Pascal 格式命名组件文件名称
正例：
```text
components/
|- MyComponent.vue
```

反例：
```text
components/
|- mycomponent.vue
components/
|- myComponent.vue
components/
|- my-component.vue
```

### 1.2.2 组件名称应对该组件具有描述意义
正例：
```text
components/
|- SearchInput.vue
```

反例：
```text
components/
|- SInput.vue
```

### 1.2.3 紧密耦合的组件名
和父组件紧密耦合的子组件应该以父组件名作为前缀命名。
如果一个组件只在某个父组件的场景下有意义，这层关系应该体现在其名字上。因为编辑器通常会按字母顺序组织文件，所以这样做可以把相关联的文件排在一起。
正例：
```text
components/
|- TodoList.vue
|- TodoListItem.vue
|- TodoListItemButton.vue

components/
|- SearchSidebar.vue
|- SearchSidebarNavigation.vue
```

反例：
```text
components/
|- TodoList.vue
|- TodoItem.vue
|- TodoButton.vue

components/
|- SearchSidebar.vue
|- NavigationForSearchSidebar.vue
```

### 1.2.4 组件名中的单词顺序
组件名应该以高级别的 (通常是一般化描述的) 单词开头，以描述性的修饰词结尾。
正例：
```text
components/
|- SearchButtonClear.vue
|- SearchButtonRun.vue
|- SearchInputQuery.vue
|- SearchInputExcludeGlob.vue
|- SettingsCheckboxTerms.vue
|- SettingsCheckboxLaunchOnStartup.vue
```

反例：
```text
components/
|- ClearSearchButton.vue
|- ExcludeFromSearchInput.vue
|- LaunchOnStartupCheckbox.vue
|- RunSearchButton.vue
|- SearchInput.vue
|- TermsCheckbox.vue
```

### 1.2.5 模板中的组件名大小写
由于 HTML 是大小写不敏感的，在 DOM 模板中必须仍使用 kebab-case
正例：
```html
<my-component></my-component>
```

反例：
```html
<MyComponent></MyComponent>
```

### 1.2.6 完整单词的组件名
组件名应该倾向于完整单词而不是缩写。

编辑器中的自动补全已经让书写长命名的代价非常之低了，而其带来的明确性却是非常宝贵的。不常用的缩写尤其应该避免。
正例：
```text
components/
|- StudentDashboardSettings.vue
|- UserProfileOptions.vue
```

反例：
```text
components/
|- SdSettings.vue
|- UProfOpts.vue
```

## 1.3 组件数据
组件的 data 必须是一个函数
当在组件中使用 data property 的时候，它的值必须是返回一个对象的函数。
正例：
```javascript
export default {
  data () {
    return {
      foo: 'bar'
    }
  }
}
```

反例：
```javascript
Vue.component('some-comp', {
  data: {
    foo: 'bar'
  }
})

export default {
  data: {
    foo: 'bar'
  }
}
```

# 2 Prop
## 2.1 Prop 定义
Prop 定义应该尽量详细。
在你提交的代码中，prop 的定义应该尽量详细，至少需要指定其类型。
```javascript
props: {
  status: String,
  default: 'error'
}

props: {
  status: {
    type: String,
    required: true,
    validator: function (value) {
      return [
        'syncing',
        'synced',
        'version-conflict',
        'error'
      ].indexOf(value) !== -1
    }
  }
}
```

反例：
```javascript
// 这样做只有开发原型系统时可以接受
props: ['status']
```

## 2.2 Prop 名大小写
在声明 prop 的时候，其命名应该始终使用 camel 规范
```javascript
props: {
  greetingText: String
}
```

反例：
```javascript
props: {
  'greeting-text': String
}
```

# 3 指令
## 3.1 指令缩写
```html
<input
  :value="newTodoText"
  :placeholder="newTodoInstructions"
>

<input
  @input="onInput"
  @focus="onFocus"
>
```

反例：
```html
<input
  v-bind:value="newTodoText"
  :placeholder="newTodoInstructions"
>

<input
  v-on:input="onInput"
  @focus="onFocus"
>
```

## 3.2 为 v-for 设置键值
在组件上总是必须用 key 配合 v-for，以便维护内部组件及其子树的状态。
```html
<ul>
  <li
    v-for="todo in todos"
    :key="todo.id"
  >
    {{ todo.text }}
  </li>
</ul>
```

反例：
```html
<ul>
  <li v-for="todo in todos">
    {{ todo.text }}
  </li>
</ul>
```

## 3.3 避免 v-if 和 v-for 用在一起
```html
<ul>
  <li
    v-for="user in activeUsers"
    :key="user.id"
  >
    {{ user.name }}
  </li>
</ul>

<ul v-if="shouldShowUsers">
  <li
    v-for="user in users"
    :key="user.id"
  >
    {{ user.name }}
  </li>
</ul>
```

反例：
```html
<ul>
  <li
    v-for="user in users"
    v-if="user.isActive"
    :key="user.id"
  >
    {{ user.name }}
  </li>
</ul>

<ul>
  <li
    v-for="user in users"
    v-if="shouldShowUsers"
    :key="user.id"
  >
    {{ user.name }}
  </li>
</ul>
```

## 3.4 v-show 与 v-if 选择
如果运行时，需要非常频繁地切换，使用 v-show ；如果在运行时，条件很少改变，使用 v-if。

# 4 组件中的样式
应该为只有在该组件中使用的样式添加作用域限制，公用的css样式应提取到公共css文件里。
正例：
```html
<ul class="info_list"></ul>

<style scope>
  .info_list{}
</style>
```

反例：
```html
<ul class="info_list"></ul>

<style>
  .info_list{}
</style>
```

# 5 attribute
## 5.1 多个 attribute 的元素应该分多行撰写，每个 attribute 一行
用多行分隔对象的多个 property 是很常见的最佳实践，因为这样更易读。模板和 JSX 值得我们做相同的考虑。
正例：
```html
<img
  src="https://vuejs.org/images/logo.png"
  alt="Vue Logo"
>

<my-component
  foo="a"
  bar="b"
  baz="c"
/>
```

反例：
```html
<img src="https://vuejs.org/images/logo.png" alt="Vue Logo">

<my-component foo="a" bar="b" baz="c"/>
```

## 5.2 带引号的 attribute 值
正例：
```html
<input type="text">

<app-sidebar :style="{width: sidebarWidth + 'px'}">
```

反例：
```html
<input type=text>

<app-sidebar :style={width: sidebarWidth + 'px'}>
```

## 5.3 元素 attribute 的顺序
元素 (包括组件) 的 attribute 应该有统一的顺序。

这是我们为组件选项推荐的默认顺序。它们被划分为几大类，所以你也能知道新添加的自定义 attribute 和指令应该放到哪里。

1. 定义 (提供组件的选项)
  + ```is```

2. 列表渲染 (创建多个变化的相同元素)
  + ```v-for```

3. 条件渲染 (元素是否渲染/显示)
  + ```v-if```
  + ```v-else-if```
  + ```v-else```
  + ```v-show```
  + ```v-cloak```

4. 数据绑定
  + ```v-model```
  + ```v-bind```

5. 事件
  + ```v-on```

6. 样式类
  + ```class```

7. 唯一的 attribute
  + ```id```
  + ```ref```
  + ```key```

8. 其他
  + ```v-slot```
  + ```v-html```
  + ```v-pre```
  + ```v-once```
  ......

# 6 标签顺序保持一致
单文件组件应该总是让标签顺序保持为
正例：
```html
<template></template>
<script></script>
<style></style>
```

反例：
```html
<template></template>
<style></style>
<script></script>
```

# 7 script 标签内部结构顺序
components > props > data > computed > watch > filter > methods > 钩子函数（钩子函数按其执行顺序） 

# 8 模板中简单的表达式
组件模板应该只包含简单的表达式，复杂的表达式则应该重构为计算属性或方法。
正例：
```html
<div>{{normalizedFullName}}</div>
<script>
  new Vue({
    data () {
      return {}
    },
    computed: {
      normalizedFullName () {
        return this.fullName.split(' ')
          .map(word => word[0].toUpperCase() + word.slice(1))
          .join(' ')
      }
    }
  })
</script>
```

反例：
```html
<div>
  {{
    fullName.split(' ')
    .map(word => word[0].toUpperCase() + word.slice(1))
    .join(' ')
  }}
</div>
```

# 9 Vue Router 规范
## 9.1 页面跳转数据传递使用路由参数
页面跳转，例如 A 页面跳转到 B 页面，需要将 A 页面的数据传递到 B 页面，推荐使用 路由参数进行传参，而不是将需要传递的数据保存 vuex，然后在 B 页面取出 vuex 的数据，因为如果在 B 页面刷新会导致 vuex 数据丢失，导致 B 页面无法正常显示数据。
示例：
```javascript
let id = '123';
this.$router.push({
  name: 'userCenter',
  query: {
    id: id
  }
});
```

## 9.2 使用路由懒加载（延迟加载）机制
示例：
```javascript
{
  path: '/uploadAttachment',
  name: 'uploadAttachment',
  meta: {
    title: '上传附件'
  },
  component: () => import('@/view/components/uploadAttachment/index.vue')
}
```

# 10 VueX
## 10.1 store文件目录
+ store
  + modules
    + user
      + getter.js
      + mutation.js
      + action.js
      + state.js
      + index.js
    + setting
      + getter.js
      + mutation.js
      + action.js
      + state.js
      + index.js
    + common
      + getter.js
      + mutation.js
      + action.js
      + state.js
      + index.js
  + index.js

+ 根目录下index.js为 store 实例：
```javascript
import Vue from 'vue';
import Vuex from 'vuex';

Vue.use(Vuex);
import user from './modules/user/index.js'
import cart from './modules/cart/index.js'
import test from './modules/test/index.js'
export default new Vuex.Store({
  modules:{
    user,
    setting,
    common
  }
})
```
+ vuex状态管理使用应按照功能模块拆分成对应的module

+ module里应该设置命名空间（namespaced）为true
  ```javascript
  export default {
    namespaced: true,
    state: {},
    mutations: {},
    getters: {},
    actions: {}
  }
  ```
+ 建议在每个module下，将state、getter、mutation、action拆分开来，不要放在同一个js文件中，通过index.js汇总导出模块

## 10.2 state
+ 统一使用getters去获取state，不建议使用this.$store.state去获取
+ 修改状态统一使用mutations

## 10.3 去使用getters
建议使用computed 配合 mapGetters 去使用getters
示例：
```javascript
computed: {
  ...mapGetters([
    'getUserInfo'
  ])
}
```

## 10.4 mutations
+ 组件内使用mutation统一用mapMutations
  ```javascript
  methods: {
    ...mapMutations([
      'changeUserInfo'
    ])
  }
  ```

## 10.5 actions
+ 组件内使用action统一用mapActions
  ```javascript
  ...mapActions({
    AsyncSetUsername: 'user/AsyncSetUsername',
    AsyncSetUsername1: 'cart/AsyncSetUsername'
  })
  ```

# 11 项目工程结构
源码目录（src）：
```text
src
| -- api 所有api接口
| -- assets 静态资源 images, icons, styles等
| -- components 组件
| -- config 配置信息
| -- directives 自定义指令
| -- filters 过滤器
| -- libs 插件
| -- router 路由
| -- store 状态（vuex）
| -- utils 工具类
| -- views 视图目录
```


    
---
title: 全局对象
type: guide
order: 4
---
## logger
### 说明
* 这个对象是插件pea-logger暴露出来的方法，pea-logger插件是对 [log4js-node](https://github.com/log4js-node/log4js-node)的二次封装，log4js-node里面的方法皆可以在程序中使用。
* 开箱即用,项目初始化完成之后直接可以使用
* 项目初始化完成之后会在系统的当前用户目录下**(cd ~)**生成一个logs 文件夹，所有日志存储在这个位置
* 日志格式 {project_name}_yyyy-mm-dd.log {project_name}_err_yyyy-mm-dd.log

### 目的
1. 能够以插件化的形式注入到系统中，随时可开关
2. 自动按日期分割日志文件，每天生成两个文件,一个正确,一个错误.


### 用法
直接可以使用,使用方法和[log4js-node](https://github.com/log4js-node/log4js-node)一致
```
logger.trace('Entering cheese testing');
logger.debug('Got cheese.');
logger.info('Cheese is Gouda.');
logger.warn('Cheese is quite smelly.');
logger.error('Cheese is too ripe!');
logger.fatal('Cheese was breeding ground for listeria.');

```

level和名称在配置文件里面，可修改 **config/{env}.js**
```
  logger: {
        name: 'bt',
        level: 'info'
    }
```
是否启用在插件里面修改 **app/plugin.js**

```
logger: {
        enable:true,
        package:'quick-logger'
    }
```


## APP

### 目的
* 存储插件的对象,比如我们使用了插件 [pea-redis](https://github.com/TimLiu1/pea-redis) 插件
 在插件文件夹下面配置,则可以使用APP.redis这个对象操作方法
```
//config/plugin.js
   redis:{
        enable:true,
        package:'quick-redis'
    }
 //config/development.js
      redis: {
      host: '127.0.0.1',
      port: '6379',
      password: null,
      db: 0
          }

```
* 存储插件的对象,比如



### 原始 HTML(Raw HTML)

双花括号语法，会将数据中的 HTML 转为纯文本后再进行插值。为了输出真正的 HTML，你需要使用 `v-html` 指令：

``` html
<p>使用双花括号语法：{{ rawHtml }}</p>
<p>使用 v-html 指令：<span v-html="rawHtml"></span></p>
```

{% raw %}
<div id="example1" class="demo">
  <p>使用双花括号语法：{{ rawHtml }}</p>
  <p>使用 v-html 指令：<span v-html="rawHtml"></span></p>
</div>
<script>
new Vue({
  el: '#example1',
  data: function () {
    return {
      rawHtml: '<span style="color: red">This should be red.</span>'
    }
  }
})
</script>
{% endraw %}

`span` 中的内容，将会被替换为 `rawHtml` 属性的值，并且作为原始 HTML 插入 - 会忽略解析属性值中的数据绑定。请注意，无法使用 `v-html` 来组合局部模板，这是因为 Vue 不是基于字符串(string-based)的模板引擎。反之，对于用户界面(UI)，组件更适合作为可重用和可组合的基本单位。

<p class="tip">在网站中动态渲染任意的 HTML 是非常危险的，因为这很容易导致网站受到 [XSS 攻击](https://en.wikipedia.org/wiki/Cross-site_scripting)。请只对可信内容使用 HTML 插值，**绝对不要**对用户提供的内容使用 HTML 插值。</p>

### 属性(Attributes)

不能在 Vue 模板中的 HTML 属性上使用双花括号语法(mustache)。而是应该使用 [v-bind 指令](../api/#v-bind)：

``` html
<div v-bind:id="dynamicId"></div>
```

在属性是布尔类型的一些情况中，`v-bind` 的作用有点不同，只要值存在就会隐含为 `true`。在这个例子中：

``` html
<button v-bind:disabled="isButtonDisabled">Button</button>
```

如果 `isButtonDisabled` 的值为 `null`, `undefined` 或 `false`，`disabled` 属性甚至不会被包含在渲染后的 `<button>` 元素中。

### 使用 JavaScript 表达式

到目前为止，我们只实现了将模板绑定到基本的属性键上。然而，Vue.js 实际上能够支持通过完整的 JavaScript 表达式，将模板与任意的数据绑定在一起：

``` html
{{ number + 1 }}

{{ ok ? 'YES' : 'NO' }}

{{ message.split('').reverse().join('') }}

<div v-bind:id="'list-' + id"></div>
```

这些表达式，将在所属的 Vue 实例的数据作用域下，作为 JavaScript 取值。有个限制是，每个绑定都只能包含**单个表达式**，所以以下示例都**无法运行**：

``` html
<!-- 这是语句，不是表达式 -->
{{ var a = 1 }}

<!-- 流控制也无法运行，请使用三元表达式 -->
{{ if (ok) { return message } }}
```

<p class="tip">模板表达式放置在沙盒中，只能访问全局变量的一个白名单列表，如 `Math` 和 `Date`。在模板表达式中，你不应该试图访问用户定义的全局变量。</p>

## 指令(Directives)

指令(directive)是带有 `v-` 前缀的特殊属性。指令属性的值期望接收的是**单个 JavaScript 表达式**（`v-for` 是例外情况，稍后我们再讨论）。指令的职责是，当表达式的值改变时，将其产生的影响效果，响应式地作用于 DOM。回顾我们在介绍中看到的例子：

``` html
<p v-if="seen">Now you see me</p>
```

这里，`v-if` 指令将根据表达式 `seen` 的值的真假来移除/插入 `<p>` 元素。

### 参数(Arguments)

一些指令能够接收一个“参数”，在指令名称之后以 `:` 表示。例如，`v-bind` 指令可以用于响应式地更新 HTML 属性：

``` html
<a v-bind:href="url"> ... </a>
```

这里 `href` 是参数，告知 `v-bind` 指令将元素的 `href` 属性与表达式 `url` 的值绑定在一起。

另一个示例是 `v-on` 指令，用于监听 DOM 事件：

``` html
<a v-on:click="doSomething"> ... </a>
```

这里，参数是要监听事件的名称。稍后我们会详细地讨论事件处理。

### 修饰符(Modifiers)

修饰符(modifier)是以 `.` 表示的特殊后缀，表明应当以某种特殊方式绑定指令。例如，`.prevent` 修饰符告诉 `v-on` 指令，在触发事件后调用 `event.preventDefault()`：

``` html
<form v-on:submit.prevent="onSubmit"> ... </form>
```

稍后我们在探索这些特性时，你就会看到其他修饰符的相关示例，例如 [`v-on`](events.html#Event-Modifiers) 和 [`v-model`](forms.html#Modifiers)。

## 简写(Shorthands)

在模板中，`v-` 前缀作为非常符合直觉的提示，能够十分有效地标识出 Vue 特定(Vue-specific)属性。当你在使用 Vue.js 为现有标签添加动态行为(dynamic behavior)时，`v-` 前缀很有帮助，然而，对于一些频繁用到的指令来说，就会感到使用繁琐。同时，在构建由 Vue.js 管理所有模板的[单页面应用程序(SPA - single page application)](https://en.wikipedia.org/wiki/Single-page_application)时，`v-` 前缀也变得没那么重要了。因此，Vue.js 为 `v-bind` 和 `v-on` 这两个最常用的指令，提供了特定简写：

### `v-bind` 简写

``` html
<!-- 完整语法 -->
<a v-bind:href="url"> ... </a>

<!-- 简写 -->
<a :href="url"> ... </a>
```

### `v-on` 简写

``` html
<!-- 完整语法 -->
<a v-on:click="doSomething"> ... </a>

<!-- 简写 -->
<a @click="doSomething"> ... </a>
```

它们看起来可能与通常我们见到的 HTML 属性略有不同，但是，其实 `:` 和 `@` 都是符合属性名称(attribute name)相关标准的有效字符，并且所有支持 Vue.js 的浏览器都能够正确解析它们。此外，它们并不会出现在最终渲染的 HTML 标记中。简写语法是完全可选的书写方式，然而，随着你深入地了解它们的用法之后，你会领会到这种简单直接的简写方式，是非常赏心悦目的用法。

***

> 原文：https://vuejs.org/v2/guide/syntax.html

***
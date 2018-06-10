---
title: 基础工作
type: guide
order: 8
---

## 概述
peajs 的目的是让开发者能够忽略基础工作，专注于业务的开发，并没有对koa框架做大的改动，或则语法结构的改动，而是集成许多基础工作和插件，省去开发者的基础烦恼

## eslint
### 介绍
在开始做nodejs项目的时候，我们team的所有项目都是没有eslint的，那时候我犯了很多低级错误，比如变量未定义，变量定义未使用，变量定义但是使用的时候单词拼错了，有一部分错误甚至是到线上才发现的，这样不仅仅降低我们的开发效率，而且很容易带来生产事故。

### 引进可能遇到的问题
我们team在引进eslint的时候遇到了一下几个问题。
* 历史遗留问题，eslint引进的时候一下10000甚至更多错误冒出来了，由于工作量或则项目进度原因放弃了。
* 市场上各种各样的eslint规则不知从哪入手。
* 甚至eslint规则和开发工具格格不入，只要格式化就报错。

所以peajs不仅仅按照标准nodejs语法集成了eslint，同时还提供教程教大家如何避免以上问题

### 用法
* 历史遗留老项目
如果想非常迅速的解决历史遗留问题，VSCode对这种场景是非常友好的
* 支持插件检测和提醒错误，在VSCode插件里面搜索和安装ESLint。

* 这是非常高效的一个特性，支持按配置保存的时候自动修复大部分ESlint错误问题。
在Code->Preferences->Settings->workspace setting 里面添加如下设置
```
 "eslint.autoFixOnSave": true
```
这样就可以在保存文件的时候自动修复eslint常规错误



## apidoc
peajs集成了[apidocjs](http://apidocjs.com/), 具体详情可参考[apidocjs](http://apidocjs.com/),这是一个很好的管理api工具，只需要按照固定格式配置，就可以生成可读性极佳的html文档。
下面讲讲peajs在peajs里面的用法

### 快速开始
在项目更目录运行
```
npm run doc

```

然后就可以在根目录下生成一个目录 **apidoc**,打开 **apidoc/index.html**,就可以看到如下图的网页
![apidoc](/images/apidoc.png)

### 用法详解
* 常规的请求信息，常规信息在根目录的apidoc.json里面配置
* **npm run doc** 会把所有的 **/app/routes/apiguide**下面的js文件全部解析为html文件,所以所有的api都维护到**\/app/routes/apiguide**下面.
* 约定一个路由文件有一个对应的api的js文档



---
title: 插件
type: guide
order: 7
---

## 概述
插件在peajs里面主要提供两方面的功能
* 让功能可插拔，用户只需要修改一个flag就可以实现插件的使用与否
* 插件本身暴露出比较友好的方法，让用户有更多选择

> 插件是基于现在非常流行的包进行二次封装

## 基本用法
下面是初始化默认开启的[pea-logger](https://github.com/TimLiu1/pea-logger)插件。

``` javascript
// config/development.js
 logger: {
        name:  'bt',// default: yeoman生成时的项目名称
        level: 'info'
    }
//config/plugin.js
  logger: {
        enable:true, //是否启用标识
        package:'quick-logger' //包名称
  }

```
## 插件集合

### pea-logger
这个插件默认在系统中初始化完成的，完成之后生成一个全局对象logger,可以直接在系统中使用,
如果想使用自己的包，可以在 **config/plugin**禁止。logger具体使用参见[logger](global-object.html#logger)

### pea-redis
#### 简介
pea-redis插件是对 [ioredis](https://github.com/luin/ioredis)的二次封装，支持ioredis的所有方法
同时新增以下两个特性。
* 对于常用方法支持async await方法操作redis数据库
* 支持对象的存取

可以单独使用，也可以作为peajs的插件,具体可见[pea-redis](https://github.com/TimLiu1/pea-redis)

#### 作为peajs插件使用

因为一些项目并不需要redis作为插件，所以项目初始化过程并没有集成，需要单独作为插件使用
``` javascript

npm i pea-redis
// config/development.js
   redis: {
        host: '127.0.0.1',
        port: '6379',
        password: null,
        db: 0
    },
//config/plugin.js
  redis: {
        enable:true, //是否启用标识
        package:'quick-logger' //包名称
  }
```
做完以上配置启动的时候会初始化好所有工作，在APP绑定一个APP.redis对象
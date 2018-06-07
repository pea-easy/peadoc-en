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

### pea-redis

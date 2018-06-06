---
title: 配置
type: guide
order: 5
---

## 简介
目前常规配置有两种
* 通过平台注入，好处是更安全，缺点是本地开发麻烦
* 在代码里面配置，好处是本地开发和线上部署都比较方便，缺点存在安全问题
> 建议: 把生产的配置文件ignore，防止开发人员误连，或则恶意操作

## 配置文件加载
```
config/config.js
config/development.js

```
系统会首先加载config.js里面的配置文件，然后根据环境变量NODE_ENV加载配置文件,采取同名一级键覆盖的原则,如果没有配置文件，默认加载development.js文件。


## 建立生产环境
只需新建**config/{env}.js**,然后启动的时候指定**NODE_ENV={env}**即可,例
```
config/production.js
```

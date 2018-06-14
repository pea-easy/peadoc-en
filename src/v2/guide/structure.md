---
title: 目录结构
type: guide
order: 3
vue_version: 2.5.13
gz_size: "30.67"
---

### 目录结构

初始化项目目录结构
```html
pea-project
├── app
│   ├── controller
│   |   └── user-ctrl.js
│   ├── service 
│   |   └── user-server.js
│   |   └── validate
|   |       └── validate-user.js 
│   ├── dao 
│   |   └── user-dao.js
│   ├── routes
│   |   └── index.js
│   │   └── user.js
│   │   └── apiguide
|   |       └── user.js 
├── config
|   ├── plugin.js
|   ├── development.js
└── lib
|   ├── middleware
|   |   └── responseJSON.js
└── test
    | 
   .core
    |
    public
    | 
    .eslintrc.json
    |
    .gitignore
    |
    apidoc.js
    |
    eslintignore
    |
    index.js
    |
    package.json
    |
    README.md
    |
    server.js
```


如上，由框架约定的目录：

* **app/router.js** 用于配置 URL 路由规则
* **app/controller/\*\*** 用于组装service层提供的服务
* **app/service/**** 用于编写业务逻辑层，可选，建议使用。
* **app/dao/**** 用于编写和业务交互层，可选，建议使用。
* **config/{env}.js** 用于编写配置文件，具体参见配置。
* **config/plugin.js** 用于配置需要加载的插件，具体参见插件。
* **lib/middleware/**** 用于放置中间件
* **lib/spec.js** 初始化操作
* **public** 存储静态文件
* **test** 存储测试文档
* **.core/\*\*/*** peajs核心程序，可适当根据业务需求扩展


> app/model/** 用于放置领域模型，可选，yo生成项目的时候如何选择数据库可以做初始化工作。


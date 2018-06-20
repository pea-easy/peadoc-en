---
title: yo pea工具类使用
type: guide
order: 701
---
 
## 概述

yo pea不仅仅能够[初始化项目](instance.html),同时也提供工具类自动生成组件

### 生成整个module
*** yo pea:module {module name} ***
比如想生成一个数据module,只需运行
```
yo pea:module data

```
运行以上命令之后就会生成以下文件，并且初始化所有引用关系
**app/routes/data.js**
**app/routes/apiguide/data.js**
**app/controllers/data-ctrl.js**
**app/service/validate/validate-data.js**
**app/service/service-data.js**

完成之后可以用以下命令测试是否成功
```
curl localhost:8899/user
```
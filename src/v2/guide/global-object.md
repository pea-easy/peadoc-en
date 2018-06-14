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
如果希望自己定义日志路径,可以增加outputPath字段
  ```
   logger: {
        name: 'bt',
        level: 'info',
        outputPath:'./logs'
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
* 储存配置文件对象 APP.config 可以获取配置文件对象

### 使用，项目初始化完成之后可以直接使用

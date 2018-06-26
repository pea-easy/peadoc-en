---
title: Plugin
type: guide
order: 7
---

## Overview
Plugin in peajs primarily provides 2 feature: 
* To enable functions swappable, user could merely change a flag to implement the plugin.
* Plugin itself is a use-friendly way that facilitates development process.

> Plugin is re-encapsulated based on the prevailing packages listing below.

## Basics
The [pea-logger](https://github.com/TimLiu1/pea-logger) plugin below is toggled on by default in initialization。

``` javascript
// config/development.js
 logger: {
        name:  'bt',// default: The project name in yeoman
        level: 'info'
    }
//config/plugin.js
  logger: {
        enable:true, // If to enable the marker
        package:'quick-logger' // The package name
  }

```
## Plugin Library

### pea-logger
As illustrated above, after the pea-logger is loaded in initialization, a global object logger would be created and it could be used in the system.

If you are willing to use your package, please toggle it down in **config/plugin**. Refer to [logger](global-object.html#logger) for detailed usage.

### pea-redis
#### Introduction
pea-redis is a re-encapsulation based on the [ioredis](https://github.com/luin/ioredis), which inherits all methods in the ioredis and supports 2 more features:
* Support async await for common method to operate redis database.
* Support to read and write object. 

It could be used independently, and as well used as a plugin of peajs. Refer to [pea-redis](https://github.com/TimLiu1/pea-redis) for more details.

#### Use pea-redis as a plugin of peajs

Concerning some project doesn't integrate redis in the initialization, pea-redis could be independently loaded as a plugin which doesn't require redis.
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
        enable:true, // If to enable the marker
        package:'quick-logger' //
  }
```
After completing the initialization according to the configuration above, an object of APP.redis will be bound to the app.
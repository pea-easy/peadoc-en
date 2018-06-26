---
title: Business Level
type: guide
order: 6
---

A conventional and rational development standard in the team could dramatically save communication and migration cost. Here we are going to introduce the level in peajs.

Usually, in the real development we need to frequently use the file under the following level: route service, controlling level, service authentication level and database operation level, which are combined in Pea.js as business level, and stores under app folder. 

Notice that Service Authentication Level is particularly added in the peajs, which we found is pretty useful to avoid forgetting to transfer parameter.

## Route Service
按模块分比如用户模块，订单模块，图表模块 In Pea.js, route service is divided by module, eg. User Module, Order Module, Graph Module, etc.

## Controlling Level
服务层提供功能完整性的模块，控制层对功能完整性模块进行组装。

## Service Level
服务层主要为控制层服务，完成一个个功能性模块，然后控制层在对服务层进行调用。

### Service Authentication Level
每个服务function需要一些简单的校验，比如查询用户需要检测用户id是否存在，更新订单需要校验订单id是否存在，主要是为了避免一些常规的错误。


## Database Operation Level
这一层主要是为了和数据库进行交互


> 因为peajs只是koa的扩展,所有支持koa所有通用的语法.
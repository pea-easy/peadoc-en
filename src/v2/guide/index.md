---
title: Introduction
type: guide
order: 1
---

## What is Pea.js?

Peajs是基于koa二次封装扩展的一个框架，聚焦于让开发者关注于业务开发，从繁杂的基础工作中解脱出来。
Peajs is a extended framework based on the re-encapsulation of koa. It enables developer to concentrate on development and get rid of other tedious basic work.

## Why to create Pea.js?
With the development going on, we found a fact that enormous basic work is duplicated across various projects. For instance, we have to integrate log module, eslint, api document module, etc. by copy-paste, which is lavishing the time of not only migration but also extra debug. Yet if we don't integrate them prior to kicking off development (due to the tight schedule of project), more and more effort of refactoring and communication would have to be spent. 在沉淀过很多项目之后，我们会发现在很多项目中我们做了相同的基础工作，比如集成日志模块，集成eslint，集成api文档模块等。并且每次都需要拷贝集成，不仅浪费了很多迁移的时间，同时也需要很多额外调试的时间，同时由于项目的进度原因,这些模块并没有集成进来，给后期项目的开发和沟通带来很多不便利性。

## Key Values项目特点
### 基础工作的集成 Integration of basic work
Peajs incorporates eslint, api document, configuration file, logger, etc.
集成了eslint, api文档,配置文件,logger等基础服务
### 插件化配置 Plug-in mechanism
外部服务可以通过插件注入到系统中,比如pea-redis,pea-logger
### 约定的开发标准 Consensual development standard
*Convention is better than configuration.* This Egg's design principle that we strongly agree, follows the Loader to do the development, it helps to reduce the cost of learning. The cost of communication is very high for a team without convention. It is easy to get fault without convention. However convention is not equal to difficult extension.
约定优于配置, 我非常赞同egg的司机思想，按照一套统一的约定进行应用开发，团队内部采用这种方式可以减少开发人员的学习成本，没有约定的团队，沟通成本是非常高的，比如有人会按目录分栈而其他人按目录分功能，开发者认知不一致很容易犯错。

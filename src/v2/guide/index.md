---
title: Introduction
type: guide
order: 1
---

## What is Pea.js?

Peajs is an extended framework based on the re-encapsulation of koa. It enables developer to concentrate on development and get rid of other tedious basic work.

## Why you should try Pea.js?
With the development going on, we found a fact that enormous basic work is duplicated across various projects. For instance, we have to integrate log module, eslint, api document module, etc. by copy-paste, which is lavishing the time of not only migration but also extra debug. Yet if we don't integrate them prior to kicking off development (due to the tight schedule of project), more and more effort of refactoring and communication would have to be spent.

## Key Values
### Integration of basic work
Peajs incorporates eslint, api document, configuration file, logger, etc.

### Plug-in mechanism
External service could be leveraged as a plugin into system, eg. pea-redis, pea-logger.
### Convention development standard
*Convention is better than configuration.* This Egg's design principle that we strongly agree, follows the Loader to do the development, it helps to reduce the cost of learning. The cost of communication is very high for a team without convention. It is easy to get fault without convention. However convention is not equal to difficult extension.

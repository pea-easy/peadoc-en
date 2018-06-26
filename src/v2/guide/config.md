---
title: Configuration
type: guide
order: 5
---

## Introduction
Here are some common control tactics:
* Use platform to manage configurations, which is safer but effort-consuming for local development.
* Use code to manage configurations, which is easy for local development and deployment, but may cause security problem.
> Suggestion: ignore the configuration file of production environment to prevent developers from fault connection or malicious operation.

## Load configuration file
```
config/config.js
config/development.js

```
System will firstly load the config file in config.js and then load the config file based on env variable NODE__ENV. If no env is specified, by default load development.js


## Setup production environment

Only type **config/{env}.js** and specify **NODE_ENV={env}** when launching the project.
```
config/production.js
```

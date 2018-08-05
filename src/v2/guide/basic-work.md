---
title: Basic Works Automation
type: guide
order: 8
---

## Overview
The principle of peajs is to forget those duplicated basic works and focus on functional development. We don't revamp framework or language structure of koa, but combined many plugins and basic work components, so that developers don't need to worry about them anymore. 

## eslint
### Introduction
Once we kicked off a nodejs project, there was no eslint embedded. At that time, such mistakes were not even found until they were pushed on production environment, like undefined variables, defined variable not in use, typo on defining variables, etc. Therefore, we had to pay double work on fixing it and more importantly it would cause immeasurable lost for these rookie mistakes.

### What if I just import eslint since then?
When eslint was imported, our team confronted several problems below:
* When you suddenly saw there were more than 10,000 errors, that was definitely a huge effort and we gave it right away due to the project schedule.
* There are so many rules of eslint and we have few ideas which one suits our situation.
* Eslint conflicts with some development tool. It popped up error even as long as you do format.

Luckily, peajs not only integrates eslint with the formal syntax of nodejs, but also provides instruction for users.

### Usage
Use peajs in the middle of the development.
If you want to resolve those historical issue in a flash, VSCode is such a perfect tool to do that. 

## apidoc
Peajs has embedded apidoc, please refer to the [apidocjs](http://apidocjs.com/) for details. It's an awesome api management tool. You can generate a polished html-based document following the syntax in config file.
In the next part, we will briefly introduce how to leverage apidoc in peajs

### Quick Start
Run in the root folder
```
npm run doc

```

Next, the **apidoc** folder will be created in the root folder. Open **apidoc/index.html**, you will see the web page as below
![apidoc](/images/apidoc.png)

### Explanation
* Common request information could be configured in the apidoc.json in root folder.
* **npm run doc** will parse all the js file in **/app/routes/apiguide** into html file, so all api should be maintained in **\/app/routes/apiguide**.
* A convention is in place that a route file responds to one js doc of API.



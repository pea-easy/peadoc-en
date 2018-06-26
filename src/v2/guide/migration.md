---
title: "Utility Class: yo pea"
type: guide
order: 701
---
 
## Overview

Not only can yo pea [initiate project](instance.html), but also it provides components to auto generate utility class.

### Generate a collective module
*** yo pea:module {module name} ***
For instance, if you want to create a data module, only need to run:
```
yo pea:module data

```
By running this code, the files below will be created, and initiate the reference relationship across each other.
**app/routes/data.js**
**app/routes/apiguide/data.js**
**app/controllers/data-ctrl.js**
**app/service/validate/validate-data.js**
**app/service/service-data.js**

After that, execute the code below to verify if the module has been generated successfully
```
curl localhost:8899/user
```
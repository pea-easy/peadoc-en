---
title: Directory Structure
type: guide
order: 3
vue_version: 2.5.13
gz_size: "30.67"
---

### Directory Structure

Initialize the project directory structure
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


As above, directories by conventions of framework:

* **app/router.js** used to configure URL routing rules.
* **app/controller/\*\*** used to package the service provided by service level.
* **app/service/**** used for business logic layer, optional, recommend to use.
* **app/dao/**** used for middleware, optional, recommend to use.
* **config/{env}.js** used to write configuration files, see Configuration for details.
* **config/plugin.js** used to configure the plugins that need to be loaded, see Plugin for details.
* **lib/middleware/**** used to place middleware.
* **lib/spec.js** used to initialize works at startup.
* **public** used to store static resources.
* **test** used for unit test.
* **.core/\*\*/*** the core application for peajs, which could be extended according to business requirement.


> app/model/** used to place the domain model, optional. It would be created if a database is chosen when initialize a project by yo.


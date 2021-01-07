---
description: >-
  Here we introduce IceHrm extensions and covers the steps needed to create a
  basic extension
---

# Creating First Extension

## Introduction

IceHrm extensions allow developers to extend the features offered by IceHrm without making changes to the IceHrm core. Here we will start building an extension to list some tasks for employees

* Create the directory `icehrm/extensions` if it doesn't exist
* Create a directory named `tasks` inside `icehrm/extensions`

{% hint style="info" %}
Code for this extension is here: [https://github.com/gamonoid/icehrm/tree/feature/custom-extentions-example/extensions/tasks](https://github.com/gamonoid/icehrm/tree/feature/custom-extentions-example/extensions/tasks)
{% endhint %}

### Add meta.json file

```text
icehrm
    |--extnsions
          |--tasks
               |--meta.json
```

The meta.json file for this extension should look like:

```javascript
{
    "label": "My Tasks",
    "menu": ["Tasks", "fa-list"],
    "icon": "fa-tasks",
    "user_levels": [
        "Admin",
        "Manager",
        "User"
    ],
    "model_namespace": "\\Tasks\\Model",
    "manager": "\\Tasks\\Extension",
    "headless": false
}
```

* **menu**: the name of the main menu and the icon for the main menu
* **label**: the name of the menu item that will be created by this extension
* **icon**: the icon for the menu that will hold the extension
* **user\_levels**: which types of users will be able to see and use the extension \(in this case Admins / Managers and Employees\)
* **headless**: if true this extension will not have any UI visibility. It'll just function as a background module
* **manager**: the main class which will control the extension
* **model\_namespace**: the namespace which will hold all the database model classes

### Add Extension Manager Class

```text
icehrm
    |--extnsions
          |--tasks
               |--src
                  |--Tasks
                       |--Extension.php
               |--meta.json
```

#### Extension.php

```php
<?php
namespace Tasks;

use Classes\IceExtension;

class Extension extends IceExtension
{

    public function install() {

    }

    public function uninstall() {

    }

    public function setupModuleClassDefinitions()
    {

    }

    public function setupRestEndPoints()
    {

    }
}
```

### Adding Extension Include File

{% hint style="warning" %}
Every extension should have an include file with the same name as the extension. In our example, it will be tasks.php
{% endhint %}

```text
icehrm
    |--extnsions
          |--tasks
               |--src
                  |--Tasks
                       |--Extension.php
               |--meta.json
               |--tasks.php
```

#### tasks.php

```text
<?php

require_once __DIR__.'/src/Tasks/Extension.php';
```

### Adding the View file

{% hint style="warning" %}
Every extension must have a view file if it's not running on headless mode. File should always be &lt;extension\_dir&gt;/web/index.php
{% endhint %}

```text
icehrm
    |--extnsions
          |--tasks
               |--src
                  |--Tasks
                       |--Extension.php
               |--web
                   |--index.php
               |--meta.json
               |--tasks.php
```

### web/index.php

```php
<?php
$user = \Classes\BaseService::getInstance()->getCurrentUser();
echo "Welcome ".$user->username;
```

Here we use a core class from Icehrm to get the currently logged in user

## Load the Extension in IceHrm

Visit `http://icehrm.os` and you should see the **My Tasks** menu

![](../.gitbook/assets/icehrm-my-tasks-extension.png)


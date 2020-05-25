---
description: How to create a new module in icehrm
---

# Create a New Module

You can create a new module in IceHrm without putting much effort. Let's create a sample module called 'rooms'.

There are 2 types of modules in IceHrm.

These modules are directly separated to allow different access level. In IceHrm we have three main user levels, Admin, Manager and Employee. Users with Employee level access can only  

1. **common**: `common` modules live under icehrm/core/modules and icehrm/web/modules directories. There modules can be accessed by all three main user levels \(`Admin` / `Manager` / `Employee`\)
2. **admin**: `admin` modules can only be accessed by `Admin` and `Manager` level users. By default a user with `Admin` user level get access to all these modules. But for Manager user level access should be provided explicitly.

Here we are creating an admin module. The new module is called Meeting Rooms, and allow users to create some new meeting rooms

## Create a Migration

First we need to create a migration to add a new database table called 'MeetingRooms'.

Create a new php file inside `core -> migrations` and name it accordingly. Name is formatted as `v<date_YYYYMMDD>_<TARGET_VERSION>_<migration name>.php`

Make sure to keep the class name and migration name in sync

Write sql query to create the new table. \(in just ignoring migration down function here\)

```text
<?php
   namespace Classes\Migration;

   class v20200331_270009_add_meeting_rooms_table extends AbstractMigration {

       public function up(){

           $sql = <<<'SQL'
   create table `MeetingRooms` (
   `id` bigint(20) NOT NULL AUTO_INCREMENT,
   `name` varchar(100),
   `description` varchar(500),
   `meeting_link` varchar(500),
   `departments` varchar(250),
   `teams` varchar(250),
   `updated` datetime default NULL,
   `created` datetime default NULL,
   primary key (`id`),
   ) engine=innodb default charset=utf8;
   SQL;

         return $this->executeQuery($sql);

       }
       public function down(){
           return true;
       }
   }
```

Add the file name of this migration to the top of `list.php` file inside the `core -> migrations` directory.

Migration will run automatically and create the table. When you refresh any page in IceHrm

### Create model class

Create a folder called 'Rooms' inside `core->src` and create the model class inside. We'll name it as 'MeetingRoom.php'. We can provide module access here.

It's better to maintain the existing folder structure of the project throughout creating this new module. So refer the existing modules.

Add `MeetingRoom.php` file inside `core/src/Rooms/Common/Model`

```text
<?php
   namespace Rooms\Common\Model;

   use Classes\ModuleAccess;
   use Model\BaseModel;

   class MeetingRoom extends BaseModel
   {
       public $table = 'MeetingRooms';

       public function getAdminAccess()
       {
           return ["get","element","save","delete"];
       }

       public function getManagerAccess()
       {
           return ["get","element","save"];
       }

       public function getUserAccess()
       {
           return [];
       }

       public function getAnonymousAccess()
       {
           return [];
       }

       public function getModuleAccess()
       {
           return [
               new ModuleAccess('rooms', 'admin'),
           ];
       }
   }
```

Here you can provide different access levels to different user levels

for an example following code allows an `Admin` level users to:

* `get` - read all meeting rooms
* `element` - read a single meeting room
* `save` - save or update a meeting room
* `delete` - delete a meeting room

```text
public function getAdminAccess()
{
   return ["get","element","save","delete"];
}
```

### Implement the Module Manager Class

{% hint style="info" %}
`setupModuleClassDefinitions` method
{% endhint %}

Add `RoomsAdminManger.php` file inside `core/src/Rooms/Admin/Api`

```text
<?php
namespace Rooms\Admin\Api;

use Classes\AbstractModuleManager;

class RoomsAdminManager extends AbstractModuleManager
{
    public function initializeUserClasses()
    {
    }

    public function initializeFieldMappings()
    {
    }

    public function initializeDatabaseErrorMappings()
    {
    }

    public function setupModuleClassDefinitions()
    {
        $this->addModelClass('MeetingRoom');
    }

    public function setupRestEndPoints()
    {
    }

    public function getDashboardItemData()
    {
    }

    public function initQuickAccessMenu()
    {
    }

    public function initCalculationHooks()
    {
    }
}
```

### Implement frontend changes

Javascript files are inside `web` folder.

Create a new folder named `rooms` inside `icehrm/web/admin/src`

Then add `RoomsAdapter` class as shown below in`icehrm/web/admin/src/rooms/lib.js` 

* **getDataMapping** - defines which data is displayed in the table
* **getHeaders** - defines table headers \(the order of the headers is used to map headers to data\)
* **getFormFields** - defines the form for adding a meeting room

```text
import AdapterBase from '../../../api/AdapterBase';

class RoomsAdapter extends AdapterBase {
  getDataMapping() {
    return [
      'id',
      'name',
      'description',
      'meeting_link',
    ];
  }

  getHeaders() {
    return [
      { sTitle: 'ID', bVisible: false },
      { sTitle: 'Name' },
      { sTitle: 'Description' },
      { sTitle: 'Link' },
    ];
  }

  getFormFields() {
    return [
      ['id', { label: 'ID', type: 'hidden' }],
      ['name', { label: 'Room Name', type: 'text', help: 'Name of the room' }],
      ['description', { label: 'Description', type: 'textarea', validation: 'none' }],
      ['departments', { label: 'Department', type: 'select2multi', 'remote-source': ['CompanyStructure', 'id', 'title'] }],
      ['teams', { label: 'Team', type: 'select2multi', 'remote-source': ['EmployeeTeams', 'id', 'name'] }],
      ['meeting_link', { label: 'Meeting Link', type: 'text' }],
    ];
  }
}

module.exports = { RoomsAdapter };
```

Add `icehrm/web/admin/src/rooms/index.js`

This file wires the ES6 class above to the window so we can use it frontend

```text
import { RoomsAdapter } from './lib';
window.RoomsAdapter = RoomsAdapter;
```



### Creating admin files

Create the folder `icehrm/core/admin/rooms`

Then create the `index.php`

```text
<?php

$moduleName = 'rooms';
$moduleGroup = 'admin';
define('MODULE_PATH',dirname(__FILE__));
include APP_BASE_PATH.'header.php';
include APP_BASE_PATH.'modulejslibs.inc.php';
?><div class="span9">

    <ul class="nav nav-tabs" id="modTab" style="margin-bottom:0px;margin-left:5px;border-bottom: none;">
        <li class="active"><a id="tabRoom" href="#tabPageRoom"><?=t('Meeting Rooms')?></a></li>
    </ul>

    <div class="tab-content">
        <div class="tab-pane active" id="tabPageRoom">
            <div id="Room" class="reviewBlock" data-content="List" style="padding-left:5px;">

            </div>
            <div id="RoomForm" class="reviewBlock" data-content="Form" style="padding-left:5px;display:none;">

            </div>
        </div>

    </div>

</div>
    <script>
        var modJsList = new Array();

        modJsList['tabRoom'] = new RoomsAdapter( 'MeetingRoom','Room');

        var modJs = modJsList['tabRoom'];

    </script>
<?php include APP_BASE_PATH.'footer.php';?>
```

and `meta.json` file

When instantiating `RoomsAdapter` the endpoint and tab name are provided as parameters.

We are creating this `Meeting Room` module inside a main menu named `Remote Work`.

```text
{
  "label": "Meeting Rooms",
  "menu": "Remote Work",
  "order": "83",
  "icon": "fa-comments",
  "user_levels": [
    "Admin",
    "Manager"
  ],
  "permissions": [],
  "model_namespace": "\\Rooms\\Common\\Model",
  "manager": "\\Rooms\\Admin\\Api\\RoomsAdminManager"
}
```

Give a label name and a suitable font awesome icon name. Add the correct paths to model and manger.

We can provide a suitable font awesome icon to the main menu by editing `core->admin->meta.json`

### Include module in gulpfile.json

There is a `gulpfile.js` file inside root. You need to add the new module under admin-js or module-js according to its type. In this case it's admin-js

```text
gulp.task('admin-js', (done) => {
  // we define our input files, which we want to have
  // bundled:
  let files = [
    'attendance',
    'company_structure',
    'clients',
    'dashboard',
    'data',
    'rooms'
    ....
  ];

```

Finally you have to rebuild the frontend with gulp command.

### Vagrant ssh and log into vagrant machine

RUN `gulp` inside your vagrant machine path /vagrant

```text
~ $ cd /vagrant
~ $ gulp
```

The new module should be created now. Refresh your icehrm to see the new module


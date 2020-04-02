# Creating a new module

You can create a new module in IceHrm without putting much effort. Let's create a sample module called 'rooms'.

There are 2 types of modules in IceHrm. Here we are creating an admin module. There are user modules as well. You need to choose `admin` or `module` folders inside `core` and `web` according to the module type you are creating.

## Create Migration

First we need to create a migration to add a new database table called 'MeetingRooms'.

Create a new php file inside `core -> migrations` and name it accordingly.

Write sql query to create the new table.

```
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
   primary key (`id`),
   `updated` datetime default NULL,
   `created` datetime default NULL
   ) engine=innodb default charset=utf8;
   SQL;
   
         return $this->executeQuery($sql);
   
       }
       public function down(){
           return true;
       }
   }

```

Add the file name of this migration to the top of `list.php` file inside the same directory.

Migration will run automatically and create the table.

### Create model class

Create a folder called 'Rooms' inside `core->src` and create the model class inside. We'll name it as 'MeetingRoom.php'. We can provide module access here.

Its better to maintain the existing folder structure of the project throughout creating this new module. So refer the existing modules.


```
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

Create RoomsAdminManger.php file inside `core->src->Rooms->Api`

```
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


#### Create javascript files

Javascript files are inside `web` folder.

Create a new folder named `rooms` inside `web->admin->src`

Create `index.js` 

```
import { RoomsAdapter } from './lib';
window.RoomsAdapter = RoomsAdapter;
```
and `lib.js` files.

```
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
`getDataMapping()` and `getHeaders()` methods should contain the same fields.

You can use the form data input types accordingly from `getFormFields()` method.



### Creating admin files

Create a folder named rooms inside `core->admin`

Let's create the `index.php`
```
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

```
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

There is a `gulpfile.json` file inside root. You need to add the new module under admin-js or module-js according to its type.

Finally you have to rebuild the frontend with gulp command.

vagrant ssh and log into vagrant machine.
```
~ $ cd /vagrant
~ $ gulp
```

The new module should be created now.

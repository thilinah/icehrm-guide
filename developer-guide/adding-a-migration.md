---
description: >-
  Here we will show you how to add a database migration
---

# Creating a Migration

## Introduction

When your extension is installed on a IceHrm installtion, you can make changs o the IceHrm database using Migrations.

### Add a Simple Migration

This extension will manage tasks. So we might have to make changes to the database. For that we should add a migration. We can use the core migration classes offered by Icehrm.

```text
icehrm
    |--extnsions
          |--tasks
               |--src
                  |--Tasks
                       |--Extension.php
                       |--Migration.php
               |--meta.json
```

#### Migration.php

```php
<?php
namespace Tasks;

use Classes\Migration\AbstractMigration;

class Migration extends AbstractMigration
{
    public function up()
    {
        $sql = <<<'SQL'
create table `Tasks` (
	`id` bigint(20) NOT NULL AUTO_INCREMENT,
	`employee` bigint(20) NULL,
	`name` varchar(250) NOT NULL,
	`description` TEXT NULL,
	`attachment` varchar(100) NULL,
	`created` DATETIME default NULL,
	`updated` DATETIME default NULL,
	primary key  (`id`),
	CONSTRAINT `Fk_EmployeeTasks_Employees` FOREIGN KEY (`employee`) REFERENCES `Employees` (`id`) ON DELETE CASCADE ON UPDATE CASCADE
) engine=innodb default charset=utf8;
SQL;
        return $this->executeQuery($sql);
    }

    public function down()
    {
        $sql = <<<'SQL'
DROP TABLE IF EXISTS `Tasks`; 
SQL;
        return $this->executeQuery($sql);
    }
}
```

This migration will create a table named Tasks in IceHrm database. The migration will be executed only on the first time the extension is enabled. If you are making changes to the migration you need to make sure it gets applied manually.

### Execute Migration when Installing the Extension

For this, we should update the Extension.php a bit to execute the migration when the extension is activated for the first time

```php
<?php
namespace Tasks;

use Classes\IceExtension;

class Extension extends IceExtension
{

    public function install() {
        $migration = new Migration();
        return $migration->up();
    }

    public function uninstall() {
        $migration = new Migration();
        return $migration->down();
    }

    public function setupModuleClassDefinitions()
    {

    }

    public function setupRestEndPoints()
    {

    }
}
```

### Update Extension Include File

#### tasks.php

```text
<?php

require_once __DIR__.'/src/Tasks/Extension.php';
require_once __DIR__.'/src/Tasks/Migration.php';

```

{% hint style="warning" %}
Since the extension is already active the migration will not get executed. Because of this we need to remove it from the Modules table manually. 
{% endhint %}

```sql
$> DELETE from Modules where name = 'tasks' and mod_group = 'extension';
```

{% hint style="success" %}
Now reload the page and you will be able to see the new Tasks table in your IceHrm database.
{% endhint %}

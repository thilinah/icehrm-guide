# Manual Installation

If you encountered any issues with automated installation please follow these steps to manually configure icehrm on your server.

### Download and Extract IceHrm Latest Release

1. If you are using icehrm opensource version download it from \([https://github.com/gamonoid/icehrm/releases](https://github.com/gamonoid/icehrm/releases)\). Make sure to download the release .zip or .gz file \(e.g : icehrm\_v19.0.OS.zip\).
2. If you have purchased icehrm pro, you can find installation directory inside the files you have downloaded after purchase.
3. Extract icerm to public web directory root on your web server **for now we assume it to be \(/var/www/\)**

### Creating MySQL Database

Login to your mysql installation and create a database and a user for icehrm

```
mysql> create database icehrm;
mysql> create user 'icehrm_user'@'localhost' identified by 'icehrm_pwd';
mysql> grant all on icehrm.* to 'icehrm_user'@'localhost';
```

Then execute icehrm database scripts on newly created mysql database via console or phpmyadmin.

The two files you need to execute can be found in icehrm installation directory \(**assuming it to be /var/www/icehrm**\)

1. /var/www/icehrm/scripts/icehrmdb.sql
2. /var/www/icehrm/scripts/icehrm\_\_master\_\_data.sql

```
mysql> use icehrm;
mysql> source /var/www/icehrm/scripts/icehrmdb.sql
mysql> source /var/www/icehrm/scripts/icehrm_master_data.sql
```

### Creating Configuration File

Inside &lt;icehrm&gt;/app/ directory you will find:

`config.sample.php`

```
<?php 
ini_set('error_log', '_LOG_');
define('APP_NAME', 'Ice Framework');
define('FB_URL', 'Ice Framework');
define('TWITTER_URL', 'Ice Framework');
define('CLIENT_NAME', '_CLIENT_');
define('APP_BASE_PATH', '_APP_BASE_PATH_');
define('CLIENT_BASE_PATH', '_CLIENT_BASE_PATH_');
define('BASE_URL','_BASE_URL_');
define('CLIENT_BASE_URL','_CLIENTBASE_URL_');
define('APP_DB', '_APP_DB_');
define('APP_USERNAME', '_APP_USERNAME_');
define('APP_PASSWORD', '_APP_PASSWORD_');
define('APP_HOST', '_APP_HOST_');
define('APP_CON_STR', 'mysqli://'.APP_USERNAME.':'.APP_PASSWORD.'@'.APP_HOST.'/'.APP_DB);
//file upload
define('FILE_TYPES', 'jpg,png,jpeg');
define('MAX_FILE_SIZE_KB', 10 * 1024);
//Home Links
define('HOME_LINK_ADMIN', CLIENT_BASE_URL."?g=admin&n=dashboard&m=admin_Admin");
define('HOME_LINK_OTHERS', CLIENT_BASE_URL."?g=modules&n=dashboard&m=module_My_Account");
```

Rename this file to `config.php` and start updating it.

You may change app name and social media urls to your company social media accounts:

```
define('APP_NAME', 'Ice Framework');
define('FB_URL', 'Ice Framework');
define('TWITTER_URL', 'Ice Framework');
define('CLIENT_NAME', '_CLIENT_');
```

So above section can be changed to:

By default CLIENT\_NAME should be app

```
define('APP_NAME', 'IceHrm - Your Company Name');
define('FB_URL', 'https://facebook.com/yourcompany');
define('TWITTER_URL', 'https://twitter.com/yourhandle');
define('CLIENT_NAME', 'app');
```

For updating urls you need to know the absolute path of your icehrm installation and url to your icehrm installation.

For an example we assume path to icehrm is : **/var/www/icehrm/** and icehrm web url to be [http://your-company-domain.com/icehrm](http://your-company-domain.com/icehrm) then paths and urls should be updated as below.

```
define('APP_BASE_PATH', '/var/www/icehrm/core/');
define('CLIENT_BASE_PATH', '/var/www/icehrm/app/');
define('BASE_URL','http://your-company-domain.com/icehrm/web/');
define('CLIENT_BASE_URL','http://your-company-domain.com/icehrm/app/');
```

If you are using windows note that all the path should be specified with forward slash

e.g

```
define('APP_BASE_PATH', 'C:/xampp/htdocs/icehrm/core/');
```

Then you can update the database configurations as shown below:

```
define('APP_DB', 'icehrm');
define('APP_USERNAME', 'icehrm_user');
define('APP_PASSWORD', 'icehrm_pwd');
define('APP_HOST', 'localhost');
```

If you would like to upload files larger than 10MB you can update MAX\_FILE\_SIZE\_KB config.


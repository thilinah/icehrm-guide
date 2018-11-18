# Installation

**_If you are using icehrm cloud please skip this chapter_**

Getting IceHrm installed only take a few minutes. If it ever becomes a problem, please [file an issue](https://github.com/gamonoid/icehrm/issues/new) describing the issue you encountered and how we might make the process easier.

#### Requirements {#requirements}

Before installing IceHrm please make sure your system supports following requirements you’ll need to make sure your system has before you start.

* [PHP 5.6 or Higher](http://php.net/)
* Net\_SMTP extension for PHP
* [MySQL](http://dev.mysql.com/downloads/)
* [php-mysql extention](http://php.net/manual/en/mysqli.installation.php)
$&gt; sudo apt-get install php-mysql
* [PHP GD library](http://php.net/manual/en/mysqli.installation.php)
$&gt; sudo apt-get install php7.0-gd

###### Optional Modules {#optional-modules}

These are optional components which could improve icehrm performance

* [Memcache](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-memcache-on-ubuntu-14-04)

#### Installation {#installation}

* If you are installing the open source version, download the latest release from [GitHub](https://github.com/gamonoid/icehrm/releases/latest)

* If you are installing the pro version or enterprise you should have received the files after purchase.

* Copy the downloaded file to the path you want to install iCE Hrm in your server and extract.

* Create a mysql DB for and user. Grant all on iCE Hrm DB to new DB user.

* Visit iCE Hrm installation path in your browser.

* During the installation form, fill in details appropriately.

* Once the application is installed use the username = admin and password = admin to login to your system.


After installation the settings module can be accessed by login in as admin and going to System->Settings


## Cron (Scheduled Task) for Notifications

Notification cron is used to send periodic notifications. Document expiry notifications will depend on this scheduler.

To trigger the scheduler you need to run following file

```
(IceHrm Root)/app/cron.php
```

#### Setting up Linux Cron
In linux environment a cron should be setup to run every 10 minutes.

This can be done by placing following line in your crontab. Depending on your server you can edit crontab sudo vi /etc/crontab

or you can use crontab -e command

```
/10 * (IceHrm Root)/app/cron.php
```

make sure that (IceHrm Root)/app/cron.php file is executable *
Setting up Windows Scheduler
For setting up the windows scheduler please check [http://windows.microsoft.com/en-au/windows/schedule-task#1TC=windows-7](http://windows.microsoft.com/en-au/windows/schedule-task#1TC=windows-7)

## Configure PDF Downloads

IceHrm uses [WKHTMLTOPDF](https://wkhtmltopdf.org/index.html)

You can download and install the correct release for your OS here [https://wkhtmltopdf.org/downloads.html](https://wkhtmltopdf.org/downloads.html)

Then you should find the path to 'wkhtmltopdf' and update ```icehrm/core/config.base.php``` as shown below

```
if(!defined('WK_HTML_PATH')){
    define('WK_HTML_PATH', '/usr/local/bin/wkhtmltopdf');
}
```
# Installation

_**If you are using icehrm cloud please skip this chapter**_

Getting IceHrm installed only take a few minutes. If it ever becomes a problem, please [file an issue](https://github.com/gamonoid/icehrm/issues/new) describing the issue you encountered and how we might make the process easier.

### Software Requirements <a id="requirements"></a>

Before installing IceHrm please make sure your system supports following requirements you’ll need to make sure your system has before you start. 

**Operating system:** Dabian \(8/9/10\) or Ubuntu \(18 LTS or 20 LTS\) - Any other linux distribution will also, but we recommend to select a long term support \(LTS\) release

**Web Server**: 

Nginx \(Recommended\) or Apache.

 If you are using windows please use WAMPP \([https://bitnami.com/stack/wamp/installer](https://bitnami.com/stack/wamp/installer)\) to host IceHrm

**Database:** MySQL 5.7 \(MySQL 8.0 is not supported yet\)

**PHP**: PHP 7.0 or Higher \(IceHrm works with PHP 5.6 but the support will be removed soon\)

**PHP Extensions**

* Net\_SMTP extension for PHP
* [php-mysql extention](http://php.net/manual/en/mysqli.installation.php)

  $&gt; sudo apt-get install php-mysql

* [PHP GD library](http://php.net/manual/en/mysqli.installation.php)

  $&gt; sudo apt-get install php7.0-gd

#### Optional Extensions <a id="optional-modules"></a>

These are optional components which could improve icehrm performance

* [Memcache](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-memcache-on-ubuntu-14-04)

### Hardware Requirements <a id="requirements"></a>

|  | 100 Employees | 500 Employees | 2000 Employees |
| :--- | :--- | :--- | :--- |
| **CPU** | 1 Core | 2 Cores | 4 Cores |
| **RAM** | 2 GB | 4 GB | 8 GB |
| **Storage \(Avg\)** | 15 GB | 40 GB | 80 GB |
| **Data Transfer \(Avg / Month\)** | 20 GB | 100 GB | 400 GB |

### Installation <a id="installation"></a>

* If you are installing the open source version, download the latest release from [GitHub](https://github.com/gamonoid/icehrm/releases/latest)
* If you are installing the IceHrmPro you should have received the files after purchase.
* Copy the downloaded file to the path you want to install iCE Hrm in your server and extract.
* Create a mysql DB for and user. Grant all on iCE Hrm DB to new DB user.
* Visit iCE Hrm installation path in your browser.
* During the installation form, fill in details appropriately.
* Once the application is installed use the username = admin and password = admin to login to your system.

After installation the settings module can be accessed by login in as admin and going to System-&gt;Settings

## Cron \(Scheduled Task\) for Notifications

Notification cron is used to send periodic notifications. Document expiry notifications will depend on this scheduler.

To trigger the scheduler you need to run following file

```text
(IceHrm Root)/app/cron.php
```

### Setting up Linux Cron

In linux environment a cron should be setup to run every 10 minutes.

This can be done by placing following line in your crontab. Depending on your server you can edit crontab sudo vi /etc/crontab

or you can use crontab -e command

```text
/10 * (IceHrm Root)/app/cron.php
```

make sure that \(IceHrm Root\)/app/cron.php file is executable \* Setting up Windows Scheduler For setting up the windows scheduler please check [http://windows.microsoft.com/en-au/windows/schedule-task\#1TC=windows-7](http://windows.microsoft.com/en-au/windows/schedule-task#1TC=windows-7)

## Configure PDF Downloads

IceHrm uses [WKHTMLTOPDF](https://wkhtmltopdf.org/index.html)

You can download and install the correct release for your OS here [https://wkhtmltopdf.org/downloads.html](https://wkhtmltopdf.org/downloads.html)

Then you should find the path to 'wkhtmltopdf' and update `icehrm/core/config.base.php` as shown below

```text
if(!defined('WK_HTML_PATH')){
    define('WK_HTML_PATH', '/usr/local/bin/wkhtmltopdf');
}
```


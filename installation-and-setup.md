#
Installation

**_If you are using icehrm cloud please skip this chapter_**

Getting IceHrm installed only take a few minutes. If it ever becomes a problem, please [file an issue](https://github.com/gamonoid/icehrm/issues/new) describing the issue you encountered and how we might make the process easier.

#### Requirements {#requirements}

Before installing IceHrm please make sure your system supports following requirements you’ll need to make sure your system has before you start.

* [PHP 5.3 or Higher](http://php.net/)
* Net\_SMTP extension for PHP
* [MySQL v5.5](http://dev.mysql.com/downloads/)
* [php-mysql extention](http://php.net/manual/en/mysqli.installation.php)
* [PHP GD library](http://php.net/manual/en/mysqli.installation.php)
$&gt; apt-get update -$
$&gt; apt-get install php5-gd

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


## Global Settings

<div class="mobile-side-scroller">
<table>
<thead>
<tr>
<th>Setting</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td><p><code>Company: Name</code></p></td>
<td><p>
Name of the company

</p></td>
</tr>
<tr>
<td><p><code>Company: Logo</code></p></td>
<td><p>

Company logo. You may upload the company logo here.
Ideally should be 200px wide and height between 50px to 150 px.

</p></td>
</tr>
<tr>
<td><p><code>Company: Description</code></p></td>
<td><p>

A short description about the company. Will be used mainly in recruitment module

</p></td>
</tr>
<tr>
<td><p><code>Email: Enable</code></p></td>
<td><p>
Set this to "No" to disable all outgoing emails from modules. Value "Yes" will enable outgoing emails
</p></td>
</tr>
</tbody>
</table>
</div>

## Email Settings

#### Configuring Email with SMTP

<div class="mobile-side-scroller">
<table>
<thead>
<tr>
<th>Setting</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td><p><code>Email: Mode</code></p></td>
<td><p>

This should be set to SMTP

</p></td>
</tr>
<tr>
<td><p><code>Email: SMTP Host</code></p></td>
<td><p>

If you are using local machine to send emails, set this to localhost. If not set the IP address of the server you are using to send emails

</p></td>
</tr>
<tr>
<td><p><code>Email: SMTP Authentication</code></p></td>
<td><p>

Set this to "Yes" if SMTP server authorization is enabled

</p></td>
</tr>
<tr>
<td><p><code>Email: SMTP User</code></p></td>
<td><p>

User name of the SMTP user

</p></td>
</tr>
<tr>
<td><p><code>Email: SMTP Password</code></p></td>
<td><p>

SMTP user password

</p></td>
</tr>
<tr>
<td><p><code>Email: SMTP Port</code></p></td>
<td><p>

Port configured in SMTP server (Default 25)

</p></td>
</tr>
<tr>
<td><p><code>Email: Email From</code></p></td>
<td><p>

From email address (e.g icehrm@mydomain.com)

</p></td>
</tr>
</tbody>
</table>
</div>

#### Configuring Email with Amazon SES

<div class="mobile-side-scroller">
<table>
<thead>
<tr>
<th>Setting</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td><p><code>Email: Mode</code></p></td>
<td><p>

This should be set to SES

</p></td>
</tr>
<tr>
<td><p><code>Email: Amazon SES Key</code></p></td>
<td><p>

Amazon access key Id (You can get this through AWS console)

</p></td>
</tr>
<tr>
<td><p><code>Email: Amazone SES Secret</code></p></td>
<td><p>

Amazon access key secret

</p></td>
</tr>
<tr>
<td><p><code>Email: Email From</code></p></td>
<td><p>

Authorized email address for sending emails through SES

</p></td>
</tr>
</tbody>
</table>
</div>

#### Configuring Email with Gmail

<div class="mobile-side-scroller">
<table>
<thead>
<tr>
<th>Setting</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td><p><code>Email: Mode</code></p></td>
<td><p>

This should be set to SMTP

</p></td>
</tr>
<tr>
<td><p><code>Email: SMTP Host</code></p></td>
<td><p>

ssl://smtp.gmail.com

</p></td>
</tr>
<tr>
<td><p><code>Email: SMTP Authentication</code></p></td>
<td><p>

Yes

</p></td>
</tr>
<tr>
<td><p><code>Email: SMTP User</code></p></td>
<td><p>

yourgmailaddress@gmail.com

</p></td>
</tr>
<tr>
<td><p><code>Email: SMTP Password</code></p></td>
<td><p>

Gmail password

</p></td>
</tr>
<tr>
<td><p><code>Email: SMTP Port</code></p></td>
<td><p>

465

</p></td>
</tr>
<tr>
<td><p><code>Email: Email From</code></p></td>
<td><p>

yourgmailaddress@gmail.com

</p></td>
</tr>
</tbody>
</table>
</div>

## Developer Settings

<div class="mobile-side-scroller">
<table>
<thead>
<tr>
<th>Setting</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td><p><code>System: Do not pass JSON in request</code></p></td>
<td><p>

Select Yes if you are having trouble loading data for some tables

</p></td>
</tr>
<tr>
<td><p><code>System: Reset Modules and Permissions</code></p></td>
<td><p>

When this is set to “Yes” IceHrm will reset all values given in System->Permissions module. This setting can be used to reload permissions after adding new permissions to module meta.json file

</p></td>
</tr>
<tr>
<td><p><code>System: Add New Permissions</code></p></td>
<td><p>

Add new permissions without resetting modules

</p></td>
</tr>
<tr>
<td><p><code>System: Debug Mode</code></p></td>
<td><p>

Print debug log messages

</p></td>
</tr>
</tbody>
</table>
</div>

## Other Settings

<div class="mobile-side-scroller">
<table>
<thead>
<tr>
<th>Setting</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td><p><code>Leave: Share Calendar to Whole Company</code></p></td>
<td><p>

If "Yes" all the employees of company can see other peoples' leave schedules.
If set to "No" only admins and supervisors will be able to see leave schedule of subordinates

</p></td>
</tr>
<tr>
<td><p><code>Leave: CC Emails</code></p></td>
<td><p>

Every email sent though leave module will be CC to these comma seperated list of emails addresses

</p></td>
</tr>
<tr>
<td><p><code>Leave: BCC Emails</code></p></td>
<td><p>

Every email sent though leave module will be BCC to these comma seperated list of emails addresses

</p></td>
</tr>
<tr>
<td><p><code>Attendance: Time-sheet Cross Check</code></p></td>
<td><p>

Only allow users to add an entry to a timesheet only if they have marked atteandance for the selected period

</p></td>
</tr>
<tr>
<td><p><code>Recruitment: Show Quick Apply</code></p></td>
<td><p>

Show quick apply button when candidates are applying for jobs. Quick apply allow candidates to apply with minimum amount of information

</p></td>
</tr>
<tr>
<td><p><code>Recruitment: Show Apply</code></p></td>
<td><p>

Show apply button when candidates are applying for jobs

</p></td>
</tr>
</tbody>
</table>
</div>

## Cron for Notifications

Notification cron is used to send periodic notifications. Document expiry notifications will depend on this scheduler.

To trigger the scheduler you need to run following file

<code>(IceHrm Root)/app/cron.php</code>


## LDAP Settings

This section describe the process of configuring LDAP with IceHrm

<div class="note warning">
<h5>php5-ldap</h5>
<p>PHP5 LDAP extension should be installed for LDAP to work. Also make sure all required outbound ports are opened</p>
</div>

Before using please install php5-ldap module. R
Run following command to install php5-ldap

<code>$> sudo apt-get install php5-ldap</code>

For using php ldap on windows please [refer](http://stackoverflow.com/questions/16864306/fatal-error-call-to-undefined-function-ldap-connect)


<div class="note info">
<h5>No LDAP for user with username "admin"</h5>
<p>The user "admin" will always login with local db username and password (even LDAP is enabled)</p>
</div>


Use these config to test LDAP connection with following test LDAP server
[http://www.forumsys.com/tutorials/integration-how-to/ldap/online-ldap-test-server/](http://www.forumsys.com/tutorials/integration-how-to/ldap/online-ldap-test-server/)


#### Change configs as follows under System->Settings


<div class="mobile-side-scroller">
<table>
<thead>
<tr>
<th>Setting</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td><p><code>LDAP: Enabled</code></p></td>
<td><p>
Yes

</p></td>
</tr>
<tr>
<td><p><code>LDAP: Server</code></p></td>
<td><p>

ldap.forumsys.com

</p></td>
</tr>
<tr>
<td><p><code>LDAP: Port</code></p></td>
<td><p>

389

</p></td>
</tr>
<tr>
<td><p><code>LDAP: Root DN</code></p></td>
<td><p>

dc=example,dc=com

</p></td>
</tr>
<tr>
<td><p><code>LDAP: Manager DN</code></p></td>
<td><p>

cn=read-only-admin,dc=example,dc=com

</p></td>
</tr>
<tr>
<td><p><code>LDAP: Manager Password</code></p></td>
<td><p>

password

</p></td>
</tr>
<tr>
<td><p><code>LDAP: Version 3</code></p></td>
<td><p>

Yes

</p></td>
</tr>
<tr>
<td><p><code>LDAP: User Filter</code></p></td>
<td><p>

uid={}

</p></td>
</tr>
</tbody>
</table>
</div>

Then create a user with username "riemann" under System->Users

Logout and try login with riemann/password


<div class="note info">
<h5>Issue with LDAP</h5>
<p>If you are facing login issues after enabling LDAP, you can still login as user "admin" and disable LDAP</p>
</div>

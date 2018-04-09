## LDAP Settings

This section describe the process of configuring LDAP with IceHrm

<div class="note warning">
<h5>php-ldap</h5>
<p>PHP5 LDAP extension should be installed for LDAP to work. Also make sure all required outbound ports are opened</p>
</div>

Before using please install php-ldap module.

**For PHP 5.3**
<code>$> sudo apt-get install php5-ldap</code>

**For PHP 7.0**
<code>$> sudo apt-get install php-ldap</code>


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

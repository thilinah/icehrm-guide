# Using LDAP

This section describe the process of configuring LDAP with IceHrm

### PHP ldap extension

PHP LDAP extension should be installed for LDAP to work. Also make sure you can connect ot the LDAP host via the provided port

Before using please install php-ldap module.

**For PHP 5.3** `$> sudo apt-get install php5-ldap`

**For PHP 7.0** `$> sudo apt-get install php-ldap`

**For PHP 7.**`3` `$> sudo apt-get install php7.3-ldap`

For using php ldap on windows please [refer](http://stackoverflow.com/questions/16864306/fatal-error-call-to-undefined-function-ldap-connect)

### Enabling LDAP

LDAP can be enabled via System -&gt; Settings -&gt; LDAP. Make sure to configure all the parameters correctly

### Creating a LDAP User

IceHrm can not extract users automatically from LDAP. You need to create a matching user in IceHrm with the same username. For an example if you have a user in your LDAP with username "**user1"** and ****password **"pass123"**. Then you need to:

1. Create a user in icehrm with username "user1"
2. No need to set a password, as we will use LDAP to authenticate this user
3. The new user can login with username "user1" and password "pass123", which is his/her LDAP password

### No LDAP for user with username "admin"

The user "admin" will always login with local db username and password \(even LDAP is enabled\)

### Testing LDAP with a test server

This is a way to debug your LDAP setup. You can try to connect to a test LDAP server to find out if the problem is with your LDAP setup or if IceHrm

Use these config to test LDAP connection with following test LDAP server [http://www.forumsys.com/tutorials/integration-how-to/ldap/online-ldap-test-server/](http://www.forumsys.com/tutorials/integration-how-to/ldap/online-ldap-test-server/)

#### Change configs as follows under System-&gt;Settings

| Setting | Description |
| :--- | :--- |
| `LDAP: Enabled` |  Yes |
| `LDAP: Server` |  ldap.forumsys.com |
| `LDAP: Port` |  389 |
| `LDAP: Root DN` |  dc=example,dc=com |
| `LDAP: Manager DN` |  cn=read-only-admin,dc=example,dc=com |
| `LDAP: Manager Password` |  password |
| `LDAP: Version 3` |  Yes |
| `LDAP: User Filter` |  uid={} |

Then create a user with username "riemann" under System-&gt;Users

Logout and try login with riemann/password

### Issue with LDAP

If you are facing login issues after enabling LDAP, you can still login as user "admin" and disable LDAP


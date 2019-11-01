# Using LDAP

This section describe the process of configuring LDAP with IceHrm

### php-ldap

PHP5 LDAP extension should be installed for LDAP to work. Also make sure all required outbound ports are opened

Before using please install php-ldap module.

**For PHP 5.3** `$> sudo apt-get install php5-ldap`

**For PHP 7.0** `$> sudo apt-get install php-ldap`

For using php ldap on windows please [refer](http://stackoverflow.com/questions/16864306/fatal-error-call-to-undefined-function-ldap-connect)

### No LDAP for user with username "admin"

The user "admin" will always login with local db username and password \(even LDAP is enabled\)

Use these config to test LDAP connection with following test LDAP server [http://www.forumsys.com/tutorials/integration-how-to/ldap/online-ldap-test-server/](http://www.forumsys.com/tutorials/integration-how-to/ldap/online-ldap-test-server/)

## Change configs as follows under System-&gt;Settings

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


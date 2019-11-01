# Basic Settings

## Global Settings

| Setting | Description |
| :--- | :--- |
| `Company: Name` |  Name of the company |
| `Company: Logo` |  Company logo. You may upload the company logo here. Ideally should be 200px wide and height between 50px to 150 px. |
| `Company: Description` |  A short description about the company. Will be used mainly in recruitment module |
| `Email: Enable` |  Set this to "No" to disable all outgoing emails from modules. Value "Yes" will enable outgoing emails |

## Email Settings

### Configuring Email with SMTP

| Setting | Description |
| :--- | :--- |
| `Email: Mode` |  This should be set to SMTP |
| `Email: SMTP Host` |  If you are using local machine to send emails, set this to localhost. If not set the IP address of the server you are using to send emails |
| `Email: SMTP Authentication` |  Set this to "Yes" if SMTP server authorization is enabled |
| `Email: SMTP User` |  User name of the SMTP user |
| `Email: SMTP Password` |  SMTP user password |
| `Email: SMTP Port` |  Port configured in SMTP server \(Default 25\) |
| `Email: Email From` |  From email address \(e.g icehrm@mydomain.com\) |

### Configuring Email with Amazon SES

| Setting | Description |
| :--- | :--- |
| `Email: Mode` |  This should be set to SES |
| `Email: Amazon SES Key` |  Amazon access key Id \(You can get this through AWS console\) |
| `Email: Amazone SES Secret` |  Amazon access key secret |
| `Email: Email From` |  Authorized email address for sending emails through SES |

### Configuring Email with Gmail

| Setting | Description |
| :--- | :--- |
| `Email: Mode` |  This should be set to SMTP |
| `Email: SMTP Host` |  ssl://smtp.gmail.com |
| `Email: SMTP Authentication` |  Yes |
| `Email: SMTP User` |  yourgmailaddress@gmail.com |
| `Email: SMTP Password` |  Gmail password |
| `Email: SMTP Port` |  465 |
| `Email: Email From` |  yourgmailaddress@gmail.com |

## Developer Settings

| Setting | Description |
| :--- | :--- |
| `System: Do not pass JSON in request` |  Select Yes if you are having trouble loading data for some tables |
| `System: Reset Modules and Permissions` |  When this is set to “Yes” IceHrm will reset all values given in System-&gt;Permissions module. This setting can be used to reload permissions after adding new permissions to module meta.json file |
| `System: Add New Permissions` |  Add new permissions without resetting modules |
| `System: Debug Mode` |  Print debug log messages |

## Other Settings

| Setting | Description |
| :--- | :--- |
| `Leave: Share Calendar to Whole Company` |  If "Yes" all the employees of company can see other peoples' leave schedules. If set to "No" only admins and supervisors will be able to see leave schedule of subordinates |
| `Leave: CC Emails` |  Every email sent though leave module will be CC to these comma seperated list of emails addresses |
| `Leave: BCC Emails` |  Every email sent though leave module will be BCC to these comma seperated list of emails addresses |
| `Attendance: Time-sheet Cross Check` |  Only allow users to add an entry to a timesheet only if they have marked atteandance for the selected period |
| `Recruitment: Show Quick Apply` |  Show quick apply button when candidates are applying for jobs. Quick apply allow candidates to apply with minimum amount of information |
| `Recruitment: Show Apply` |  Show apply button when candidates are applying for jobs |


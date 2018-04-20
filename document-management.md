# Document Management

In IceHrm you can manage company documents as well as individual employee documents.

## Company Documents

Company documents can be added via <code>Employees => Document Management</code>. Depending on the confidentiality and nature of the document it can be shared only with individual employees, all employees attached to a department or all the employees in the company.

![](/assets/list-company-documents.png)

![](/assets/edit-company-documents.png)

Employees can view company documents via <code> Documents => My Documents => Company Documents </code>

![](/assets/view-company-documents.png)

## Employee Personal Documents

#### Document Types

Accessed via <code>Employees => Document Management => Document Types </code>

Document Types tab is used to define various documents relevant to your organization.The employees are able to upload documents under these categories.

#### Expire Notifications

When defining document types you can define before how many days icehrm should notify the user about the
expiring documents.

The notification cron should be setup for this feature to function properly. Please check the section [Cron for Notifications] (https://thilinah.gitbooks.io/icehrm-guide/content/installation-and-setup.html)


#### Employee Documents

Administrators and Managers can use "Employee Documents" tab to explore and manage documents uploaded by
employees or add new documents to employees.

#### Settings

Set <code>"Notifications: Send Document Expiry Emails"</code> to No if you don't wish to receive document expiry notifications.

Also set <code>Notifications: Copy Document Expiry Emails to Manager</code> to Yes if you want to send all document
expiry notifications to respective managers also
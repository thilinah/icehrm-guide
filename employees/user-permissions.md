---
description: >-
  When you want to give privilege to a particular user, you can do this by
  changing the User Level of the user or using the IceHrm User Role option.
---

# User permissions

With the updated user permission module IceHrm now supports the following user levels:

1. Admin
2. Manager
3. Employee
4. Restricted Admin
5. Restricted Manager
6. Restricted Employee

Admin user level has all the access to the IceHrm account, while the manager has limited access to administration functionalities. 

For example, under the leave module, a manager can see their subordinates leave days, can approve leaves, grant leaves. But as an admin, you can see leave requests from all the employees and act on these requests.

An employee has all the to use the platform as an employee. 

Let’s take an example scenario to understand how to grant admin access to one of your employees or managers:

1. You can log into the admin account
2. Go to the System section and click on the Users
3. Then click on the User tab in order to make changes
4. You can select the employee you want to make changes and click on the edit button

![](../.gitbook/assets/image%20%2853%29.png)

5. Now you can change the User Level of the employee to Admin.

![](../.gitbook/assets/image%20%2870%29.png)

Now you can select the user level as Admin and click on the Save button. So the particular user will have all the access granted for an admin.

### Use of Restricted User levels  <a id="use-of-restricted-user-levels"></a>

Restricted User levels are the same as the other user levels but with restricted access. If you have not granted specific permission to a restricted user using a user role, they won't have any access rights.

Let's take an example, imagine there is an external recruitment manager who will become a temporary employee of your company only to manage the recruitment related activities. 

In this case, you can add a Restricted Manager and grant only the required permissions.

This will involve providing granular entity-level permissions to a user role.  There are 4 Different types of **entity-level permissions**:

* **List - User can load the list of entities**
* **Get - User can view an individual entity**
* **Add/Edit - User can add data or edit data**
* **Delete - User can delete data**

#### Adding Restricted Recruitment Manager <a id="restricted-manager"></a>

1. Log in to the admin account
2. Go to the System section and click on the Users
3. Then click on the **User role** tab and then click on the **Add New** option in order to create a New User role
4. Then you can give a specific name to the User role - For this one, you can use Recruitment Manager
5. Then click on Add to select the permission level

![](../.gitbook/assets/image%20%2850%29.png)

  6. Select the Table and then the Permission level you need to grant and then click on Save \( According to the above example, this user only needs to view recruitment data and make adjustments, so we select List, Get, Add/Edit and Delete options for candidate, interview and application entities \)

![](../.gitbook/assets/image%20%2869%29.png)

 7. Now go to the Manage modules section under the System in order to assign the particular module to the new user role

8. Then click on the Modules tab and search for the particular module

9. Click on the edit button to make changes

![](../.gitbook/assets/image%20%2851%29.png)

10.  Select all the modules required for the recruitment process and add the created User Role to all of these modules and save changes

![](../.gitbook/assets/image%20%2865%29.png)

Once you created the User role and then Assign the module now  you can go back to the User section and click on the User tab in order to assign this to the manager

11. Select the user you want to make changes and click on the edit button

12. Now change the **User Level** of the employee into the **Restricted Manager** user level

13. Then add **Recruitment Manager** user role which you have already created

![](../.gitbook/assets/image%20%2873%29.png)

12. You won't be able to save the changes unless you have assigned a Default Module. This default module is important because that's what the users can see in their dashboard as they log in

![](http://icehrm.com/blog/content/images/2020/03/image-20.png)

Once you save the changes login to the Recruitment Manager's account, it will look like the below. And the recruitment manager will only have access to recruitment modules

![](../.gitbook/assets/image%20%2872%29.png)

#### Restricted Employees <a id="restricted-employee"></a>

**Restricted Employee** is also similar to the employee level but with restricted access. For example, **imagine you need to give access to one of your sales parsons only to mark attendance.**

To do this;

1. Login to the admin account
2. Go to the **System** section and click on the **Users**
3. Then click on the **User role tab** and then click on the **Add New** option in order to create a New User role
4. Then you can give a specific name to the User role - For this one, you can use Sales Person or something similar
5. Then Select the Table and then assign Permission

![](../.gitbook/assets/image%20%2861%29.png)

6. Now go to the Manage modules section under the System in order to assign the particular module to the new user role

7. Then click on the Modules tab and search for the particular module

8. Click on the edit button to make changes

9.  Add the created User Role to this module and save it

![](../.gitbook/assets/image%20%2866%29.png)

After creating the **User role** and Assigning the module, go back to the **User section** and click on the **User tab** in order to assign this **role** to the **employee**

10. Click on Add New to create a new user

11. Make sure the **User Level** of the employee is **Restricted Employee** user level

12. Then Select the specific user role which you have already created

13.  Set a default module and then save

![](../.gitbook/assets/image%20%2854%29.png)

Once you save the changes and logged in to the employee's account it will look like the below. The employee will only have access to mark  attendance

![](../.gitbook/assets/image%20%2856%29.png)

### How to deny access to a particular module for a user level

Denying access to one module for a particular user is easy as the same way that granting access.

**Example: You want to deny access to the training module for one of your employees**

To do this,

1. Login to the admin account
2. Go to the System section and click on the Users
3. Then click on the User role tab and then Add New option in order to create a New User role
4. Then you can give a specific name to the User role and save

![](../.gitbook/assets/image%20%2874%29.png)

 5. Now go to the Manage modules section under the System in order to assign the particular module to the new user role

6. Then click on the Modules tab and search for the particular module

8. Click on the edit button to make changes

9.  Select the created User Role to the Disallowed User Roles option and save it

After creating the User role and assigning the module now  you can go back to the **User section** and click on the **User tab** in order to assign this to the user

10. Select the employee you want to make changes and click on the edit button or Click on Add New to create a new user

11. Change the **User Level** of the employee according to your requirement \(for this example, select Employee as the user level\)

12. Then Select the specific user role which you have already created, disallowing training module

13.  Set a default module and then save

![](../.gitbook/assets/image%20%2855%29.png)

Log in as the employee and you will notice that the employee doesn't  have the Training module

![](../.gitbook/assets/image%20%2868%29.png)




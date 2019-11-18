# Vacation and Leave Management

## Leave and Vacation Management

IceHrm has once of the best leave management systems among all the HRM software. Leaves module is used to define all the elements required to manage leave application process of your company,

including:

* Leave periods
* Leave types
* Work week
* Holidays
* Leave rules

#### Leave Periods

A leave period usually a year but can be different according to company HR processes. Leave periods can’t overlap, which means if an employee applied for annual leaves in leave period for “Year 2014”, his leave balance in leave period “Year 2015” won’t get affected. This is same for all types of leaves. Also if the leave period for year 2015 is not defined, employees won’t be able to apply leaves for 2015.

#### Leave Types

Leave type tab defines types of leaves which can be applied by employees.

![IceHrm Leave Types](https://icehrm.s3.amazonaws.com/images/blog-images/leave-types.png)

#### Adding a new Leave Type

When adding a leave type you need to set following fields

![Adding a new leave type icehrm](https://icehrm.s3.amazonaws.com/images/blog-images/adding-new-leave-type.png)

| Field | Description |
| :--- | :--- |
| Admin can assign leave to employees |  If “Yes” is selected, an Admin or a Manager is able to login as an employee \(Please check switch employee concept explained in employee module\) and apply this type of leaves behalf of the employee. |
| Employees can apply for this leave type |  If “No” is selected; only an Admin or a Manager is allowed to assign this type of leave to an employee. \(An employee won’t be able to apply this type of leave\). |
| Leaves per Year |  This is the number of leaves can be applied by an employee per year \(or the current leave period\). If the leave period is less than a Year this is the number of leaves for the leave period. |
| Leave Accrue Enabled |  If this is set to “Yes”, employees won’t have all the leaves added to their leave balance at the beginning of the leave period. Instead leaves get accrued for every passing day in leave period. For an example if for a particular leave type number of leaves per period is defined as 24 and leave period \(having 12 months\) is stating from January, at the end of January an employee will be able apply for 2 leaves of this leave type \(24/12\) |
| Leave Carried Forward |  If an employee has some leave balance remaining in previous leave period, that amount will get add to the current leave period. |
| Percentage of Leaves Carried Forward |  In each year \(or period\) what percentage of remaining leaves should be carried forward. |
| Maximum Carried Forward Amount |  Maximum number of leave days which can be carried forwarded from one year to another. Set to 0 for unlimited |
| Carried Forward Leave Availability Period |  For how many days carried forward leaves are available from the start date of next leave period. |
| Proportionate Leaves on Joined Date |  Whether the available number of leaves should be calculated based on number of days employee work in a given leave period. \(e.g if an employee joined in end of June, he/she will only get half of the number of leaves specified for given leave type. |

#### Work Week

Work week defines the days that your employees are working. When an employee is applying for a leave, work week is taken into consideration. For an example if you company works only from Monday to Friday and if an employee applied for a leave for two continuous weeks including weekends, Saturdays and Sundays will NOT be counted for leave application.

In some cases, companies need to keep different workweeks for different countries. For an example if your branch in UK works a half a day on Saturday then you can add that as shown on following image. All the leave calculations of UK based employees \(employee: country field should be set to UK\) will be done according to extended workweek defined for UK.

![leave management system](https://icehrm.s3.amazonaws.com/images/blog-images/leave-workweek.png)

#### Holidays

Holidays defines the list of holidays for all leave periods. It is advised to define all holidays for all the enabled leave periods. If an employee applies for a leave which includes a holiday, the leave for holiday won’t be counted. Just like the workweek, you can have different holidays defined for different countries. In following example 2014-12-18 defined as a holiday only for UK.

![leave management system](https://icehrm.s3.amazonaws.com/images/blog-images/leaves-holidays.png)

#### Employee leaves

Employee leaves tab lists all the employee leaves. An administrator can view details of leaves and take actions on it \(Approve or Reject\). Admin should usually use this feature when the Supervisor of the person who applied the leave is not able to do it.

![hrm management system](https://icehrm.s3.amazonaws.com/images/blog-images/employee-leaves.png)

**Employee Leave Entitlement**

![Employee Leave Entitlement](https://icehrm.s3.amazonaws.com/images/blog-images/employee_leave_entitlement.png)

All the employees are allowed to check there leave entitlement. It show a summery of their leave balances for the current leave period.

| Field | Description |
| :--- | :--- |
| Available Leaves |  Number of leave remaining that you can apply during current leave period |
| Pending Leaves |  Number of leave you have applied but not approved or rejected |
| Leaves to be Accrued |  If the Leave Accrue Enabled is set for the leave type, this will show how many leave days will be added to your leave balance by end of current leave period |
| Leaves Carried Forwarded |  Leave days carried forward from previous leave periods |

#### Leave Groups

Leave groups can be used to:

1. Group a set of employees and create leave rules affecting all employees in the group.
2. Selectively allow some leave types only to a group of employees \(for an example you can assign Maternity leaves only to female employees\)

In order to do this:

* First create the leave group under “Leave Settings”-&gt;”Leave Groups”-&gt;”Edit Leave Groups”.

![leave management system](https://icehrm.s3.amazonaws.com/images/blog-images/leave_group_employees.png)

* Add employees to leave group
* Create a leave type for Maternity leave by specifying “Female employees group”. Now only employees added to that group will be able to apply for maternity leaves

## Leave Rules By Examples

Leave rules is one of the unique and advanced features of ICE Hrm. Using leave rules you can overwrite the behavior of leave types for job titles, employment statuses or even individual employees.

Following examples will show you the proper way to use leave rules

#### Example 1

 To enable all Software Engineers to apply for 20 annual leaves, you need to add a new leave rule as shown below

![icehrm - leave management system - leave rule 1](https://icehrm.s3.amazonaws.com/images/blog-images/leave-rule1.png)

#### Example 2

 Enable all Software Engineers who are permanent employees to apply for 10 medical leaves

![icehrm - leave management system - leave rule 2](https://icehrm.s3.amazonaws.com/images/blog-images/leave-rule2.png)

#### Example 3

 Do not allow contact workers to apply for casual leaves. Only administrator is allowed to apply casual leaves behalf of them with a maximum limit of 5 leaves per leave period

![icehrm - leave management system - leave rule 3](https://icehrm.s3.amazonaws.com/images/blog-images/leave-rule3.png)

## Implementing a Sample Leave Policy

**Setting Up Leave Module**

Since I've have noticed that its not a trivial task to setup the icehrm leave module initially when moving from another active leave management setup, I'm writing this to walk you through a short tutorial.

**Let's assume following:**

 1. You are moving the leave management system to icehrm, in the middle of the leave period for 2015  
 2. Some of your employees have leaves carried forwarded from 2014, which might not have been used  
 3. Your company have annual leave which can be carried forwarded to next year  
 4. There are casual leave which are accrued 1.5 per each month  
 5. Some employees have joined in 2015 and their leave entitlement should be proportionate according to joined date  


**Setting up leave periods**

First task is setting up the leave periods. If you are starting from 2015 you only need to have the 2015 leave period. But creating a leave period for 2016 also should not be an issue. Creating a leave period for 2014 will carry forward what ever the remaining leaves from 2014 to 2015. In that case you have to enter all employee leave details for 2014 manually into IceHrm. So the preferred way is to not create the previous leave period by adding all leave carried forwarded by employees using PTO \(this will be explained in another section\).

Also note that leave period can have different lengths and can be started from any month of the year.

![Setting up leave periods](https://icehrm.s3.amazonaws.com/images/blog-images/leave-periods.png)

**Setting up leave types**

1. Lets setup the leave type for annual leave which can be carried forwarded to the next year

![Setting up annual leave](https://icehrm.s3.amazonaws.com/images/blog-images/adding-annual-leave.png)

Here I've set leave carried forward to 'Yes' and carry forward percentage to 100% so all the remaining annual leave of this year will be carried forward to the next.

1. Setting up casual leave which are accrued 1.5 per each month and should not be carried forward to the next year

![Setting up casual leave](https://icehrm.s3.amazonaws.com/images/blog-images/casual-leave-setup.png)

 I have entered 18 for leave amount, this will accrue 1.5 \(18/12\) days per month since leave period length for 2015 is 12 months

**Employee leave entitlement**

Now assume we have an employee named 'Jhon Doe'. His leave entitlement \(under "Leave" =&gt; "Leave Management"\), after above leave periods and leave types are added should look like this:

![Leave entitlement for Jhon Doe](https://icehrm.s3.amazonaws.com/images/blog-images/leave-entitlement1.png)

 There are 14.39 leaves accrued for this year \(for the period 2015-01-01 to 2015-10-19\). Also it shows the number of day that will be accrued till end of the year from now, which is 3.61 days

**Adding leave balance from previous year**

The other problem you will face while adopting icehrm leave management is moving leave balance from previous year in a third party leave management system to icehrm. In order to do this you can use PTO. For an example if Jhon Doe has 3 annual leave days remaining from 2014 \(but you are not able to automatically move it to 2015 because you have not been using icehrm in 2015\), you can add a PTO days as shown below through "Admin"=&gt;"Leave Settings"=&gt;"PTO".

![PTO leave balance for Jhon Doe](https://icehrm.s3.amazonaws.com/images/blog-images/pto1.png)

After adding the leave balance you will notice that Jhon Doe has 17 annual leaves instead of 14 in his leave entitlement

Also you may add negative leave balances under PTO for current year to reflect already taken leaves by employees.

![Leave entitlement for Jhon Doe](https://icehrm.s3.amazonaws.com/images/blog-images/leave-entitlement2.png)

**Proportioning leaves respect to joined date**

Let's assume Jhon Doe joined the company in May 2015 and should not be allowed to take only a pat of leave count defined for 2015. Then for annual leave definition under "Admin"=&gt;"Leave Settings"=&gt;"Leave Types" you can edit Annual Leave and make `"Proportionate leaves on Joined Date" = "Yes"`

If this is set then Jhon Doe will only be entitled for 18 \* \(8/12\) annual leaves for the year given he has joined on 1st of May 2015

### Employee Leave Periods

With IceHrm now you can have employee leave periods which are started from joined date of the employee. For an example assume you  have an employee joining the company on 20th March, 2019. This employee should get 12 days of annual leave for the year. The leave balance should be updated again after one year from the joined date, which is 20th March 2020.

In-order to implement this you need Employee Leave Periods



## Leave Management FAQ

### Leave/Paid Time Off Management

**How to allocate 160 hours instead of days in leave management module?**

When adding leave entitlement you should primarily use leave types. Since you are getting 160 hours a year you can create a leave type called Annual leave and add 20 \(160/8\) days as leave amount for that leave type. IceHrm assumes a 8 hour work day. So when you do that you can apply for a leave for 1 day or 1 hour. If you apply for a 1 day leave your leave entitlement available leave count will become 19. If you apply for one hour it'll take away 0.125 from your leave entitlement.

**How to allocate different amounts of leave to different employees or categories?**

Let's say some employees have only 150 hours of paid time off. \(For an example all "Marketing Managers"\). To implement this you can go to add a leave rule for Marketing Managers for annual leave with leave amount of only 18.75 days \(150/8\). Leave rules are not bound to any leave period, so the leave rules that you define will be applied to all the leave periods.

**How to compensate an employee with Paid time off?**

Assume that an employee worked on a holiday due to some urgent issue. You need to compensate him/her with an additional day off. In that case you can use "Paid Time Off" tab to add an additional leave to the employee. Paid time off also used to add leaves carried forwarded from previous years where you have not been using icehrm. If you want to remove some leave from an employee you can add minus PTO also.

**I've not been using IceHrm during 2015, But when configuring leave balances for 2016 different employees are having different leave balances carried forwarded from 2015. How to handle this?**

You should add these as PTO amounts for leave period 2016 under "Paid Tome Off" tab. You will have to add one record for each employee. This is a one time setup, from 2017 you can use automatic leave carry forwarding.


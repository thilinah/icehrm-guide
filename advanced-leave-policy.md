# Implementing an Advanced Leave Policy with IceHrm

## Introduction

Icehrm has tools to implement complex leave policies. So most of the companies are covered by it. For an example, due to government regulations of some European countries, the leave policies of companies has become a bit too complicated, but still, IceHrm can handle those.

This section describes the process of implementing an advanced leave policy which involves multiple leave groups and rules in multiple countries.

## Example Leave Policy

Let's think of a company operating in **Germany** and **Singapore**. For the company in Singapore, the leave policy is simple. But for the German company, it's a bit complicated with additional leave types.

### Leave Types in Singapore

Singapore company has three leave types.

#### Annual Leave

Every employee gets 14 days off per year. Remaining leave days can be carried forward indefinitely. For an example, if you were an employee since 2016 and took 10, 13 annual leave days respectively in 2016 and 2017, by 2018 you will have 19 annual leave days. 14 from 2018 and 5 days from previous years.

##### Creating Leave Type for Annual Leave

1. Login to IceHrm installation as an admin
2. Goto Admin -> Leave Settings
3. If you have created a fresh installation, delete existing leave types
4. Add a new leave type (name it as "Annual Leave")
5. Set *Leaves per Leave Period* to 14
6. Set *Admin can assign leave to employees* to Yes
7. Set *Employees can apply for this leave type* to Yes
8. Set *Leave Carried Forward* to Yes (As you need to carry forward remaining leave to next period)
9. Set *Percentage of Leave Carried Forward* to 100 as you need to carry forward 100% of the remaining leave
10. Set *Maximum Carried Forward Amount* to 0. Setting this to 0 will remove the limitation on carried forward leave days
11. Set *Carried Forward Leave Availability Period* to *No Limit*. This will allow employees to carry forward *Annual Leave* indefinitely
12. Set *Send Notification Emails* to Yes. This will send out emails to approvers when a leave application is submitted
13. Select a *Leave Color*. This will be used to show leave details on leave calendar

![](/assets/singapore-annual-leave-icehrm.png)


#### Casual Leave

Each employee gets 7 days per year. Can not be carried forward

##### Creating Leave Type for Casual Leave

1. Add a new leave type for Casual Leave. The settings can be seen in the screenshot
2. Note that you should set *Leave Carried Forward* to No

![](/assets/singapore-casual-leave-icehrm.png)



#### Maternity Leave

A working mother can take this leave 4 weeks before expected date of childbirth. Up to 48 leave days can be taken.

##### Creating Leave Type for Maternity Leave

1. Add a new leave type for Maternity Leave. The settings can be seen in the screenshot
2. For maternity leave, we do not need to enable accrue or carry forward.

![](/assets/singapore-materlity-leave-icehrm.png)

#### Initial Test for Leave Settings

##### Adding test employees

For testing, we have added 5 employees.

![](/assets/leave-employee-list-icehrm.png)

As you can see some employees are based in Singapore and some are based in Germany.

##### Initial Test for Leave Balances

For testing the leave balance of each of them you can use the *Employee Leave Entitlement* report. Go to *Admin Reports* => *Reports* to generate it.

![](/assets/employee-leave-entitlement-report.png)

Here all the employees are entitled to have all the leave types. Also, the leave numbers are as expected.

![](/assets/leave-list-1.png)

#### Adding Leave Types by Country

As you can see there is a problem with above leave entitlement report. The leave types we have defined are entitled to all the employees, even the ones based in Germany.

In order to, correct the problem, you need to use leave groups. Leave groups is a way to allow only certain employees the ability to apply for certain types of leave.

##### Defining a Leave Group for Singapore

Define a Leave Group for Singapore under *Admin => Leave Settings => Leave Groups => Edit Leave Groups*

![](/assets/define-singapore-leave-group.png)

Then add Singapore employees to this group under *Admin => Leave Settings => Leave Groups => Leave Group Employees*

![](/assets/add-singapore-employees-to-leave-group.png)

As the next step set *Leave Group* of the *Annual Leave* to *Singapore*

![](/assets/annual-leave-set-leave-group.png)

Repeat this for other two Leave Types as well.

![](/assets/singapore-leave-types-setting-leave-group.png)

##### Second Test for Leave Balances

Now generate the  *Employee Leave Entitlement* report again. Now you will see that only Singapore based employees are entitled for Leave Types we just created.

![](/assets/leave-list-2.png)

#### Allow Maternity Leave only to Working Mothers

We still have a problem with above leave entitlement for Singapore. Only working mothers should be allowed to apply for Maternity Leave. This can be achieved by adding a new *Leave Group*.

1. Add a Leave Group Named "Singapore Working Mothers"

![](/assets/leave-group-sg-working-mothers.png)

2. Add Nicole Smith to Leave Group "Singapore Working Mothers"

![](/assets/add-employees-to-sg-working-mothers.png)

3. Go to Leave Type tab and change the Leave Group for *Maternity Leave* to "Singapore Working Mothers"

![](/assets/leave-type-list-sg-working-mothers.png)
 
4. Under *Employees => Employees* switch to *Nicole Smith*. This will let you use the application as *Nicole Smith*

![](/assets/employee-list-switch-employee.png)

5. Open *Leave => Leave Management => Leave Entitlement*. This will show all three leave types

![](/assets/leave-entitlement-nicole-smith.png)

#### Third Test for Leave Balances

Now generate the  *Employee Leave Entitlement* report again. Now you will see that Nicole Smith is entitled to Maternity Leave. This is because of *Maternity Leave* is under Leave Group *Singapore Working Mothers* and only *Nicole Smith* is in that Leave Group.

![](/assets/leave-list-3.png)



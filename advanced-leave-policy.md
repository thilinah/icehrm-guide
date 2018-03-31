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

![](/assets/singapore-annual-leave-type.png)


#### Casual Leave

Each employee gets 7 days per year. Can not be carried forward

##### Creating Leave Type for Casual Leave

1. Add a new leave type for Casual Leave. The settings can be seen in the screenshot
2. Note that you should set *Leave Carried Forward* to No

![](/assets/singapore-casual-leave-icehrm.png)



#### Maternity Leave

A working mother can take this leave 4 weeks before expected date of childbirth. Up to 48 leave days can be taken.

### Implementing Leave Policy for Singapore








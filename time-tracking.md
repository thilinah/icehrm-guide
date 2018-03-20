# Projects

Projects module is used to add clients, projects and assign projects to employees

Each and every project is attached to a client. Because of that, ICE Hrm allow adding 
clients with basic information. Once clients are added, you can start creating project 
for these clients. The clients section represent both external and internal clients of the company. 
That way you can attach each and every project to a client.

###Employee Projects
Under employee projects tab you can assign projects to employees. You need to add projects to employees to enable them to add time against 
these projects in time-sheets.

# Time Sheets

Time sheet is a document which indicates the hours an employee has worked, generally separated by days of the week.

In IceHrm employees can edit time sheets under Time Management -> Time Sheets. Current week time sheet is automatically
created and time sheets for past weeks can be created by clicking "Create Previous Timesheet" action button of a time sheet.

By clicking edit time sheet button you can start adding time entries to the time sheet. Time entries can be associated with
projects. These projects are created under Admin -> Projects/Client Setup module. 


#### Allow employees add time for only project assigned to them

By default all employees are allowed to add time entries for all the projects defined. But you can assign projects to employees under "Employee Projects"
tab of the "Projects/Client Setup" module and change the setting "Projects: Make All Projects Available to Employees"
to "No" in order to let employees add time entries for projects assigned to them.

#### Prevent employees from adding time sheet entries during days they have not marked Attendance

Change the setting "Attendance: Time-sheet Cross Check" to "Yes" in order to prevent employees from adding time sheet
entries for time periods they were not in the office.

# Attendance

Attendance tracking is one of the most used functions of IceHrm. When tracking attendance you can either let your
employees enter the time when recording attendance or configure it to use server time.

Also attendance module can be used to track people who are already punched in.

#### Attendance Tracking with User Time

Under <code>System -> Settings</code> set <code>Attendance: Use Department Time Zone</code> to No. This will let yours select the time when
punching in and out.

![Punch in with user time](https://icehrm.s3.amazonaws.com/images/blog-images/attendance_punch_in1.png)

#### Attendance Tracking with Server Time

Every employee should be attached to a department. These departments are defined under <code>Admin -> Company Structure</code> and
you should have a time zone for each department defined. When an employee attached to a department records attendance
icehrm uses the time in departments timezone to generate the correct time. All you need to do is setting the proper
time zone and set <code>Attendance: Use Department Time Zone</code> to Yes.

![Punch in with server time](https://icehrm.s3.amazonaws.com/images/blog-images/attendance_punch_in1.png)

# Difference in Attendance and Time Sheets

#### Attendance

Attendance represent the time you were in office. It do not store what kind of a work you've been doing or 
on which project you have been working on. Also attendance can not be approved. 

- Admins can monitor attendance via <code>Employees->Monitor attendance</code>
- Employees can register attendance via <code>Time Management -> Attendance</code>

#### Time Sheets

Time sheets and time entries represent actual work you have been doing. A time sheet which represent one week
can have multiple time entries. Once an employee completed a time sheet they can send it to direct 
supervisor for approval.

Timesheets can be accessed via <code>Time Management -> Timesheets</code>

You can export a report on daily time sheet details using "Employee Time Tracking" report under 
<code>Reports -> Reports</code> module


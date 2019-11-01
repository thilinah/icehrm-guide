# Attendance Module

IceHrm has several different tools for managing and recording employee time.

## Attendance Tracking

Attendance represents the time you were in office.

### Recoding Attendance

Employees can record attendance via Time Management -&gt; Attendance. While recording attendance they can select the time they arrive and leave the office.

When tracking attendance you can either let your employees enter the time when recording attendance or configure it to use server time.

#### Attendance Tracking with User Time

Under `System -> Settings` set `Attendance: Use Department Time Zone` to No. This will let yours select the time when punching in and out.

![Punch in with user time](https://icehrm.s3.amazonaws.com/images/blog-images/attendance_punch_in1.png)

#### Attendance Tracking with Server Time

Every employee should be attached to a department. These departments are defined under `Admin -> Company Structure` and you should have a time zone for each department defined. When an employee attached to a department records attendance icehrm uses the time in departments timezone to generate the correct time. All you need to do is set the proper time zone and set `Attendance: Use Department Time Zone` to Yes.

![Punch in with server time](https://icehrm.s3.amazonaws.com/images/blog-images/attendance_punch_in2.png)

### Monitoring Attendance

Attendance details of employees can be viewed/edited via `Employees => Monitor attendance` module. Admin users can view all employee attendance while Managers can view attendance data for subordinates \(direct reports\).

### Uploading Attendance Data

You can upload attendance data from your attendance recording devices instead of allowing employees to punch in/out using icehrm.

1. Download the sample attendance file from [here](https://s3.amazonaws.com/icehrm/images/blog-files/attendance_sample_import.csv)
2. Then add your attendance data in the same format.
3. Goto `System -> Data -> Data Import Files` tab
4. Create a new data import as shown below. Use a descriptive name ![](../.gitbook/assets/data-import-create-attendance.png)
5. Save and from the "data import file list" click process button

   ![](../.gitbook/assets/data-import-attendance-process.png)

### Attendance with photo proof

![](https://cdn-images-1.medium.com/max/1600/1*k7LWas2GYxe0gFhfOSgsKw.png)

This feature lets your employees take a photo of him/her at the office or at any place you want them to be via the webcam when punching in or out. This help to make sure the employee is at his/her desk when adding attendance entry.

[Read more about this here](https://medium.com/@icehrm/how-to-prevent-buddy-punching-and-time-theft-73eb4c83aa29)

## Attendance Sheets

Attendance Sheets which can be accessed via `Time Management => Attendance Sheets` is a way for employees to group attendance details for the whole week and send it for approval to the supervisor. This feature is useful when you pay employees based on attendance. In such cases, there should be an approval process in place.

![](../.gitbook/assets/attendance-sheets.png)


# Training Module

Training module in IceHrm can be used to manage process of providing internal trainings for employees.

In training module we have courses, training sessions and training subscription management.

1. Admins/Managers can define courses
2. Admins/Managers can use courses to create training sessions
3. Admin can assign courses to employees or employees can subscribe
4. Employees can mark training sessions as attended and attach a proof of completion if required
5. Admins/Managers can approve that the training session is completed by the employee

## Adding a new Course

| Field | Description |
| :--- | :--- |
| `Code` |  Each course should have a code |
| `Name` |  The course name |
| `Coordinator` |  The employee of the company who is responsible for coordinating the course. In some cases coordinator could be the trainer/instructor as well |
| `Trainer` |  Name of the person who conduct the course |
| `Payment Type` |  Whether the course is sponsored by the company or paid by the employee |

### Most of the other fields are self-descriptive

## Adding a new Training Session

| Field | Description |
| :--- | :--- |
| `Name` |  Name of the training session |
| `Course` |  Select the trainign course |
| `Scheduled Time` |  When this training session is scheduled |
| `Assignment Due Date` |  If the training session has an associated assignment, the due date for that |
| `Delivery Method` |  Whether the training session is delivered in a class room, online or its a sel study session |
| `Attendance Type` |  - Assign = Only admins/mangers can assign the session to employees - Sign Up = Session is open for employees to sign up |
| `Attachment` |  An attachment with other resources for the session |
| `Training Certificate Required` |  If Yes, employees have to attach a proof of completion \(such as certificate\) before marking the training session as completed |

## Subscribing to a Training Session

1. An employee can subscribe to a training session via `Training => Training` module.
2. Go to "All Training Sessions" tab
3. Click on subscribe button

![](https://icehrm.s3.amazonaws.com/images/blog-images/employee_training_sessions.png)

### Attendance Type

Employees can only subscribe to training sessions having Attendance Type set to "Sign Up"

## Completing a Training Session

Once an employee participated in a training session he/she can mark the training as completed via`Training=>Training=>My Training Sessions`tab. Once this is done a notification will be sent to the supervisor to approve the training session.

### Proof of Completion

If the training session requires proof of completion, an employee has to edit the training session under "My Training Sessions" tab and attach a proof of completion before submitting it for approval

## Approving a Training Session

Once an employee mark a training session as completed, the supervisor will receive a notification to approve it.

![Approve training session](https://icehrm.s3.amazonaws.com/images/blog-images/approve_training_session.png)

If all the things are in order, the supervisor can approve the training session via `Training=>Training=>Training Sessions of Direct Reports` tab


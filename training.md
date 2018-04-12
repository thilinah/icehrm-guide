# Setting Up Training Module

Training module in IceHrm can be used to manage process of providing internal trainings for employees.

In training module we have courses, training sessions and training subscription management.

 1. Admins/Managers can define courses
 2. Admins/Managers can use courses to create training sessions
 3. Admin can assign courses to employees or employees can subscribe
 4. Employees can mark training sessions as attended and attach a proof of completion if required
 5. Admins/Managers can approve that the training session is completed by the employee
 
 
#### Adding a new Course

<div class="mobile-side-scroller">
<table>
  <thead>
    <tr>
      <th>Field</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><p><code>Code</code></p></td>
      <td><p>
        
        Each course should have a code

      </p></td>
    </tr>
    <tr>
      <td><p><code>Name</code></p></td>
      <td><p>

        The course name

      </p></td>
    </tr>
    <tr>
      <td><p><code>Coordinator</code></p></td>
      <td><p>

        The employee of the company who is responsible for coordinating the course.
        In some cases coordinator could be the trainer/instructor as well

      </p></td>
    </tr>
    <tr>
      <td><p><code>Trainer</code></p></td>
      <td><p>

        Name of the person who conduct the course

      </p></td>
    </tr>
    <tr>
      <td><p><code>Payment Type</code></p></td>
      <td><p>

        Whether the course is sponsored by the company or paid by the employee

      </p></td>
    </tr>
  </tbody>
</table>
</div>

<div class="note info">
  <h5>Most of the other fields are self descriptive</h5>
  <p></p>
</div>

#### Adding a new Training Session

<div class="mobile-side-scroller">
<table>
  <thead>
    <tr>
      <th>Field</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><p><code>Name</code></p></td>
      <td><p>
        
        Name of the training session

      </p></td>
    </tr>
    <tr>
      <td><p><code>Course</code></p></td>
      <td><p>

        Select the trainign course

      </p></td>
    </tr>
    <tr>
      <td><p><code>Scheduled Time</code></p></td>
      <td><p>

        When this training session is scheduled

      </p></td>
    </tr>
    <tr>
      <td><p><code>Assignment Due Date</code></p></td>
      <td><p>

        If the training session has an associated assignment, the due date for that

      </p></td>
    </tr>
    <tr>
      <td><p><code>Delivery Method</code></p></td>
      <td><p>

        Whether the training session is delivered in a class room, online or its a sel study session

      </p></td>
    </tr>
    <tr>
      <td><p><code>Attendance Type</code></p></td>
      <td><p>

        - Assign = Only admins/mangers can assign the session to employees
        - Sign Up = Session is open for employees to sign up

      </p></td>
    </tr>
    <tr>
      <td><p><code>Attachment</code></p></td>
       <td><p>
 
         An attachment with other resources for the session
 
       </p></td>
     </tr>
     <tr>
      <td><p><code>Training Certificate Required</code></p></td>
       <td><p>
 
         If Yes, employees have to attach a proof of completion (such as certificate) before marking the training session as completed
 
       </p></td>
     </tr>
  </tbody>
</table>
</div>


#### Subscribing to a Training Session

1. An employee can subscribe to a training session via <code>Training => Training</code> module.
2. Go to "All Training Sessions" tab
3. Click on subscribe button

![](https://icehrm.s3.amazonaws.com/images/blog-images/employee_training_sessions.png)


<div class="note warning">
  <h5>Attendance Type</h5>
  <p>Employees can only subscribe to training sessions having Attendance Type set to "Sign Up"</p>
</div>

#### Completing a Training Session

Once an employee participated in a training session he/she can mark the training as completed via 
<code>Training=>Training=>My Training Sessions</code> tab. Once this is done a notification will be sent
to the supervisor to approve the training session.

<div class="note info">
  <h5>Proof of Completion</h5>
  <p>If the training session requires a proof of completion, employee has to edit the training session under "My Training Sessions" tab
  and attach a proof of completion before submitting it for approval</p>
</div>
 
 
#### Approving a Training Session
 
Once an employee mark a training session as completed, the supervisor will receive a notification to approve it.

![Approve training session](https://icehrm.s3.amazonaws.com/images/blog-images/approve_training_session.png)

If all the things are in order, the supervisor can approve the training session via <code>Training=>Training=>Training Sessions of Direct Reports</code> tab


# Recruitment
Recruitment module can be used to:
 
- Post jobs
- Let candidates apply for these jobs
- Schedule interviews
- Track candidate progress with notes
- Share job links with linkedIn, facebook, twitter and google+ directly from icehrm

##Recruitment Setup

Recruitment setup menu is available under "Recruitment"=>"Recruitment Setup". Here you can add/edit Employment Types,
Experience levels, Job Functions, Education Levels and Benefits. All these information will be used when posting a job.

![Recruitment Setup](https://icehrm.s3.amazonaws.com/images/blog-images/recruitment-setup.png)

##Posting a Job

Jobs can be posted via "Recruitment"=>"Job Positions". Following table will list out main fields used to create job postings

<div class="mobile-side-scroller">
<table>
  <thead>
    <tr>
      <th>Fields</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><p><code>Job Code</code></p></td>
      <td><p>
        
        A unique code to identify the job position. Url for applying the job position will contain this code.

      </p></td>
    </tr>
    <tr>
      <td><p><code>Job Title</code></p></td>
      <td><p>

        The job title

      </p></td>
    </tr>
    <tr>
      <td><p><code>Short Description</code></p></td>
      <td><p>

        A short description about the job position. This will be displayed when listing company jobs.
        The public url for companies open positions is,<br/>
        http://icehrm_url/entry.php?g=admin&n=candidates

      </p></td>
    </tr>
    <tr>
      <td><p><code>Description</code></p></td>
      <td><p>

        Full description of the job position

      </p></td>
    </tr>
    <tr>
      <td><p><code>Show Salary</code></p></td>
      <td><p>

        Whether you want to show the salary range for this job position

      </p></td>
    </tr>
    <tr>
      <td><p><code>Keywords</code></p></td>
      <td><p>

        Keywords for improving search and SEO

      </p></td>
    </tr>
    <tr>
      <td><p><code>Status</code></p></td>
      <td><p>

        Only active jobs will get listed

      </p></td>
    </tr>
    <tr>
      <td><p><code>Image</code></p></td>
      <td><p>

        Attach an image if you want to show an image with job listing

      </p></td>
    </tr>
  </tbody>
</table>
</div>


###Job Position - Display Type

You should select a display type when posting a job position. This section details the for display types supported y icehrm

<div class="mobile-side-scroller">
<table>
  <thead>
    <tr>
      <th>Fields</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><p><code>Text Only</code></p></td>
      <td><p>
        
        Only text will be displayed<br/>
        e.g:
        <a href="http://apps.gamonoid.com/icehrm-hosted/entry.php?g=admin&n=candidates&ref=JC002">Text ad</a>


      </p></td>
    </tr>
    <tr>
      <td><p><code>Image Only</code></p></td>
      <td><p>
        
        Only an image will be displayed. The image for the ad should be provided in <code>Image</code> field when creating job position<br/>
        e.g:
        <a href="http://apps.gamonoid.com/icehrm-hosted/entry.php?g=admin&n=candidates&ref=J0003">Image only ad</a>

      </p></td>
    </tr>
    <tr>
      <td><p><code>Image and Full Text</code></p></td>
      <td><p>
        
        Use this display type when you want to show an image for the job position with a full description and details such as salary,
        requirements and benefits.

      </p></td>
    </tr>
    <tr>
      <td><p><code>Image and Other Details</code></p></td>
      <td><p>
        
        Use this display type when you want to show an image for the job position only with a minimum set of meta data about the job
        position such as salary, employment type, experience, job functions and closing date.

      </p></td>
    </tr>
  </tbody>
</table>
</div>


##Sharing your job position on social media and using direct links

You can share created job positions on Google+, Facebook, Twitter and LinkedIn directly from IceHrm using
social links on job positions module. Also you can get a direct link to the job position which you can send via
email or any other media by clicking on "Job Link" icon.

![Recruitment Job Position Sharing](https://icehrm.s3.amazonaws.com/images/blog-images/recruitment-share.png)


# Candidates
 
- Store candidate details
- Receive job applications from candidates via job postings
- Schedule interviews
- Track candidate progress with notes


After creating a job position you can list all the candidates who have applied for the job position via 
"Recruitment"=>"Candidates" module. It should list all the candidates who have applied for your jobs.

![Candidate Details](https://icehrm.s3.amazonaws.com/images/blog-images/candidates.png)

Here you can schedule interviews and add notes related to the candidate. Notes could be a details about a telephone conversation or
candidates expectations.

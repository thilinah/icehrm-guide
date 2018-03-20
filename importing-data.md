# Importing Data

You can import data into icehrm using CSV files. By default we support importing basic employee details and attendance data.

### Preparing Employee Data for Upload

1. Download sample data file <a href="https://s3.amazonaws.com/icehrm/images/blog-files/employees.csv" target="_blank">here</a>
2. The file has following columns which matches with default employee data file definition

    - employee_id = The id of the employee (this id should be unique, if the employee with same id exists in the system then employee details will be replaced)
    - first_name, middle_name, last_name = Employee names
    - address1,address2,home_phone,mobile_phone,work_email = Employee contact details
    - gender = Male or Female
    - marital_status = Married, Single, Divorced, Widowed, Other
    - birthday = MM/DD/YY format
    - Nationality/nationality = Any nationality defined in System -> Manage Meta Data -> Nationality
    - Ethnicity/ethnicity = Any ethnicity defined under System -> Manage Meta Data -> Ethnicity
    - EmergencyContact/name = Emergency contact name
    - EmergencyContact/relationship = Emergency contact relationship
    - EmergencyContact/home_phone = Emergency contact phone
    - ssn_num = Social security number or ID number
    - job_title = Job Title (this should be predefined in Admin -> Job Details Setup -> Job Titles)
    - employment_status = Employment Status (should be predefined in Admin -> Job Details Setup -> Employment Status)
    - joined_date = Joined date in MM/DD/YY format
    - department = Company Structure this employee is attached to (predefined in Admin -> Company Structure)


### Importing Basic Employee Data

1. Login as Admin and Navigate to System -> Data Import Files and create a new entry with file created in previous step
![Create data import file](https://s3.amazonaws.com/icehrm/images/blog-images/create_employee_data_import.png)
2. Once the entry is created click on "Process"
![Process data import file](https://s3.amazonaws.com/icehrm/images/blog-images/process_employee_data_import.png)

### Creating Data Importers

You can create data importers for importing custom fields or any other additional fields into employees.

### Creating a Data Importer for Updating Supervisors

Here is an example for creating a Data Importer for updating supervisors and some custom fields

1. Login as Admin and Navigate to System -> Data Importers
2. Create a new Data Importer named "Supervisor and Custom Field Importer" and Data Type should be "EmployeeDataImporter"
![data_import_create_custom_importer](https://s3.amazonaws.com/icehrm/images/blog-images/data_import_create_custom_importer.png)
3. Each importer should have one ID column. For employees the id column should be employee_id. Here is how you can add this unique id column.
4. Edit the newly created data importer and add a new column named employee_id. Note that the value "is key field" is true
![Process data import file](https://s3.amazonaws.com/icehrm/images/blog-images/data_import_add_employee_id.png)
5. Then add the column for Supervisor. We call this type of a column a reference type column because it depends on another row in a different or same entity
![Process data import file](https://s3.amazonaws.com/icehrm/images/blog-images/data_import_supervisor_column.png)
6. Note that we have set "is key field" to true.
7. Then you can add a sample custom field to the employees (via System -> Field Names Setup -> Employee Custom Fields).
8. For now we will add a custom field named Contract End Date
![Add custom field](https://s3.amazonaws.com/icehrm/images/blog-images/data_import_add_custom_field.png)
9. Now you can add a column to the existing data importer for importing data for "Contract End Date"
![Process data import file](https://s3.amazonaws.com/icehrm/images/blog-images/data_import_add_contract_end_date.png)
10. Now you can create the csv file for importing supervisor and contract end date for employees. In the csv file there should be 
three columns defined fo Employee Id, Supervisor and Contract End Date. The supervisor field should hold the employee_id of the
supervisor.
11. Download the file already created csv file for this step from <a href="https://s3.amazonaws.com/icehrm/images/blog-files/employee_supervisors.csv" target="_blank">here</a>
12. Crate a "Data Import File" for uploading the new file
![Add custom field](https://s3.amazonaws.com/icehrm/images/blog-images/data_import_employee_supervisors_file.png)
13. Process the file








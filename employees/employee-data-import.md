# Employee Data Import

You can import data into icehrm using CSV files. By default, we support importing basic employee details and attendance data. This feature should be used only during the initial setup.

## Preparing Employee Data for Upload

1. Download sample data file [here](https://s3.amazonaws.com/icehrm/images/blog-files/employees.csv?v=2)
2. The file has following columns which matches with default employee data file definition
   * employee\_id = The id of the employee \(this id should be unique, if the employee with same id exists in the system then employee details will be replaced\)
   * first\_name, middle\_name, last\_name = Employee names
   * address1,address2,home\_phone,mobile\_phone,work\_email = Employee contact details
   * gender = Male or Female
   * marital\_status = Married, Single, Divorced, Widowed, Other
   * birthday = MM/DD/YY format
   * Nationality/nationality = Any nationality defined in System -&gt; Manage Meta Data -&gt; Nationality
   * Ethnicity/ethnicity = Any ethnicity defined under System -&gt; Manage Meta Data -&gt; Ethnicity
   * EmergencyContact/name = Emergency contact name
   * EmergencyContact/relationship = Emergency contact relationship
   * EmergencyContact/home\_phone = Emergency contact phone
   * ssn\_num = Social security number or ID number
   * job\_title = Job Title \(this should be predefined in Admin -&gt; Job Details Setup -&gt; Job Titles\)
   * employment\_status = Employment Status \(should be predefined in Admin -&gt; Job Details Setup -&gt; Employment Status\)
   * joined\_date = Joined date in MM/DD/YY format
   * department = Company Structure this employee is attached to \(predefined in Admin -&gt; Company Structure\)

## Importing Basic Employee Data

1. Login as Admin and Navigate to System -&gt; Data Import Files and create a new entry with the file created in the previous step

   ![Create data import file](https://s3.amazonaws.com/icehrm/images/blog-images/create_employee_data_import.png)

2. Once the entry is created click on "Process"

   ![Process data import file](https://s3.amazonaws.com/icehrm/images/blog-images/process_employee_data_import.png)

## Creating Data Importers

You can create data importers for importing custom fields or any other additional fields into employees.

## Creating a Data Importer for Updating Supervisors

Here is an example of creating a Data Importer for updating supervisors and some custom fields

1. Login as Admin and Navigate to System -&gt; Data Importers
2. Create a new Data Importer named "Supervisor and Custom Field Importer" and Data Type should be "EmployeeDataImporter"

   ![data\_import\_create\_custom\_importer](https://s3.amazonaws.com/icehrm/images/blog-images/data_import_create_custom_importer.png)

3. Each importer should have one ID column. For employees, the id column should be employee\_id. Here is how you can add this unique id column.
4. Edit the newly created data importer and add a new column named employee\_id. Note that the value "is ID field" is true

   ![Process data import file](https://s3.amazonaws.com/icehrm/images/blog-images/data_import_add_employee_id.png)

5. Then add the column for Supervisor. We call this type of a column a reference type column because it depends on another row in a different or same entity

   ![Process data import file](https://s3.amazonaws.com/icehrm/images/blog-images/data_import_supervisor_column.png)

6. Note that we have set "is key field" to true.
7. Then you can add a sample custom field to the employees \(via System -&gt; Field Names Setup -&gt; Employee Custom Fields\).
8. For now, we will add a custom field named Contract End Date

   ![Add custom field](https://s3.amazonaws.com/icehrm/images/blog-images/data_import_add_custom_field.png)

9. Now you can add a column to the existing data importer for importing data for "Contract End Date"

   ![Process data import file](https://s3.amazonaws.com/icehrm/images/blog-images/data_import_add_contract_end_date.png)

10. Now you can create the CSV file for importing supervisor and contract end date for employees. In the CSV file, there should be three columns defined for Employee Id, Supervisor and Contract End Date. The supervisor field should hold the employee\_id of the

    supervisor.

11. Download the file already created CSV file for this step from [here](https://s3.amazonaws.com/icehrm/images/blog-files/employee_supervisors.csv)
12. Crate a "Data Import File" for uploading the new file

    ![Add custom field](https://s3.amazonaws.com/icehrm/images/blog-images/data_import_employee_supervisors_file.png)

13. Process the file


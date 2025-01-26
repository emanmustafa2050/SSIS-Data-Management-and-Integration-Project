# SSIS-Data-Management-and-Integration-Project-SSIS
Project Overview

This project demonstrates the use of SQL Server Integration Services (SSIS) to design and implement various ETL (Extract, Transform, Load) workflows. 
The objective was to transfer, process, and manage data between an existing database ([ITI DB]) and a newly created database ([Test DB]), as well as generate and manipulate files for reporting purposes.

The project covers essential data integration and transformation tasks, showcasing practical applications of SSIS tools and components.

Features and Objectives: 

1. Transfer Department Data
 
     Description: Transfer department data from [ITI DB] to [Test DB].

     Steps:
  
     - Truncate the department table in [Test DB] before data transfer.

     - Use the SSIS wizard to design a package for this operation.

     Tools/Components Used:

     - Execute SQL Task Component

     - Data Flow Task

2. Export Student Data to a Delimited File

      Description: Export selected student data (St_id, St_Fname, St_lname, St_address) from [ITI DB] to a delimited file (Student.txt) with column names in the first row.

      Steps:

      - Configure a Flat File Destination.

      - Set column headers as the first row.

     Tools/Components Used:

     - Flat File Destination

     - Data Flow Task

3. Student Data Transfer and Transformation

      Description: Transfer and transform student data from [ITI DB] to [Test DB].

      Steps:

      - Check if the Student table exists in [Test DB]. If it does, delete all data.

      - Merge first and last names into a single field (Full name) using the Derived Column Component.

      - Perform a full backup of [Test DB].

      - Display an error message box if any error occurs during the process.

     Tools/Components Used:

     - Execute SQL Task

     - Derived Column Component

     - Script Task (for error message box)

4. Split and Sort Course Data

       Description: Split course data from [ITI DB] into three separate files based on course duration.

      Steps:

      - Extract course data with the topic name.

      - Sort course data by Crs_name in descending order.

      - Convert Crs_name to lowercase.

      - Split course data into three files:

      - File1.txt: Courses with duration < 30 hours.

      - File2.txt: Courses with duration = 30 hours.

      - File3.txt: Courses with duration > 30 hours.

     Tools/Components Used:

     - Sort Component

     - Character Map Component

     - Conditional Split Component

     - Flat File Destination

5. Merge and Combine Files

        Description: Merge File1.txt and File2.txt into a single file, sorted by Crs_name.

        Steps:

        - Use the Merge Component to combine the files.

        - Sort the combined data by Crs_name.

        - Optionally, use the Union Component for additional integration tasks.

       Tools/Components Used:

       - Union Component

Tools and Technologies Used : 

   - SSIS (SQL Server Integration Services)

   - SQL Server Management Studio (SSMS)

   - Flat File Source/Destination

   - Execute SQL Task

   - Derived Column Component

   - Sort Component

   - Character Map Component

   - Conditional Split Component

   - Union Component

How to Run the Project :

   - Attach the ITI database to your SQL Server.

   - Create a new database named Test in SQL Server.

   - Open the SSIS project in SQL Server Data Tools (SSDT).

   - Execute the packages in the following order:

   - Transfer_Department_Data

   - Export_Student_To_File

   - Student_Data_Transfer

   - Split_And_Sort_Course_Data

   - Verify the results in [Test DB] and the generated files.

Challenges Faced:

   - Managing data type mismatches during the Merge process.

   - Ensuring metadata consistency across components.

   - Handling errors effectively with meaningful messages.

Future Improvements:

    - Automate database creation and table structure setup.

    - Add more advanced transformations for real-world scenarios.

    - Implement logging and monitoring features for better error tracking.

<details> 
	 <summary> SQL (Structured Query Language) </summary>
	
1. is a programming language used to communicate with databases.
2. is used to access and manipulate the data in a database.
3. SQL is an ANSI (American national standard institute)
4. SQL is not case-sensitive
   
</details>

<details>
		 <summary> Database </summary>
	
# Database
1. is a collection of organized data that may be structured, unstrutured and semi-structured , stored on computer systems.
2. It can be managed by #DBMS (database management system), a software to manage the data.
3. The primary goal of a database is to store a huge amount of data.
4. Data present in the database can be easily accessed, updated, deleted using SQL (structured query language)
5. There are different types of databases to handle different data and use-cases. 
6. Relational Database and Non- relational Database
   
</details>

# DBMS:  
1. is a software that manages a database by storing, retrieving, and manipulating the data from database. # Ex: oracle, MySQL...Etc. are some DBMS tools.

# Databases Challenges
1. Scalability : as data increases data storage and processing demands increases
2. Performance Optimization:
3. Data Security:
4. Data Consistency and Integrity:
5. Data Quality:
6. Backup and Disaster Recovery:
7. Data Governance and Compliance:

<details>
	<summary>Datawarehouse</summary>
	
# Datawarehouse (think first , load later)
1. is a system that gathers raw data from different source into a single, central, consistent data store to perform data analysis.
2. A data warehouse system enables an organization to run powerful analytics on huge volumes (petabytes) of historical data in ways that a standard database cannot.
3. Data warehouse maintain both current + historic data.
4. Traditionally, data warehouse was hosted on-premises. Now-a-days DW is hosted on cloud too.
5. DW is structured using predefined schema.
6. #note : databases is used for transactional processing and datawareHouse is used for analytical processing.
7. Data warehouses often use a **#dimensional** model, organizing data into fact tables (containing business facts or metrics) and dimension tables (containing descriptive attributes)

# on-premises
1. refers to computing infrastructure and software that are located within the physical premises of an organization.
2. which means organization/business maintain there own servers/data centers and managed by internal IT staff.

# Advantages of DW:
1. Better data quality:
2. Faster, business insights:
3. Smarter decision-making:

</details>

# DataTypes
**Numeric Types:**

**int:** Integer (whole number) data type.
**bigint:** Large integer.
**smallint:** Small integer.
**tinyint**: Very small integer.
**decimal(p, s):** Fixed precision and scale numeric data.
**numeric(p, s):** Fixed precision and scale numeric data (same as decimal).
**float(n):** Floating-point number.
**real:** Single-precision floating-point number.

**Character Strings:**

**char(n):** Fixed-length character data.
**varchar(n):** Variable-length character data.
**nvarchar(n):** Variable-length Unicode character data.
**text:** Variable-length non-Unicode data.

**Date and Time Types:**

**date:** Date data type.
**time:** Time data type.
**datetime:** Date and time data.
**datetime2:** Date and time data with larger fractional seconds precision.
**datetimeoffset:** Date and time data with time zone awareness.
**smalldatetime:** Date and time data with less precision.

**Binary Types:**

**binary(n):** Fixed-length binary data.
**varbinary(n)**: Variable-length binary data.
**image:** Variable-length binary data (for storing large data such as images).

**Other Types**:

**bit:** Boolean data type.
**uniqueidentifier:** Unique identifier (GUID).
**xml:** XML data type.
**geometry:** Spatial data type for representing data in a two-dimensional plane.
**geography:** Spatial data type for representing data in a round-earth coordinate system.

**JSON Types** (introduced in newer versions):

**json:** JSON data type for storing JSON (JavaScript Object Notation) data.

# DDL ( data defination language)
1. DDL commands are used to define, modify and manage the structure of database objects like table, view, constraints and indexes.
2. **Create:** Used to create new database objects.
3. **ALTER:** Used to modify the structure of existing database objects.
4. **TRUNCATE:** used to remove the data without deleting the table structure.
5. **DROP :** used to drop both data and table struture.
6. **RENAME:** Used to rename existing database objects.
7. Create syntax :
     CREATE TABLE table_name (
       column1 datatype [constraint],
       column2 datatype [constraint],
        ...);
   ex :
        create table sample
        ( serial_no int primary key identity,
          name varchar(50) not null,
          dob date unique,
          birthtime time,
          salary decimal(10,3),
          sex char(1),
          curr_tm datetime )
   
   ex2: **create table sample as (select * from existing_table_name )**

9. Alter syntax :
   
    A.--to add new column
    **alter table sample add last_name varchar(50);**

    B.--modifying coulumn data type
   **alter table sample alter column name varchar(60)**

    C.--modify the column name ( we can't do with single step)

    I-- Step 1: Add a new column with the desired name
   **ALTER TABLE sample
    ADD  full_name varchar(60);**

    II--Step 2: Update the new column with data from the old column
    **UPDATE sample SET full_name = name;**

    III-- Step 3: Drop the old column
    **ALTER TABLE sample
    DROP COLUMN name;**

10. truncate syntax : **truncate table sample;**
11.  drop syntax : **drop table sample;**

# DML (Data Manipulation Language):
1. these commands are used to manipulate the data stored in database objects.
2. **SELECT:** Used to retrieve data from one or more tables based on specified criteria.
3. **INSERT:** Used to add new rows of data into a table.
4. **UPDATE:** Used to modify existing data in a table.
5. **DELETE:** Used to remove rows of data from a table.
6. **MERGE:** Used to perform a combination of INSERT, UPDATE, and DELETE operations based on a specified condition.
7. 	create table sample
	(
  	serial_no int primary key identity,
  	name varchar(50) not null,
  	dob date unique,
  	birthtime time,
  	salary decimal(10,3),
  	sex char(1),
  	curr_tm datetime
 	)

 	insert into sample (name,dob,birthtime,salary,sex,curr_tm) values ('sindhu koramoni','12-dec-1997','10:55:34',120000.98,'F', CURRENT_TIMESTAMP),
 	('Aadhithya koramoni','24-nov-1999','10:55:34',120000.98,'M', CURRENT_TIMESTAMP),
 	('chandra prakash reddy Addan','03-jun-1993','10:55:34',120000.98,'M', CURRENT_TIMESTAMP),
 	('sripriya konda','29-apr-1997','10:55:34',120000.98,'F', CURRENT_TIMESTAMP),
 	('suppu goud','16-aug-1997','10:55:34',120000.98,'F', CURRENT_TIMESTAMP);

  	select * from sample;

 	update sample set name = 'Supraja Goud' where name = 'suppu goud';
 	update sample set name = 'Sripriya Konda' where name = 'sripriya konda';

	 delete from sample where name like '%koramoni'

# DCL (Data Control Language): 
1. DCL commands are used to control access to the database objects and define permissions for users or roles.
2. GRANT SELECT, INSERT ON Employees TO user1;
3. REVOKE INSERT ON Employees FROM user1;

   
      
   
        
    







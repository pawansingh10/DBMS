# DBMS
Database Management System


### **Database**
***
- Database is an organised collection of data, Storing and retrieving digitally from a remote or local system.

- Database can be vast and complex and such databases are developed using fixed design and modelling approaches.

### **DBMS**
***
- DBMS stands for ***Database Management System.***

- DBMS is a system software responsible for the **Creation, Retrieval, Updation and Management** of the database.

- It ensures that our data is consistent, organized and easily accessible by serving as an Interface between the database and its end users or application software.


### **RDBMS**
***
- RDBMS stands for ***Relational Database Management System.***

- RDMS stores data in the forms of a collection of Tables/Relations can be defined between common field of these tables.

- Most modern Database Management System like ***MySQL, MicroSOft SQL Server, Oracle, IBM DB2 and Amazon Redsit*** are based on RDBMS

### **SQL**
***
- SQL stands for ***Structure Query Language***

- Standard Language for Relational Database Management System

- It is especially useful in handling organized data comprised of entities and relation between different entities of data


### **SQL vs MySQL**
***
- **SQL** is standard language for retrieving and manipulating Structured Databases

- **MySQL** is a Relational Database Management System like **SQL Server, Oracle or IBM DB2** i.e, used to manage SQL database


### **Table and Fields**
***
- ***Table*(Relation) is an organised collection of data stored in the form of rows and columns***
- **Columns** can be categorized as Vertical & **Rows** as Horizontal 
- | Table | Relation|
  |-------|---------|
  | Columns | Field |
  | Rows    | Records|
  
### **Constraints in SQL**
***
- Constraints are used to specify the rules concerning data in the table.
- It can be applied for single or multiple fields in a SQL table during **CREATION** of Table or After **CREATION** uaing **Alter** table command
- The Constraints are :- 

- **1. NOT NULL**
   - Restricts NULL Value from being inserted into a column

- **2. CHECK**
   - Verify that all values in a field satisfy a condition.

- **3. DEFAULT**
   - Automatically Assigns a default value if no value has been specified for the field
   
- **4. UNIQUE**
   - Ensure unique values to be inserted into the fields
   
- **5. INDEX**
   - Indexes provides faster retrieval of records
   
- **6. PRIMARY KEY**
   - Uniquely identifies each records in a table
   
- **7. FOREIGN KEY**
   - Ensures referential integrity for a record in another table
   

### **Primary Key**
***
- The primary key constraints uniquely identifies each row in a table .
- It must contain **UNIQUE** values and has an implicit **NOT NULL** constraint.
> ***A table in SQL is strictly restricted to have one and only one Primary Key which is comprises of single or multiple columns***

- ```sql
     CREATE TABLE student ( Id INT NOT NULL Name VARCHAR(50) Primary Key(Id) ); 
  ```
- ```sql
     CREATE TABLE student (Id INT NOT NULL First_name VARCHAR(25) NOT NULL, CONSTRAINTS pk Primary Key(Id, First_name));
  ```
  
- ```sql
     Alter Table students add primary key(id); 
  ```
- ```sql
     Alter Table students add Constraints pk Primary Key(id, First_name);
  ```
 

### **Foreign Key**
***
- Foreign Key comprises of Single or Collection of fields in a table that essentially refers to the primary key in another table.
- Foreign Key constraints ensures referential integrity in the relation between two tables.
- ```sql
     CREATE TABLE students (Id, INT NOT NULL Name VARCHAR(20) Lib_Id INT Primary Key(Id) Foreign Key(Lib_Id) References Library(Lib_Id));
  ```
- ```sql
     CREATE TABLE students (Id NOT NULL Primary Key Name VARCHAR(20) Lib_Id INT Foreign Key(Lib_Id) References Library(Lib_Id));
  ```
 
- ```sql
     Alter TABLE students Add Foreign Key(Lib_Id) References Library(Lib_Id);
  ```
  
### **Unique Constraint**
***
- A unique constraints ensure that all values in a column are different.

- This provides uniqueness for the column and helps to identify each row uniquely

> ***Unlike Primary Key, There can be multiple unique constraints defined per table***

- ```sql
      CREATE TABLE students (Id INT NOT NULL UNIQUE Name VARHAR(25));
  ```

- ```sql
      CREATE  TABLE students (Id NOT NULL Last_Name VARCHAR(20) First_name VACHAR(20) NOT NULL Constraints pk UNIQUE(Id, First_Name) );
  ```
  
- ```sql
      Alter Table students Add constraints pk Unique(Id, First_name);
  ```
 
- ```sql
      Alter Table students Add Unique(Id);
  ```
  
### **Join**
***
- A Join clause is used to combine data from two or more table based on a related column between them.
- | Roll_No | Name  | Add  | Phone | Age  |
  |---------|-------|------|-------|------|
  | 1 |---- | -----|  ---- | -----| 18 |
  | 2 |---- | -----|  ---- | -----| 19|
  | 3 |---- | -----|  ---- | -----| 20|
  | 4 |-- | -----|  ---- | -----| 21 |
  | 5 |--- | -----|  ---- | -----| 22 |
  
- | Course_Id | Roll_no |
  |-----------|---------|
  | 1    | 1 |
  | 2 | 2 |
  | 2 | 3 |
  | 3 | 4 |
  | 3 | 5 |
 
### **Different Type Of SQL Join**
***
- ***1. Inner Join***
  - Inner Join is used to return rows from both tables which satisfy the given condition.
  - It is the most widely used join operation and can be considered as a default Join-Type
  - [x] **Theta Join**
  - [x] **Natural Join**
  - [x] **Equi Join**

- ***2. Outer Join***
  - [x] **Left Outer Join**
  - [x] **Right Outer Join**
  - [x] **Full Outer Join**



### **Self-Join**
***
- A self join is a case of regular join where a table is joined to itself based on some relation between its own column

- Self Join uses the Inner-Join or left-Join **clause** and a table **alias** is used to assign different name to the table

- ```sql
     SELECT A.emp_id AS "Emp_Id", A.emp_name AS "Employee", B.emp_id AS "Sup_Id", B.emp_name AS "Supervisor" From employee A, employee B Where A.emp_id=B.emp_id;
  ```
  
### **Cross-Join**
***
- Cross Join can be defined as a cartesian product of the two tables included in the join

- The table after join contains the same number of rows as in the cross product of numbers of rows in the two tables

- ```sql
     SELECT stu.name, sub.subject FROM students AS stu CROSS JOIN subjects AS sub;
  ```
  

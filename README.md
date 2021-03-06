# DBMS
Database Management System


### **Database**
***
- Database is an organised collection of data, Storing and retrieving digitally from a remote or local system.

- Database can be vast and complex and such databases are developed using fixed design and modelling approaches.

> **Database is a collection of inter-related data which is used to retrieve, insert, and delete the data efficiently**

### **DBMS**
***
- DBMS stands for ***Database Management System.***

- DBMS is a system software responsible for the **Creation, Retrieval, Updation and Management** of the database.

- It ensures that our data is consistent, organized and easily accessible by serving as an Interface between the database and its end users or application software.

> **DBMS is a software which is used to manage the Database with protection & Security in efficient way**
> Example - Oracle, MySQL, SQLite, MongoDB etc

### Why DBMS?
***
- **Protection & Security**
- **Efficient**
- **Maintain Data Consistency**
- **Easy to use**


## **ACID Property**
***
- **Atomicity**
  > ***Either All or Nothing***
 
- **Consistency**
  > ***Data should be valid according to all defined Rule***
 
- **Isolation**
  > ***Transaction do not affect each other***
  
- **Durability**
  > **Commited data would not be lost even after power failure**

## File Approach vs Database Approach
***
| **File Approach** | **Database Approach** |
|-------------------|----------------------|
| Data Redundancy | No Data Redundancy |
| Data Inconsistent | Data Consistency & Integrity |
| Data Security Low     | Data Security High |
| Difficult to Access Data as Compare to DBMS | Easy to access data |
| Atomicity Issues | Atomicity follows|
| Data Recovery Issues | Easy Data Recovery |
| Static              | Flexible |


## Schema
***
- **Schema** means **Structure** simply means **Table** which is **Rows & Columns**
- Database Schema is the skeleton or structure that represents the logical view of entire database

> ***Database schema means the overall strucure of database without data value***

- There are 3 types of schema architecture
- **External Schema**
  > ***How to show data to users?***
- **Conceptual Schema**
  > ***What is the structure of Data?***
- **Physical Schema**
  > ***Where the data is physically present?***

## Database Model or Data Modelling
***
- Data Modelling is a way to define the structure or logical design of database & the way of data is stored, accesses and updated in the database

- **Relational Model**
  > ***Data is oranised in 2-Dimensions***
 
- **Hierarchical Model**
  > ***Data is represented in a tree like structure***

- **Network Model**
  > ***Extension of Hierarchical Model***
  
- **ER-Model**
  > ***Entity Relationship Model, Objects are divided into Entities and their characteristics***


## Data Abstraction
***
- Data Abstraction means, The Process of Hidding background Details from the Users
- There are 3 levels of Data Abstraction:-
- **Physical Level**
   > ***How data is stored actually?***
   
- **Logical Level**
   > ***What are data get stored & what are the relationship among them?***

- **View Level**
   > ***It is the highest level of data abstraction that only describe a part of database indirectly***


## Data Independency
***
> **Data Independency means the capacity to change data from one level to another without affecting**



### **RDBMS**
***
- RDBMS stands for ***Relational Database Management System.***

- RDMS stores data in the forms of a collection of Tables/Relations can be defined between common field of these tables.

- Most modern Database Management System like ***MySQL, MicroSOft SQL Server, Oracle, IBM DB2 and Amazon Redsit*** are based on RDBMS

> **It arrange data & Information into Rows and Columns**
> Oracle, MySQL, SQL Server etc
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
  
 ## Database Language
 ***
 - The language which is used to interact with database through some set of commands & perform **CRUD** opeation on Database
  
  - **DDL**
    - Data Definition Language
    - Create
    - Alter
    - Drop
    - Truncate
  
  - **DML**
    - Data Manipulation Language
    - Insert
    - Update
    - Delete
    - select
  
  - **DCL**
    - Data Control Language
    - Grant
    - Revoke
  
  - **TCL**
    - Transaction Control Language
    - Commit
    - RollBack
    - SavePoint
  

## **Drop vs Truncate vs Delete**
***
| Drop & Truncate are DDL Command| Delete is a DML Command| 
| Used to delete table from database| Used to delete rows from the table|
| Once table is deleted all priviledges & indexes that are related to the table also get deleted| Not in the case of Delete|
| Drop & Truncate cannot Rollback | Deletecn be Rollback|

### Tuple
***
- A single row of table, which contains a single record is called **Tuple**

### Degree & Cardinality
***
- **Degree**
  > ***Total Number of Attributes(columns) in a table***
  
- **Cardinality**
  > ***Total number of Records(Rows) in a table***
  
### Relation
***
- ***Every Individual Table in a Database is called Relation***
- **Table==Relation**
- A Table is a Relation because it stores the relations between data in its Rows & Columns

### Relationship in DBMS
***
- There are basically 4 types of Relationship
- **1. One to One**
- **2. One to Many**
- **3. Many to One**
- **4. Many to Many**


### Query vs Subquery
***
- Query is a statement that is used for extracting data from Database
- ```sql Select * FROM table_name;```
- Query within Query is SubQuery
- ```sql Select * FROM student Where marks=(Select max(marks) FROM student);```

### Role Of DML Compiler
***
> **It translate DML statements in a query language into low level instruction that the Query Evaluation Engine can easily Understand**


### Clause
***
- Clause enable us to specific conditions that filetrs the results as per the requirement
- Most Commonly used caluse are:-
  - HAVING
  - Where
  - Order By
  - Group BY


## **Normalization**
***
- Normalization is the process of removing redundant data and reduce data dependancy in a table or relation
- | 1-NF | 2-NF | 3-NF | BCNF | 4-NF |
  |------|------|------|------|------|
 
- **1. 1-NF**
  > A realtion or table is said to be in 1-NF if it has **Atomic Property**
  > Each Table cell should contain a single value
  > Each records needs to Unique
  
- **2. 2-NF**
  > A relation or table is said to be in 2-NF if it is in **1-NF** and **ALl non-prime attribute is fully functional dependent on Primary Key**
  
- **3. 3-NF**
  > A relation or table is said to be in 3-NF if it is in **2-NF** and **There is no transitive functional dependency**
  
- **4. BCNF**
  - ***Boyce-Codd Normal Form***
  > It is considered as to be advance version of **3-NF** or **3.5-NF**
  > A table or relation is said to be in BCNF if it is in **3-NF** and **For every funtional dependency p->Q, P should be super key of this table**
  
- **5. 4-NF**
  > A relation or table is said to be in 4-NF if it is in **3-NF** and **No Multi-Value Dependency**
  

## **Denormalization**
***
- It is the reverse process of Normalization
- It is the process of trying to improve the readability of the database by grouping data
- Denormalization is also used for Speeding Up the performance


### Transaction
***
- Transactions refers to the collection of multiple statement that are responsible for transferring a database from one consistent state to another consistent state


### Trigger
***
- Triggers are defines as special kind of stored programs, which are automatically executed whenever a specific operation occurs in the database server


### Lock
***
- Locking is mechanism to protect data integrity and ensure data consistency during transactions.
- Locks are most common cause of blocked process

- Differents Types Of Locks
  - **Shared Lock**
    > ***These locks are acquired by readers during read operation***
    > When two transactions are granted read access, Data Updation is not allowed until shared lock is release.
    
  - **Exclusive Lock**
    > ***Data items can be both read as well as write by transaction***
    > In Multiple transactions do not modify the same data simultaneously
    

### Cursor
***
- Cursor is a temporary work area created in system memory when a SQL Statement is executed

- A Cursor can hold more than one row but can process only one row at a time






## Key
***
- Key is an attribute or set of attributes which help us to identify row or column

* **Super Key**
  > **Attribute or set of attributes that uniqueness in database is reffered as Super key**
  > It is the superset of Candidate Key
  
* **Candidate Key**
  > **A Super key with no repeated attribute is called Candidate key**
  > The primary key should be selected from the candidate key
 
* **Composite Key**
  > **A key which has multiple attribute to uniquely identify rows in a table is called Composite Key**
  
* **Primary Key**
  > **Primary key is a key which is uniquely identify the row and column**

- Rules for Primary Key
  - **Primary Key fields cannot be NULL**
  - **It must for every row to have a primary key**
  - **Primary key must be unique**
  - **Primary Key column never updated if any foreign**
  
* **Foreign Key**
  > **A set of attribute or attributes that is used to establish and enforce a link between data in two or more relations**
  
  - Foreign Key helps to maintain Data Integrity


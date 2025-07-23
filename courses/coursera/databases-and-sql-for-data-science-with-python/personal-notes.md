# Databases and SQL for Data Science with Python

[Databases and SQL for Data Science with Python](https://www.coursera.org/learn/sql-data-science/home/info)

## 1. Getting Started with SQL

### Basic SQL

- Structured Query Language (SQL): language used for relational databases to query or get data out of a database
- data: collection of facts in the form of words, numbers or pictures; one of the most critical assets of any business; it needs to be secure
- database: repository of data; program that stores data; provides the functionality for adding, modifying and querying data; different kinds of databases store in different forms
  - other names: database server, database system, data server, DBMS
- relational database
  - tabular form: spreadsheet; columns and rows
- Database Management System (DBMS): software to manage databases
- Relational DBMS (RDBMS): set of software tools that controls the data (access, organization and storage); backbone of applications
  - e.g. MySQL, Oracle Database, IBM Db2, ...
- Data Manipulation Language statements (DML statements): used to read and modify data.
- Basic SQL Commands
  - create a table
  - insert data
  - select data
  - update data
  - delete data

#### Select

- SELECT statement: query; the output is called a result set or a result table.
  - `SELECT * FROM <tablename>`
  - `SELECT * FROM Book : selects all data rows and columns
  - `SELECT column1, column1, ... FROM Book`: selects all data rows from specific columns
  - the order of the columns always match the order in the SELECT statement
- WHERE: to restrict the result set; always requires a predicate
  - predicate: condition evaluation to true, false or unknown; used in the search condition of the WHERE clause
  - `SELECT book_id, title FROM Book WHERE book_id='B1'`: selects one row with specific columns
- COUNT: retrieves the number of rows
  - `SELECT COUNT(*) FROM tablename`
- DISTINCT: removes duplicate values
  - `SELECT DISTINCT columnname FROM tablename`
  - `SELECT COUNT(DISTINCT columnname) FROM tablename`
- LIMIT: restricts the number of rows retrieved
  - `SELECT * FROM tablename LIMIT 10`
  - `SELECT * FROM tablename WHERE book_id='B1' LIMIT 10`
- OFFSET: starts FROM a specific row to retrive data
  - `SELECT * FROM tablename LIMIT 10 OFFSET 5`

#### Insert

- INSERT statement: populate table with data by inserting rows
  - `INSERT INTO [TableName]`<br>
    `<([ColumnName], ...)>`<br>
    `VALUES ([Value], ...)`<br>
  - `INSERT INTO AUTHOR`<br>
    `(AUTHOR_ID, LASTNAME, FIRSTNAME, EMAIL, CITY, COUNTRY)`<br>
    `VALUES ('A1', 'Chong', 'Raoul', 'rfc@ibm.com','Toronto', 'CA'), ('A2', 'Doe', 'Jane', 'jd@ibm.com','Montreal', 'CA')`

#### Update

- UPDATE statement: used to alter or modify the data
  - `UPDATE [TableName] SET [[ColumnName]=[Value]] <WHERE [CONDITION]>`
  - `UPDATE AUTHOR SET LASTNAME='Katta' FIRSTNAME='Lakshmi' WHERE AUTHOR_ID='A2'`

#### Delete

- DELETE statement: remove one or more rows from a table
  - `DELETE FROM [TableName] WHERE [CONDITION]`
  - `DELETE FROM AUTHOR  WHERE AUTHOR_ID IN ('A2', 'A3')`

## 2. Introduction to Relational Databases and Tables

- relational model:
  - most used data model
  - data is stored in tables
    - row: record
    - column: attribute
  - allows for relationships between different tables
  - allows for data independence
- data independence: ability to change the structure without having to change the application programs - if you do some changes applications can still access the data in the same way
  - logical data independence: changing the logical schema (adding fields or changing data types)
  - physical data independence: changing physical storage of data (like file organization or storage devices)
  - physical store independence: changing the actual storage mechanism (like hard drives, SSDs, or cloud storage)
- entity relationship (ER): concept of identifying entities (objects) in a system and the relationships between them
- entity relationship diagram (ERD): visual representation of the entities (tables) and their relationship
  - entity: rectangle
  - attributes: ovals
  - primary key: uniquely identifies each tuple or row (prevent data duplication)
  - foreign keys: primary keys defined in other tables to create a link between the tables
- entity relationship model: design tool - framework that describes how entities and their relationships are represented in a database
  - entities become tables
  - attributes get translated into columns
- common data types: CHAR (fixed length) and VARCHAR (variable length), numbers such as INT, FLOAT and DECIMAL, timestamps including DATE, TIME, DATETIME, TIMESTAMP

### Types of SQL Statements

- Data Definition Language (DDL) statements: define, change or drop data
  - CREATE: creating tables and defining its columns
  - ALTER: altering tables including adding/dropping columns and modifying their data type
  - TRUNCATE: deleting data in a table but not the table itself
  - DROP: deleting tables
- Data Manipulation Language (DML) statement: read and modify data - CRUD operations (create, read, update and delete rows)
  - INSERT: insert one or several rows
  - SELECT: reads or selects rows
  - UPDATE: edit rows
  - DELETE:  remove rows

#### Create

- CREATE statement: creating tables and defining its columns
  - `CREATE TABLE table_name`<br>
    `(`<br>
    `column_name_1 datatype optional_parameters,`<br>
    `column_name_2 datatype,`<br>
    `...`<br>
    `)`
- optional parameters
  - KEY PRIMARY: identifies primary key of the table
  - NOT NULL: values cannot be null for this column

#### Alter

- ALTER statement: altering tables including adding/dropping columns,  modifying their data type, adding or removing keys and adding or removing constraints
  - `ALTER TABLE table_name`<br>
    `ADD COLUMN column_name_1 datatype`<br>
    `ADD COLUMN column_name_2 datatype`<br>
    `MODIFY column_name_2 datatype`<br>
    `...`

#### Drop

- DROP statement: deleting tables
  - `DROP TABLE table_name;`

#### Truncate

- TRUNCATE statement: deleting data in a table but not the table itself
  - `TRUNCATE TABLE table_name;`

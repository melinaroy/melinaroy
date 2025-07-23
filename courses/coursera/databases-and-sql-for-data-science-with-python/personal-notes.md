# Databases and SQL for Data Science with Python

[Databases and SQL for Data Science with Python](https://www.coursera.org/learn/sql-data-science/home/info)

## 1. Getting Started with SQL

### Basic SQL

- database: structured place to store data - can be locally or remotely
- Structured Query Language (SQL): **language** used for relational databases to query or get data out of a database
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

- `SELECT` statement: query; the output is called a result set or a result table.
  - `SELECT * FROM <tablename>`
  - `SELECT * FROM Book : selects all data rows and columns
  - `SELECT column1, column1, ... FROM Book`: selects all data rows from specific columns
  - the order of the columns always match the order in the SELECT statement
- `WHERE`: to restrict the result set; always requires a predicate
  - predicate: condition evaluation to true, false or unknown; used in the search condition of the WHERE clause
  - `SELECT book_id, title FROM Book WHERE book_id='B1'`: selects one row with specific columns
- `COUNT`: retrieves the number of rows
  - `SELECT COUNT(*) FROM tablename`
- `DISTINCT`: removes duplicate values
  - `SELECT DISTINCT columnname FROM tablename`
  - `SELECT COUNT(DISTINCT columnname) FROM tablename`
- `LIMIT`: restricts the number of rows retrieved
  - `SELECT * FROM tablename LIMIT 10`
  - `SELECT * FROM tablename WHERE book_id='B1' LIMIT 10`
- `OFFSET`: starts FROM a specific row to retrive data
  - `SELECT * FROM tablename LIMIT 10 OFFSET 5`

#### Insert

- `INSERT` statement: populate table with data by inserting rows
  - `INSERT INTO [TableName]`<br>
    `<([ColumnName], ...)>`<br>
    `VALUES ([Value], ...)`<br>
  - `INSERT INTO AUTHOR`<br>
    `(AUTHOR_ID, LASTNAME, FIRSTNAME, EMAIL, CITY, COUNTRY)`<br>
    `VALUES ('A1', 'Chong', 'Raoul', 'rfc@ibm.com','Toronto', 'CA'), ('A2', 'Doe', 'Jane', 'jd@ibm.com','Montreal', 'CA')`

#### Update

- `UPDATE` statement: used to alter or modify the data
  - `UPDATE [TableName] SET [[ColumnName]=[Value]] <WHERE [CONDITION]>`
  - `UPDATE AUTHOR SET LASTNAME='Katta' FIRSTNAME='Lakshmi' WHERE AUTHOR_ID='A2'`

#### Delete

- `DELETE` statement: remove one or more rows from a table
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
  - `CREATE`: creating tables and defining its columns
  - `ALTER`: altering tables including adding/dropping columns and modifying their data type
  - `TRUNCATE`: deleting data in a table but not the table itself
  - `DROP`: deleting tables
- Data Manipulation Language (DML) statement: read and modify data - CRUD operations (create, read, update and delete rows)
  - `INSERT`: insert one or several rows
  - `SELECT`: reads or selects rows
  - `UPDATE`: edit rows
  - `DELETE`:  remove rows

#### Create

- `CREATE` statement: creating tables and defining its columns
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

- `ALTER` statement: altering tables including adding/dropping columns,  modifying their data type, adding or removing keys and adding or removing constraints
  - `ALTER TABLE table_name`<br>
    `ADD COLUMN column_name_1 datatype`<br>
    `ADD COLUMN column_name_2 datatype`<br>
    `MODIFY column_name_2 datatype`<br>
    `...`

#### Drop

- `DROP` statement: deleting tables
  - `DROP TABLE table_name;`

#### Truncate

- `TRUNCATE` statement: deleting data in a table but not the table itself
  - `TRUNCATE TABLE table_name;`

### Cloud Databases

- advantages:
  - ease of use (API, web interface, cloud/remote applications)
  - scalability & economics (expand/shrink storage & compute resources, pay per use)
  - disaster recovery (natural disaster, equipment failure, power outage, ...)
- examples of cloud databases
  - IBM Db2
  - PostgreSQL
  - Oracle Database Cloud Service
  - MS Azure SQL DB
  - Amazon Relational Database Services (RDS)
- cloud databases available as
  - VMs (need to install everything and maintain it) or managed service
  - single tenant (each customer has their own db - security & performance) or multi-tenant (customers share the same db - cost savings & easier management)

## Intermediate SQL

### 3.1 Using String Patterns and Ranges

- String pattern: sequence of chars used to search for specific text
- `LIKE` predicate: used in WHERE clause to search for a pattern in a column
- wildcard characters:
  - `%`: unknown chars or sequences
- comparison operator
  - `between .. and ..`: inclusive range
  - `IN`: specifies a set of values in a WHERE clause
- `ORDER BY`: to sort the result set by a specified column
  - by default, sorted in alphabetical (ascending)
  - `DESC`: to sort in descending order (added after the column name)
  - `ORDER BY` comes after `GROUP BY` clause
- `GROUP BY`: to group rows that have the same values in specified column(s)
- `AS`: to assign an alias (temporary name) to a column name or table
- `HAVING`: to set a condition on groups created by `GROUP BY`

### 3.2 Functions, Multiple Tables and Sub-queries

- built-in functions:
  - can reduce the amount of data that needs to be retrieved
  - can speed up data processing
- Aggregate or column functions:
  - INPUT: collection of values (e.g. entire column)
  - OUTPUT: single value
  - `SUM()`: add up all the values in a column
  - `MIN()`: get to lowest value of a column
  - `MAX()`: get the highest value of a column
  - `AVG()`: return the average value
    - can be performed between columns
- Scalar and string functions: perform operations on every input value
  - `ROUND()`: round up or down values
  - `LENGTH()`: length of char or varchar
  - `UCASE`: return upper case values of strings
  - `LCASE`: return lower case values of strings
- date: YYYYMMDD
- time: HHMMSS
- timestamp: YYYYXXDDHHMMSSZZZZZZ
  - XX: month
  - ZZZZZZ: mnicroseconds
- data/time functions:
  - `YEAR()`
  - `MONTH()`
  - `DAY()`
  - `DAYOFMONTH()`
  - `DAYOFWEEK()`
  - `DAYOFYEAR()`
  - `WEEK()`
  - `HOUR()`
  - `MINUTE()`
  - `SECOND()`
  - `DATE_ADD(COLUMN_NAME, INTERVAL Number Date_element)`, e.g. DATE_ADD(Date, INTERVAL 3 DAY)
  - `DATE_SUB(COLUMN_NAME, INTERVAL Number Date_element)`
  - `CURRENT_DATE`
  - `CURRENT_TIME`
  - `FROM_DAYS(number_of_days)`: to present the output in a YYYYMMDD format
  - `DATEDIFF(Date1, Date2)`: gives as number of days between two dates
- Sub-query: a query inside another query
- column expression: substitute column name with a sub-query
- table expression or derived table: substitute the table name with a sub-query
- multiple tables in same query:
  - sub-queries
  - implicit `JOIN`: full join if no operands specified
  - `JOIN` operators
    - `INNER JOIN`
    - `OUTER JOIN`

## 4. Accessing Databases using Python

- benefits of using Python:
  - ecosystem: numpy, pandas, matplotlib, scipy
  - ease of use
  - portable
  - supports relational database systems
  - python database API (DB-API)
  - detailed documentation
  - notebooks
- jupyter notebooks advantages:
  - language of choice
  - can be shared by github, email, ecosystem
  - interactive output
  - big data integration
- SQL API: library function calls as an Application Programming Interface (API) for the DBMS

| Application/Database                     | SQL API     |
| ---------------------------------------- | ----------- |
| MySQL                                    | MySQL C API |
| PostgreSQL                               | psycopg2    |
| IBM DB2                                  | ibm_db      |
| SQL Server                               | dblib API   |
| Database access for Microsoft Windows OS | ODBC        |
| Oracle                                   | OCI         |
| Java                                     | JDBS        |

- DB-API: python's standard API for accessing relational databases
  - allows a single program to work with multiple kinds of relational databases
  - easy to implement and understand
  - encourage similarity between python modules
  - achieve consistency
  - portable access databases
  - broad reach of database connectivity from python
- Connection Objects
  - database connections
  - manage transactions
- Connection Methods
  - `.cursor()`: returns new cursor object using the connection
  - `.commit()`: commit any pending transaction to the db
  - `.rollback()`: roll back to the start of any pending transaction
  - `.close()`: close db connection

- Cursor Objects
  - behaves like a filename or file handle
  - database queries
  - scroll through result set
  - retrieve results
  - cursors connected from the same connection are not isolated (any changes made by a cursor to the db are immediately visible by the other cursors)
  - cursors created from different connection might or might not be isolated depending on how the transaction support is implemented
- Cursor Methods
  - `.callproc()`:
  - `.execute()`:
  - `.executemany()`:
  - `.fetchone()`:
  - `.fetchmany()`:
  - `.fetchall()`:
  - `.nextset()`:
  - `.arraysize()`:
  - `.close()`:

### SQL Magic

- magic statements
  - special commands that provide special functionalities
  - not valid Python code but affect the behavior of the notebook
  - designed to solve standard data analysis problems
- Line Magics: commands that are prefixed with a single `%` and operate on a single line of input
  - `%pwd`: prints the current working directory
  - `%ls`: lists all files in the current directory
  - `%history`: shows the command history
  - `reset`: resets the namespace by removing all names defined by the user
  - `who`: lists all variables in the namespace
  - `whos`: provides more detailed info about all variables
  - `matplotlib inline`: makes matplotlib plots appears within the notebook
  - `timeit`: times the execution of a single statement
  - `lsmagic`: lists all available line magics
- Cell Magics: commands that are prefixed with two `%%` ad operate on multiple lines of input

### Graph and pandas

Example:

```py
!pip install ipython-sql
!pip install seaborn
import seaborn as sns
%load_ext sql

import csv, sqlite3
con = sqlite3.connect("socioeconomic.db")
cur = con.cursor()
!pip install pandas

%sql sqlite:///socioeconomic.db

import pandas
df = pandas.read_csv('https://data.cityofchicago.org/resource/jcxq-k9xf.csv')
df.to_sql("chicago_socioeconomic_data", con, if_exists='replace', index=False,method="multi")

# Install the 'ipython-sql' and 'prettytable' libraries using pip
!pip install ipython-sql prettytable
# Import the 'prettytable' library, which is used to display data in a formatted table
import prettytable
# Set the default display format for prettytable to 'DEFAULT' (i.e., a simple table format)
prettytable.DEFAULT = 'DEFAULT'

income_vs_hardship = %sql SELECT per_capita_income_, hardship_index FROM chicago_socioeconomic_data;
plot = sns.jointplot(x='per_capita_income_',y='hardship_index', data=income_vs_hardship.DataFrame())
```

## 5. Course Assignment

- getting list of tables in the db
  - SQLite3: `sqlite_master` (`SELECT name FROM sqlite_master WHERE type="table"`)
  - SQL server: `information_schema.tables`
  - MySQL: `SHOW TABLES`
- getting table attributes
  - SQLite3: `PRAGMA table_info([table_name])`
  - My SQL: `DESCRIBE table_name`

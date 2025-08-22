# 8.5 Structured Query Language (SQL)

=> language used to interact with databases
*   Two categories of SQL: DDL & DML...

## Data Definition Language (DDL)

=> SQL used to manipulate the structure of a database
*   Common DDL commands are:
    -   `CREATE DATABASE <name>;`
    -   `CREATE TABLE <name> (attribute#1 datatype, attribute#2 datatype ...);`
    -   `ALTER TABLE <name> ADD PRIMARY KEY (<name>);` _sets existing attribute as primary key or secondary key_
*   keys can be created on creation of the table or added later

### Some SQL Rules

-   consists of sequence of commands
-   commands end with ';' and can span lines
-   no case sensitivity (T = t)
-   lists of items are separated with a comma
-   some commands require their variables to be enclosed by '()'
    -> e.g. `create table`

### Datatypes in SQL

*   datatypes have to be defined on creation of an attribute
*   datatypes and datatype names might vary with different DBMS
*   Common Datatypes:
    -   `character(<value>)` -> uses predefined amount of storage (text L)
    -   `varchar(<value>)` -> only uses as much storage as text needs _requires maximum characters to be defined_
    -   `boolean`
    -   `integer`
    -   `real` -> basically a float
    -   `date`
    -   `time`

## Data Manipulation Language (DML)

=> SQL used to modify data inside a database
-> This includes insertion of data, modification, deletion, and reading
*   Common Commands:
    -   `SELECT <names> FROM <name>;`
    -   `INSERT INTO <names> (attribute#1, attribute#2) VALUES (<value>, <value>);`
        - _is used when order is unknown: attribute #1, #2 will be attribute names and Order in values matches order of insert into_
        - _can be used alone if attribute order of table is known_
    -   commands that can be added on top:
        -   `ORDER BY <attribute>*` -> orders alphabetically by selected column
        -   `GROUP BY <attribute>` -> eliminates duplicates of entities with identical value for <attribute>
        -   `WHERE <attribute> = <value>` -> filters entities. '=' can be e.g. '>'

### Aggregate Commands

\* ASC and DESC can be specified to change the order

=> SQL Commands that perform some operation with data from multiple tuples
*   Example Commands:
    -   `SELECT Count(<attribute>)` -> counts rows that have a value for <attribute>
    -   `AVG(<attribute>)` -> attribute average
    -   `SUM(<attribute>)` -> sum of <attribute>

### Join Conditions

=> two tables are joined based on a common attribute, data can be fetched from that temporary combined table.
example:
`SELECT VenueName, Date` _<- values to fetch_
`FROM Band-Booking, Booking`
`WHERE Band-Booking.BookingID = Booking.BookingID` _<- combine both tables with foreign key 'BookingID'_
`AND Band-Booking.BandName = 'Daft Punk's` _<- filter combined table for specific entity_

### Modify Data

*   `UPDATE <table> SET <attribute> = <value>` -> _sets the data for all values of <attribute>_
    `WHERE <attribute2> = <value>;` -> _filters for specific entity to modify_
*   `DELETE FROM <table>`
    `WHERE <attribute> = <value>;` <- _delete all entities in <table> where the attribute has a certain value_
    -   Deletion Error with Foreign Keys:
        -   if an attribute acts as a foreign key in an other table, the DBMS won't allow the deletion of the original attribute
        -> Foreign keys have to be deleted before the original attribute

---

### Exam Style 4, 5b iii, iv, 6c

**4. a)** `create table subject (subjectname varchar, primary key, subjectteacher varchar);`

`create table student(studentid integer primary key, studentname varchar, studentothername varchar, dateofbirth date);`

**b)** `alter table subject set primary key(subjectname);`

`alter table tutorial set studentid foreign key...`
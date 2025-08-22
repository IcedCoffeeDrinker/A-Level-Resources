# 8.1 Relational Databases

## Problems with File-Based Systems
- all databases, file-based or not, are vulnerable to wrong data entry
    - -> fix: validation
- File-based systems, using only a single file don't allow for permission handling

### File-based systems using multiple files:
- are vulnerable to data redundancy
    - -> means same data stored more than once
- data dependency becomes an issue:
    - -> changing data in one file doesn't update the same data in other tables -> integrity issue
- pre-defined structure issues: when inserting an extra column, a program that targeted e.g. column 4 might have to be rewritten
    - -> databases tend to be more rigid, making it harder to create new programs that use a database that was optimized for other programs
    - -> I imagine this being an issue with any database...

## Relational Databases

### Structure:
- data is stored in relations which are special types of tables
- It is given a name and a list of attributes on creation
    - -> Users(userID, balance, recent...) <- created like this
- Attributes are the column headers of a table, e.g. 'User-ID'
- There is no order for columns or rows
- A row in a relation is called a **tuple**
    - -> sometimes reffered to as 'record' and attribute values as 'fields'
- A tuple is reffered to as 'one instance' of a relation
- Relational databases use 'atomic' values: an attribute value holds either **one** value or no value

### Keys
- **Primary key:** each relation has one attribute (or a combination of attributes) that are used as a primary key
    - each tuple must hold a unique value for that key -> used as a selector
    - ensures integrity -> no duplicates
- **Candidate keys:** some relations have multiple attributes for which all values are unique
    - -> those attributes are considered candidate keys
- **Secondary keys:** candidate keys that weren't chosen to be a primary key
- often there is no candidate key, so a primary key has to be created
- the DBMS (database management system) rejects any new tuples with already existing primary key values
- **Foreign keys:** an attribute (a column) that refers to a column in another table (relation)
    - prevents data redundancy and protects integrity as data gets changed at all locations
    - provides referential integrity: foreign keys can be used to link attributes to prevent entry of non-existing values
        - -> the foreign key lists all acceptable values
        - -> the DBMS checks for referential integrity

## Exam-Style Questions 1, 5a, 6a

1.  **a)**
    i.  **Relation** -> the entire table
        **Attribute** -> a column, e.g. 'subject studied'
        **Tuple** -> a row, e.g. Xiangfei, 3, MUDI, Computing, A, DER
    ii. There are no column headers (attributes), so it's not clear which column matches to which attribute. This could be fixed by adding column headers.
        Also there's no truly unique attribute, so there are no candidate keys that could be chosen as a primary key. This could be solved by creating a private key, e.g. 'user_id' and generating the primary key attribute for each new user. This could be an index number.
    iii. haven't done

    **b)**
    i.  1. Prevention of data abundancy through foreign keys
        2. The splitting of one table into multiple for permission handling or better accessability...?
        3. Tutorial has a compound primary key
    ii. It would be a problem if no foreign key was used for Student Name as it might cause integrity issues and would result in data aboundancy
        -> Student names might not be unique but it's a primary key (haven't seen where)
    iii. haven't done

2.  **a)**
    i. Database Management System
    ii. He could introduce different levels of authorization that allow access to different attributes
        He could do regular updates?
    iii. The school secretary could use the DBMS to search for all students that attend a specific course. This could e.g. be done over the denominator or by dedicated software.
    iv. Data integrity and abundancy are no more of a problem due to the use of foreign keys.
        It's easy to augment the database and insert new attributes, as there is no pre-defined order.

3.  **a)**
    1.  **Data security:** relational databases allow for easy program permission handling (no different authoriz. for files)
    2.  **Data integrity:** foreign keys change data globally and prevent data abundance redundancy
    3.  **Augmentability:** due to the modular structure it's easy to create new relations or insert new attributes.
        - There is no predefined order for attributes which allows for insertion of new attributes
        - The format and exact data structure don't have to be known by the program
        - no dependency between DB and program
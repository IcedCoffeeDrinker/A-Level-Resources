*revisit*
# 8.3 Normalization (Database-related)
=> Restructure databases to reduce data redundancy

## Normal Forms
=> Describe the grade of optimization regarding data redundancy
- 1NF has lots of abundancy, 3NF is aimed for

### 1NF:
- All values (fields) are **atomic**, meaning that they hold only a single value, not a list.
- Each row has a **primary key**.

### 2NF:
- database fulfills 1NF
- **no partial dependencies of non-key attributes on composite primary keys**
	- ask yourself: could I identify this (non-key) attribute with only part of the composite primary key? -> move it to it's own new table
	- single primary key relations are automatically in 2NF

`Student Class Info (StudentID, ClassID, Grade, Teacher)`
*primary key (composite)*
> grade is dependent on student id and class id -> it's good
> teacher is only dependent on Class id -> it ain't good

`StudentClassInfo(StudentID, ClassID, Grade)`
`Class(ClassID, teacher)`
*foreign key*

### 3NF:
- database fulfills 2NF
- **non-key attributes don't contextually depend on any other non-key attributes**

`CharacterDescription(DescriptionID, described character, book title)` X
> `book title` depends on `described character`

`Character Description(DescriptionID, characterID)`
`Characters(CharacterID, character name, book title)`

Summarized:
3NF means each non-key attribute is dependent on the primary key, the whole primary key, and nothing but the primary key.

## Un-Normalized Data
=> Data is said to be 'un-normalized' if it contains repeating groups or straight up lists
e.g. `(CustomerID, Name, Phone number #1, Phone number #2)`
*repeating group*
- repeating groups are sets of attributes which represent similar data
> leads to data redundancy because not all customers have two phone numbers

## Exam Style 3.
a) Booking Number (non-repeating), hotel (non-repeating), date (non-rep.), Room type (repeating), number of rooms (non-rep.), room rate (non-rep.), address (rep.), rating (non-rep.)

b) `Booking(Booking Number, hotel(fk), date, room type, number of rooms, room rate)`
`Hotel(hotel, address, rating)`

c) The requirements for 2NF are that all values are atomic, there are no repeating groups, and no partial dependencies of non-key attributes on composite keys. As 1NF is already satisfied (at least when fixing the repeating groups formatting issue) and because there are no composite primary keys that could have any partial dependencies, the database is automatically 3NF.
Satisfies
# 10.1 Data Types & Records

## Primitive Data Types
*   ⇒ Basic pre-defined datatypes provided by programming languages
*   also known as 'atomic' data types

### Common Primitive Data Types:
*   Integer `42`
*   Real/Float `3.141`
*   Char `'H'`
*   Boolean `True`
*   (String `"Hello"`) debatable

## Structured Data Types
*   => Data types consisting of primitive data types
    *   Date `06/08/2007`
    *   String `"I love cake"`
*   ↳ string consists of many characters, date of integers
*   (There is some debate around strings being structured or primitive data types, e.g. imagine an empty array)

## Record Type
*   => A data structure that holds a collection of logically connected data of various data types
*   e.g. the data type 'person' might consist of birthday, height, weight, hair-color
*   in python the 'class' method is used

### Pseudocode:
```
TYPE BookType
    DECLARE Title, ISBN : STRING
    DECLARE Year_of_publication : INTEGER
    DECLARE Price: REAL
ENDTYPE

DECLARE new_book : BookType

new-book.Title ← "Computer science"
new-book.ISBN ← "S78..."
new-book.year_of_publication ← 2015
new-book.Price ← 44.95

OUTPUT new-book.Title

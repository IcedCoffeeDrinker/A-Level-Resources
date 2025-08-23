# 8.2 Entity-Relationship Modelling

=> Entity-relationship diagrams (E-R diagrams) are used to visualize which data is linked between different tables.

## Entity
- some concept that will become a table in a database
- e.g. a 'member', 'class', or a 'booking'
- entities might 'share' the same attributes through foreign keys
- e.g. Booking: band name and Band info: band name

## Stepwise Refinement
=> E-R diagrams use a top down approach:
1. broad relations are made between rather unspecific concepts (entities)
2. Entities and connections are repeatedly subdivided until they are specific enough to work efficiently in code

## ER-Diagram Syntax
=> relations between entities are called **Cardinalities** which have different symbols

### Preliminary (Undefined)
`[Member] --- [Band] --- [Booking] --- [Venue]`

## Cardinality Notation
> *the relations are between single entities of each table (relation)*
> *e.g. 1 band entity has many member entities*

=> At each end of the relation there is a maximum and a minimum defined:

`[Band] --||----------< [Member]`
- For Band side: `max: 1`, `min: 1`
- For Member side: `max: many (up to ∞)`, `min: many (more than one)`

### Building-blocks:
- `--<` many
- `--|--` one
- `--o--` zero

### Examples:
- `--o|--` zero or one: 1, 0
- `--o<--` zero to many: 0, 1, 2, ...
- `--|<--` one to many: 1, 2, 3, ...
- `--||--` one only: 1
- `<--` many to many (more than one): 2, 3, ...

## Types of Relationships
- one-to-one ($$1:1$$): `--||-----||--`
- one-to-many ($$1:M$$): `--||------<`
- many-to-one ($$M:1$$): `>-------||--`
- many-to-many ($$M:M$$): `>--------<`

## Problem with 'Many-to-Many' Relationships
=> $$M:M$$ relationships can't be implemented in databases, **link entities** are required.
- a foreign key can link a single attribute in one table with an attribute in one or many other tables (entities)
- a foreign key cannot link multiple attributes in one table with multiple attributes in an other table (entity)
- => the foreign key would lack an origin - a place where it is created first

`[Bands] >---------< [Bookings]`

## Solution: Link Entities
=> The linked entity can store the two foreign keys of the two entities. They both refer to the primary keys of the other entities:

| Bands                 | Band-Booking              | Bookings                |
| --------------------- | ------------------------- | ----------------------- |
| - Yoasobi, members    | - 1, Yoasobi, June 1st    | - June 1st, 4k$         |
| - Daft Punk, ...      | - 2, Daft Punk, March 2nd | - March 2nd, 10k$       |
| - Stoners, ...        | - 3, Yoasobi, April 5th   | - April 5th, 6k$        |
| (*primary key*)       | (*generated primary key*, *foreign keys*) | (*primary key*)         |

- the linked entity keeps track of all combinations

## Solution #2: Subdivide
=> Split many-to-many relations until they become $$1:1$$ or $$1:M$$

`[Bands] >---------< [Bookings]`
is transformed into
`[Bands] >----- [Summer Festival 2025] -----< [Bookings]`
(e.g. 30. June, 6th July, 9th July)

=> This might not always be possible, so remember link entities

---

## Exam Style
2. 6b

2. a) event, dishes, venue, staff
   b) venue-event, dishes-event, staff-venue
   c) 
      `[event] --||-----||-- [venue]` ?
      one event has one venue
      
      `[event] --||------< [dishes]` ?
      one event has multiple dishes

      `[staff] >------||-- [venue]` ?
      multiple staff members will be at a single venue

6. b) `[Member] --||-----< [Bookings] >-----||-- [Class]`
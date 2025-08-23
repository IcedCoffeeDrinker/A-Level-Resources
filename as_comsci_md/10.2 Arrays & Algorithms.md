# 10-2 Arrays & Algorithms

> An array is an ordered list of variables that all share the same datatype, stored under a single identifier.

## List* vs Array
- a list can store a mix of datatypes, an array can't
- Arrays store data more efficiently
- Arrays aren't native to python, lists are

\* note, Lists sometimes refer to 1D arrays but can also mean mixed-data-type-lists

## Array Technical Terms

`DECLARE new_array[0:10] OF INTEGER`
- `new_array` -> array identifier
- `[0:10]` -> `0` is the lower bound, `10` is the upper bound
- `OF INTEGER` -> data type for all elements is required
- The bound is inclusive, meaning `[0:10]` creates 11 values.

`new_array[2] <- 42`
- `[2]` -> array index

## 2D Arrays

`> DECLARE new_array[1:3, 1:5] OF BOOLEAN`
- `[1:3]` -> rows
- `[1:5]` -> columns

This defines a 3x5 grid where indexing starts at 1.

`> new_array[2, 3] <- TRUE`

## Algorithms

### Linear Search
> Compare each element of an array with a value until the matching value is found

`[1, 5, 7, 9, 0, 42]`
- `1=0? no` -> `5=0? no` -> `7=0? no` -> `9=0? no` -> `0=0? yes!` found at Index = ...

### Bubble Sort
> Sort numerical values in an array by comparing two numbers next to each other and switch them if the left is smaller. After each pass the array is reduced as the last place is certainly correct.

Initial: `1, 5, 3, 2`

**Pass 1:**
- `[1, 5], 3, 2` -> ok
- `1, [5, 3], 2` -> `1, 3, 5, 2` (swap)
- `1, 3, [5, 2]` -> `1, 3, 2, 5` (swap) -> We know for sure the five is largest.

**Pass 2:**
- `[1, 3], 2, 5` -> (five is not iterated over anymore)
- ... until a perfect run is completed (all values are in correct places)
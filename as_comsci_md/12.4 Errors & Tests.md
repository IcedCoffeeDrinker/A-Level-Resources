# 17.4 Errors & Tests

## Types of Errors
### Syntax Error:
> Program statement defies the rules of the programming language
- The compiler or interpreter won't understand the statement
    - a compiler can only compile syntax-error-free code
    - an interpreter will only stop when reaching a syntax error

### Run-Time Error:
> While executing, the program unexpectedly halts or crashes
- **Causes:**
    - memory overflow
    - access undefined variable
    - infinite loop floods RAM, freezes program
    - division by zero, etc...
- Run-Time Errors won't be flagged
    - Testing is required to uncover any errors

### Logic Error:
> The program doesn't do/output what is expected, due to a logical design flaw
- **Causes:**
    - Bad planning
    - Incompetence
- Logic Errors won't be flagged and don't throw errors on execution
    - Requires testing where output is compared with expected output

## Types Of Testing
### Stub Testing
stub trans. German = Stummel
> Functions and procedures are empty and contain print messages to acknowledge they were being called
- great for testing top logic in a program / GUI testing

### Black-Box Testing
> Someone without knowledge about the source code looks at the program specifications and designs test data + expected outputs.
#### Test Data
- Three types of test data will be created
    - Normal Data: Explicitly valid data a user might enter
    - Extreme/Boundary Data: checks minimums, maximums, including just-out-of-bound (invalid) values
    - Erroneous/Abnormal Data: Explicitly invalid data, tries to break code

### White-Box Testing
> The programmer creates tests that check every possible path through the code
- Data is selected so that:
    - all sides of the conditions are checked
    - every submodule gets executed

### Dry-Running
> Using a trace table to record all variable states the program is run through, line-by-line.
> All variable changes and outputs are recorded in the trace table

**Example:**
`x <- 2`
`FOR i <- 1 TO 3`
 `y <- x * i`
`NEXT i`
`OUTPUT y`

| x | i | y | Output |
|---|---|---|---|
| 2 |   |   |   |
|   | 1 | 2 |   |
|   | 2 | 4 |   |
|   | 3 | 6 |   |
|   |   |   | 6 |
*spaces are only filled on changes*

**Rules:**
- new row for each iteration
- new row for function/procedure call

## Stages Of Testing
### Module Testing (my addition)
- tests previously covered are used to check single modules

### Integrity Testing
> Checking if all modules work together by adding one module at a time and seeing if the program works as expected

### Alpha Testing
> Software will be tested in-house by software testers, before it's being released

### Acceptance Testing
- done when a program is developed for a specific customer (e.g. company)
> Customer checks if the software meets all requirements
> If successful, software will be signed off

### Beta Testing
> Software released to the general public is first released to a limited audience of "beta testers"
> The released "beta version" will collect feedback and problem reports
    - Most problems will be patched by the time of the official release

## Test Strategy
> A test strategy is required to ensure the product is rigorously tested

### Create Test Plan
> Strategically create a plan with tests to run that will find as many errors as possible and explore wide parts of your system
> Start with an outline test plan and get very specific in a detailed test plan

### Test Data
> Based on the test plan design data sets of input values and expected outputs in a table
> More about the three test data categories above under "Black-Box Testing"

## How to minimize errors
- use existing libraries
- commonly accepted algorithms and design techniques
    - e.g. object-oriented-programming

---

## Exam Style #1, 2
1.  a)
    i. returns "1011"
    ii. returns "101"
    
    b) The first dry run runs successful, as 11 = 1011 in binary
    The second dry run fails, 10 is 1010, but 101 is returned
    Currently the program stops early, as soon as the last one has been written. Therefore 1010 is shortened to 101.
    **Fix:** Stop when last place value is written instead
    `UNTIL Number=0`
    -> `UNTIL PlaceValue=0`
2. 
| Type | Test Data | Reason for test data | Expected output |
|---|---|---|---|
| Normal | 1<br>5<br>20 | Some normal entries testing a range of likely entered values | /// <br> ///// <br> ///// ///// ///// ///// |
| Boundary | 0<br>-1<br>3000 | 0: Testing what happens if the lowest valid number is entered <br> -1: Testing a number just out of range <br> 3000: Testing an unexpectedly high value | empty line <br> empty line <br> ///...<br>*(showing out of bounds)* |
| Abnormal | 'a'<br>3.5 | Testing if program can handle wrong data types.<br>Testing if program is robust enough to deal with reals | empty line <br> empty line |
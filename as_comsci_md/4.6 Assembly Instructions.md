# 4.6 Assembly Instructions

## Types of Addressing: (recap of 4.5)
- **Immediate Addressing:** operand is value
    - e.g. `LDD #4`
- **Direct Addressing:** operand holds the memory address for data used
    - e.g. `LDD VARIABLE` or `LDD 216`
- **Indirect Addressing:** Holds an address that holds a usually larger address which holds the data used
    - e.g. `LDD VARIABLE` or `LDD 216` (same)
- **Indexed addressing:** operand is an offset of the value currently stored in the index register (IX)
    - -> e.g. `LDD 5`
- **Relative Addressing:** operand gives address relative to its own instruction position. (Positive is down, own instruction not counted)
    - -> e.g. (line 5) `LDD 5` -> data from line 10 loaded

## Instructions
! Conflict with previous page

### Data movement
| Opcode | Operand | Description |
|---|---|---|
| `LDM` | `#denary-value` | Loads number into ACC | immediate |
| `LDD` | `<address>` | Loads number into ACC | direct |
| `LDR` | `#denary-value` | Loads number into IX | immediate |
| `LDI` | `<address>` | Loads value at address to ACC | indirect |
| `LDX` | `<address>` | Loads value to ACC | indexed |
| `MOV` | `<register>` | `<register>` <- [ACC] |
| `STO` | `<address>` | stores value of ACC to address |

### Input & Output
| Opcode | Operand | Description |
|---|---|---|
| `IN` | (no operand) | stores the next ASCII character typed on a keyboard to ACC |
| `OUT` | (no operand) | displays the value in the ACC as ASCII on the screen (assumes value is ASCII code)|

### Comparisons and Jumps
| Opcode | Operand | Description |
|---|---|---|
| `JMP` | `<address>` | jumps to the instructions at the given address |
| `CMP` | `<address>` | compares contents of ACC with contents at address |
| `CMP` | `#denary-value` | compare value of ACC with number |
| `CMI` | `<address>` | compares contents of ACC with contents at second (indirect) address |
| `JPE` | `<address>` | following a compare instruction, if True, jump to address |
| `JPN` | `<address>` | following a compare instruction, if False, jumps to address |
| `END` | ✓ | returns the control to the operating system |

### Arithmetic Operations
| Opcode | Operand | Description |
|---|---|---|
| `ADD` | `<address>` | adds value at address to value at ACC |
| `ADD` | `#denary-value` | adds value to value at ACC |
| `SUB` | `<address>` | subtracts value at ACC by value at address |
| `SUB` | `#denary-value` | subtracts value at ACC by value |
| `INC` | `<register>` | increments either ACC or IX |
| `DEC` | `<register>` | decrements either ACC or IX |

## Shift Operations
| Opcode | Operand | Description |
|---|---|---|
| `LSL` | `#n` | Bits in ACC shifted left by n bits, most significant bit stored in carry bit in status register |
| `RSL` | `#n` | Bits in ACC shifted right by n bits, LSB saved as carry bit in status register (SR) |

! empty bit is replaced by a zero, but bit to move out becomes carry?

e.g. `ACC: 1011` `LSL #2`
`ACC: 1100` carry: 0

### Multiply / Divide by two
- unsigned binary numbers can be multiplied/divided by two
- **multiply**: shift left by one (MSB must be '0'!)
- **divide**: shift right by one (remainder can be found in carry bit)

### Cycle shift
- The bit that got pushed out moves into the carry and reemerges on the other end in the next step

ACC: `1011` -> ACC: `0110`
carry: `0` -> carry: `1`

-> ACC: `1101`
-> carry: `0`

### Arithmetic Shifts
- Basically logical shifts but specifically intended for multiplication and division by two
- -> carry bit always stored, unlike for some logical shifts

## Bitwise Logic Operations
| Opcode | Operand | Description |
|---|---|---|
| `AND` | `#Bn` / `<address>` | Contents of ACC compared with binary value or value at address. |
| `XOR` | `#Bn` / `<address>` | |
| `OR` | `#Bn` / `<address>` | all can be used with two operands or with one and the ACC |
| `NOT` | (`#Bn` / `<address>`) | (<- not in book) |

- Logic operators are sometimes called a 'mask' as they may only affect specific bits
  - -> consider `1110000` OR `0001110`

### Operations with multiple bits:
```
  00011    AND
  00110
= 00010
```

Note!:
```
  00011    AND
    110
```
*not allowed* in most assembly languages
**length has to match!**

## Status Flag Naming Convention
| Flag | Name | Description |
|---|---|---|
| Z | zero flag | -> was the result zero? |
| N | negative flag | -> was the result negative? |
| C | carry flag | |
| V | overflow flag | |
| I | interrupt flag | |
|...|...|...|

## Trace Tables
- help to understand actions of a program or test for mistakes in a dry run

### Rules:
- for each column of the program a matching row
- columns are individual memory addresses
- a value is only entered when it is new
- if there are jumps, then the program counter is also traced!

### Example:
#### Problem
```assembly
100: LDD 200
101: INC ACC
102: ADD 201
103: CMP 202
104: JPE 106
105: DEC ACC
106: INC ACC
107: STO 203
```
```
200: 0001
201: 0011
202: 0101
203: 
```
*on purpose*

*currently executing line 99, 100 is next*

| PC | 200 | 203 | line executed (not required) | |
|---|---|---|---|---|
| 100 | 0001 | | 99 | |
| 101 | | | 100 | <-- program starts here |
| 102 | | | 101 | |
| 103 | 0010 | | 102 | |
| 104 | 0101 | | 103 | |
| 106 | | | 104 | <-- JPE evidently overrides PC |
| 107 | | | 106 | *value persists but isn't shown* |
| 108 | | 0110 | 107 | *bc it stays the same* |

## Exam Style Practice
**1. a) i**
`LDD 103`
```
       Address   Data
          .
          .
          .
Accumulator   103       110
  | 110 | <----copied----'
```
**ii** `110`

**b) ii** `112`

**c) ii** `104`

**2. b)** ✓

**4. a) i.**
`LDX 60`
$$
IX = 0000\ 1000 \quad (8, 4, 2, 1)
$$
$$
IX = \#8
$$
`LDD 60 + 8`
`LDD 68`
```
{ 68: 0100 0101
  ACC: 0100 0101
```

**ii.**
`IX: 0000 1000`
`IX: 0000 0111`
|-1
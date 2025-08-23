# 3.4 Boolean Logic

## Logic proposition:
A statement that is either true or false
e.g. 5 is larger than 2; TRUE

## Problem Statement:
A construct of one or multiple logic propositions connected to each other
e.g. If it rains and I don't have an umbrella, I'll be wet

## Boolean operators:

| Operator | Notation |
| :--- | :--- |
| AND | $$AB$$ |
| OR | $$A+B$$ |
| NOT | $$\bar{A}$$ |
| NAND | $$\overline{AB}$$ |
| NOR | $$\overline{A+B}$$ |
| XOR | $$A \oplus B = \bar{A}B+A\bar{B}$$ |

- A AND B = TRUE if A=TRUE and B=TRUE
- A OR B = TRUE if A=TRUE or B=TRUE
- NOT A = TRUE if A=FALSE
- A NAND B = TRUE if A=FALSE or B=FALSE
- A NOR B = TRUE if A=False and B=False
- A XOR B = TRUE if A=TRUE or B=TRUE but not both of them

## Logic expressions:
An equation made up of logic propositions and boolean operators

AND, OR, NOT can make up every logic composition

## Truth tables

TRUE = 1
FALSE = 0

Convention: Variables: A, B,... Result: x
_also count binary: 00, 01, 10, 11..._

x = A AND B ($$x = AB$$)

| A | B | x |
| :--: | :--: | :--: |
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

## Logic Gates & Circuits

Logic Gate: represents a boolean operation in circuit form.

### NOT
| A | x |
| :--: | :--: |
| 0 | 1 |
| 1 | 0 |

### AND
| A | B | x |
| :--: | :--: | :--: |
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

### OR
| A | B | x |
| :--: | :--: | :--: |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

### NAND
| A | B | x |
| :--: | :--: | :--: |
| 0 | 0 | 1 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

### NOR
| A | B | x |
| :--: | :--: | :--: |
| 0 | 0 | 1 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 0 |

### XOR
| A | B | x |
| :--: | :--: | :--: |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

## Task 4.01
Covered by copyright $$\equiv A$$
Permission obtained $$\equiv B$$
Can be copied $$\equiv x$$

$$ x = \text{NOT A OR (A AND B)} $$
$$ x = \bar{A} + AB $$

## Task 4.02
| A | B | x |
| :--: | :--: | :--: |
| 0 | 0 | 1 |
| 0 | 1 | 1 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

## Exam-style questions

### 1a)
i) Gate 1: OR
Gate 2: AND
Gate 3: NOT

ii) Gate 1 OR

| A | B | x |
| :--: | :--: | :--: |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

### 2a) NAND:
| A | B | x |
| :--: | :--: | :--: |
| 0 | 0 | 1 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

## Worked examples

A B C D
$$ A \text{ AND } [(B \text{ AND } C) \text{ OR } (B \text{ AND } D) \text{ OR } (C \text{ AND } D)] = x $$

## How to solve datatables from circuits:

- define helper points (M, N, P, Q) to determine complex logic circuits.

_Inputs: A, B, C | Workspace: M, N, P, Q | Output: x_
| A | B | C | M | N | P | Q | x |
| :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
| 0 | 0 | 0 | 0 | 1 | 1 | 0 | 0 |
| 0 | 0 | 1 | 0 | 1 | 1 | 0 | 1 |
| 0 | 1 | 0 | 0 | 0 | 1 | 0 | 0 |
| 0 | 1 | 1 | 0 | 0 | 1 | 0 | 0 |
| 1 | 0 | 0 | 0 | 1 | 0 | 1 | 0 |
| 1 | 0 | 1 | 1 | 1 | 0 | 1 | 1 |
| 1 | 1 | 0 | 1 | 0 | 0 | 0 | 0 |
| 1 | 1 | 1 | 1 | 0 | 0 | 0 | 0 |

_way faster_

- Note: When just the solution (which combination) is asked for, not the table, then you can take 10x shortcuts. E.g. note how C has to be '1'? This throws out half of the combinations.

## Task 4.03
| A | B | x |
| :--: | :--: | :--: |
| 0 | 0 | 1 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

_same for both_

## Task 4.04
$$ C \text{ AND } ((\text{NOT } B) \text{ OR } (\text{NOT } A)) $$

## Exam Style Questions Round #2

### 2b)
i, A $$\equiv$$ won match #1
ii, B $$\equiv$$ won match #2
C $$\equiv$$ have higher score
_Different interpretation_

$$ (A \text{ AND } B) \text{ OR } (A \text{ AND } C) \text{ OR } (B \text{ AND } C) = x $$

_might need to split up_

### 1b) i
| A | B | C | #1 | #2 | #3 | x |
| :--: | :--: | :--: | :--: | :--: | :--: | :--: |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 0 | 0 | 0 | 0 |
| 0 | 1 | 0 | 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 | 0 | 1 | 1 |
| 1 | 0 | 0 | 0 | 0 | 0 | 0 |
| 1 | 0 | 1 | 0 | 1 | 0 | 1 |
| 1 | 1 | 0 | 1 | 0 | 0 | 1 |
| 1 | 1 | 1 | 1 | 1 | 1 | 1 |

### 1b) ii
If C is TRUE x will always be TRUE. Therefore the AND gate comparing C and B is redundant. _(2/2)_

### 3. a)
$$ C = \text{FALSE AND } B = \text{FALSE} $$

| A | B | C | x |
| :--: | :--: | :--: | :--: |
| 0 | 0 | 0 | 1 |
| 0 | 0 | 1 | 0 |
| 0 | 1 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 0 | 1 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 0 |
| 1 | 1 | 1 | 0 |

_(\✓) book is different but still correct? xD_

### 3. b)
$$ B=1 \text{ AND } A=0 \text{ AND } C=0 $$

_(\✓) ?_
_still not wrong?!_

### 4. a)
# 4.9 Bitwise Operations

Control systems often use closed feedback loops where a program checks for a combination of flags set by a sensor. Bit manipulation is used to interpret those signals.

**TL;DR:** control systems use flags set by sensors

Flags are set by assigning statements.
This is the syntax (pseudo):
```
IF SensorDifference > 0 THEN SensorHighFlag <- TRUE
IF SensorDifference < 0 THEN SensorHighFlag <- FALSE
```
Flags might be stored in the first few bits of an operand or in a designated byte.

## Bit Manipulation on Flags
use: OR, AND, XOR, NOT

- `AND #B 0000` <- delete all bits
- `OR #B 0010` <- set flag regardless of previous state
- `XOR #B 0100` <- Toggle flag (0 -> 1; 1 -> 0)

**Check if Flag is up**
- `AND #B 0010` <- isolate Flag in ACC
- `CMP #B 0001` <- compares ACC with content at address 0001

---

## Exam-Style Tests

```
ACC = 0101
XOR #B 1100
ACC = 1001
```
XOR actually flips all bits where the operand contains a 1

2, 3c, 4

2.
   a) `AND #B0000 0000`
   b) `XOR #B0000 0100` / `OR #B0000 0100`
   c) `XOR #B0011 0000`

3c)
   i. The 1 in the bit at location 5 indicates that the measurement is from location 5. That the bit in location 0 is 1 means that the measurement has been processed.
   ii.
      ```
      0 | 00 0000 | 11111011
      ```
      ```
      -5
      5:  00000101
      -9: 11110111
      
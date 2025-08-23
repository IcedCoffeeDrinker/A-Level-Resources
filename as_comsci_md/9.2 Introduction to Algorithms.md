# 9.2 Introduction to Algorithms

## Flowchart Rules for Algorythms
- **Input / Output**
    - Represented by a parallelogram.
- **Decision**
    - Represented by a diamond, with "Yes" and "No" branches.
- **Process**
    - Represented by a rectangle.
- **Start / Stop**
    - Represented by an oval or rounded rectangle.
- **Loop**
    - Indicated by arrows forming a cycle.

## Algorithm Definition
A sequence of steps to solve a problem in a finite amount of time.

---

## Example 1: Miles to Kilometers Conversion
```
12.01
DECLARE distance: Integer
INPUT "Enter a distance in miles: " distance
distance ← distance * 1.61
OUTPUT "Distance in km is:" distance
```
**Flowchart:**
- **Start**
- INPUT "Enter distance in miles": distance
- distance ← distance * 1.61
- OUTPUT "Distance in km is:" distance
- **End**

---

## Example 2: Symbol Pyramid
**Flowchart:**
- **Start**
- INPUT "Symbol:": symbol
- INPUT "Odd value:": value
- **Process (Initialization):**
    - DECLARE symbolNumber: INTEGER
    - symbolNumber ← 1
    - DECLARE newLine: STRING
    - DECLARE increment: INTEGER
    - increment ← 0
- **Loop Start:**
    - **Process (Loop Body):**
        - newLine ← ((symbolNumber - 1) / 2 - increment) * " "
        - newLine ← newLine + symbol * symbolNumber
        - symbolNumber ← symbolNumber + 2
        - increment ← increment + 1
    - OUTPUT newLine
    - **Decision:** Is `symbolNumber > value`?
        - **No:** Return to **Loop Start**.
        - **Yes:** Continue.
- **Stop**

---

## Number Guessing Game
**Flowchart:**
- **Start**
- INPUT "Enter the secret number:": secretNumber
- **Process (Initialization):**
    - DECLARE guessCounter: INTEGER
    - guessCounter ← 0
- **Loop Start:**
    - INPUT "Enter your guess:": guess
    - guessCounter ← guessCounter + 1
    - **Decision 1:** Is `guess = secretNumber`?
        - **Yes:** Proceed to correct guess output.
        - **No:** Proceed to **Decision 2**.
    - **Decision 2:** Is `guess > secretNumber`?
        - **Yes:** 
            - OUTPUT "The number is lower"
            - Return to **Loop Start**.
        - **No:**
            - OUTPUT "The number is higher"
            - Return to **Loop Start**.
- OUTPUT "Correct, you guessed this often:" guessCounter
- **End**

---

## Exam-Style Questions
```
5  9  1  6  ...
10 9  8  7  ...
```

$$
(5 \times 10 + 9 \times 9 + 1 \times 8 + 6 \times 7 \dots) \text{ MOD } 11 = y
$$

$$
11 - y = \text{check digit}
$$

$$
\text{if } 11 - y = 10 \text{ then checkdigit} = 'X'
$$

$$
\text{if } 11 - y = 11 \text{ then checkdigit} = 0
$$
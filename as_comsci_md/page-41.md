# 12.2 Structured Charts
> A graphical representation of the modular structure of a solution

> Shows how modules are connected together through shared variables called "parameters"

## Syntax

### Pyramid structure
- Level 0
  - Doesn't execute anything itself
- Level 1
- Level 2
- Execution is left-to-right

**Legend**
- A rectangle represents a module.
- A line represents a call to a module.

### Conditions
- A diamond shape is used for conditional logic.
- e.g., A diamond with the condition `$value = value?$` has two branches: `True` and `False`.

### Loops
- A loop is represented by a curved arrow over the connections it affects, with a condition.
- e.g., `main` module loops `UNTIL value > 42` over the calls to `Input value`, `Increment value`, and `Output value`.
- The loop iterates over the connections it intersects with.

### Variables
- An arrow with an open circle at the end shows a variable being passed.
- Arrow pointing down: `pass variable to layer below`
- Arrow pointing up: `pass variable to layer above`
> Variable passing is called an "interface"

> Interface between modules

### Flags (aka Control Flow)
- A variable name enclosed in `< >` represents a flag.
- `$$<variable>$$` => used when variable is a flag (true/false)
- Example: `INPUT` module passes `name` to `check if valid` module, which returns the flag `$$<IsValid>$$`.

### Modify passed value
- A double-headed arrow with a filled-in circle at each end shows that a value is passed, modified, and returned.
- Example: `counter` module passes `index` to the `increment` module, which modifies it and sends it back.
- This indicates a value is passed to a module, modified, and then sent back.

---

## Full Example
**Connect 4**
- Main loop: `WHILE game not finished`
- **Modules called:**
  1.  `Initialize Board`
      - Outputs: `Board`
  2.  `Set up Game`
      - Inputs: `Board`
      - Outputs: `GameState`, `Player`
  3.  `Player makes move`
      - Inputs: `board`
      - Outputs: updated `board`, `gamestate`
  4.  `Check game finished`
      - Inputs: `board`, `gamestate`
      - Outputs: updated `gamestate`

---

See page 292

> There are no stop nodes, all modules are expected to return the process to the top level after completion

> Modularization improves the program's stability, as modules are self-contained
> → changes in one module won't affect another

---

## Tasks

### 15.01
**Convert**
1.  `INPUT distance in km`
    - Outputs `km`
2.  `Convert km to miles`
    - Inputs `km`
    - Outputs `miles`
3.  `OUTPUT miles`
    - Inputs `miles`

### 15.02
**login**
- **Loop:** `while tries < 3 AND IsValid = FALSE`
    1.  `INPUT UserID`
        - Outputs `userID`
    2.  `INPUT Password`
        - Outputs `Password`
    3.  `Check UserID Password combination`
        - Inputs: `userID`, `Password`
        - Outputs: `IsValid` (flag)
    4.  `Increment tries`
        - Inputs/Outputs: `tries`
- **Post-Loop Logic:**
  - **Condition:** `Is IsValid?`
    - **True:** `OUTPUT Correct`
  - **Condition:** `Is tries=3?`
    - **True:** `OUTPUT warning`

---

## Example
**3. a)**
- **A:** Initiate tally array
- **B:** generate random number
- **C:** (value to increment) `randomNumber`
- **D:** tally
- **E:** frequency table `tally`

**b)**
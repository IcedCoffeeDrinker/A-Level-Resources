# 4.4 Machine Code & Assembly

*   CPU only recognizes machine code (binary)
*   machine code consists of a sequence of instructions
*   Instructions must contain an 'opcode', i.e. an operator
*   Instructions can include zero to three operands
*   Instruction sets are specific to their processor type
*   Instructions for different processors will be similar, but their machine code looks different

This must be defined for each individual machine code instruction:
*   length in bits/bytes of entire instruction
*   number of bits for the opcode
*   number of operands (they cover all remaining bits)
*   is opcode in the front or in the back?

e.g.
| Opcode | | | Operand |
| :--- | :--- | :--- | :--- |
| **4 bits** | **2 bits** | **2 bits** | **16 bits** |
| operation | Address mode | Register addressing | |

❗note: it's good if the operand length and the address bus width match, as the operand might be an address
TL;DR: Operand width = address bus length

## Decoding + register transfer notation
*   after the instruction arrived at the current instruction register (CIR), the opcode part is transferred to the control unit (CU) and decoded:
    $$CU \leftarrow [CIR(23:16)]$$
*   bits 16 to 23 are copied, denoted by (:)
    (note that 23 is first)

## Assembly Language
*   writing machine instructions is the most efficient at runtime but virtually impossible for serious development
*   assembly is a low-level language strongly tied to the actual machine code. Opcodes are written as short abbreviations. (as mnemonics)
    *   -> machine code is specific to the processor
    *   -> assembly tool is specific to the processor
*   for each machine code instruction there is an equivalent machine code instruction

## What Assembly Adds
*   Comments: makes the program more comprehensive
*   macros: like functions, abbreviations for entire code snippets
    *   -> snippet is copy-pasted to all locations by assembler
*   directives: directions for the assembler, e.g on how to handle memory, or how to compile something
*   subroutines: basically functions, during runtime the program will jump to a different code snippet and then return
*   system calls: when the program requests services from the system
    *   -> e.g. writing to a screen, reading files or exiting the program
*   symbolic names for variables (if wanted)
*   denary and hex-representation of variables
    *   -> #49 ; #B1001 ; #&H5C7
    *   # = value
    *   B = binary
    *   & = Hex
*   Assembler:
    *   The compiler that converts the already rather specific assembly code to even more specific machine code (specific to the processor that is)

## Programming Languages in Perspective

machine code (binary) -> Assembly -> High-level Languages (e.g. C, Python)
<br>
abstraction ------------------------------>

## Types of conversion
*   translator
    *   -> converts from one language to another
*   compiler
    *   -> a translator that converts from a high- or low-level language into machine code
*   assembler
    *   -> a compiler specifically translating from assembly into machine code

## Types of Addressing
### Symbolic addressing:
Data locations are referenced by variable names, e.g. 'TOTAL'.
*   -> the programmer doesn't have to worry about the actual location where the data is stored.

### Absolute addressing:
*   Data locations match their actual memory address
    *   -> all variables are numbers, which are usually rather long and incomprehensible e.g. 245782

### Relative addressing:
*   a special-function base register (BR) is loaded with the base address, which is the address of the first instruction (which is 0)
*   All other addresses are given relative to the base address
    *   -> numbers are significantly smaller and easy to comprehend
    *   -> program is independent from its location but control over memory placement is maintained.

Examples for all three can be found on p. 34f.

## How a Two-Pass Assembler works
*   used to handle programs with recursion or symbols
    *   -> symbols or functions might be referenced that weren't read yet
*   The assembly code is read line-by-line

**First pass:**
- removal of comments
- replacement of macros by code snippets
- removal and storage of directives (to be implemented later again)
- creation of a symbol table (resolving forward references)

### Use of symbol tables:
| Symbol | Offset |
| :--- | :--- |
| Symbol 1 | + 15 |
| Symbol 2 | + 13 |
| ... | ... |

*   On the first pass a symbol table is filled with all variable names encountered
*   the address (might be absolute, usually relative) is added to the table when encountering the symbol value
*   On the second pass:
    *   - the symbol table and an opcode lookup table are used
        *   -> opcodes are replaced by binary
        *   -> all symbols are replaced by binary addresses

## Memory in Runtime
*   empty storage spaces should be reserved for all variables
*   if the memory is being loaded into memory to be executed, changes to the addresses will have to be made

## Addressing Mode
*   two bits of the opcode are allocated to the addressing mode.
    *   -> this allows for four modes:

### Immediate:
The operand is the exact value used for the instruction
*   -> e.g. SUB #48
*   -> There are three options to define this address
    *   - #49 : denary value 48
    *   - #B00110000 : binary equivalent of 48
    *   - #&30 : hexadecimal 48

### Direct:
The operand is an address that refers to the data that should be used for the operation
*   e.g. SUB AGE or SUB 517

### Indirect:
The operand stores an address at which a second address is stored. The data at the second address is then used for the operation.
*   -> this allows for larger addresses further out in the system to be used

### Indexed:
similar to relative addressing: the address is given relative to a base address stored in the index register (IX)

---
## Exam Style Questions 2a, 3
**2c)**
*   Macros: Act as a sort of function where a snippet of code is referenced at multiple locations
*   Comments: Help to make the code more understandable
*   Directives: Give instructions on how the code should be compiled, memory addresses should be handled, or etc.

**3a)** The program takes inputs from a keyboard

**b)** no idea, haven't done

**c)**
| Label | Value | Binary |
| :--- | :--- | :--- |
| CHARACTER | 10 | -> 1010 |
| START | 84 | -> 0100 |
| OUTPUT | ??? didn't do | -> 0111 |

count from 0 bro
also the table is always in binary
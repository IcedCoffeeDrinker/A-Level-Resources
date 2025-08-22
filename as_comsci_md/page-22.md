# 5.3 Compilers & Interpreters

## Interpreter
*   Source code is compiled at runtime
    *   ↳ code gets translated and then executed, for every line
    *   ↳ if an error occurs / is found, the program halts immediately
*   code is translated into **intermediate code**: e.g. assembly or byte code
    *   ↳ (not machine code!)
*   Both source-code and interpreter are needed at runtime
    *   => code has to be re-interpreted for every execution
    *   ↳ generally slower at runtime, faster for development

## Compiler
*   reads program line by line and converts it to **intermediate code**
*   if an error is found it's recorded, program continues
    *   ↳ compiler spits out list with all errors at the end
*   If no errors occurred, intermediate code is converted to object code.

### On runtime
*   program is extremely fast
*   only compiled machine code needed
    *   => source code and compiler aren't needed
    *   => source code stays secret

**Object code**: Platform specific machine code that has yet to be linked with files, libraries or other object code, and made executable.

**Intermediate Code**: Low-Level platform-independent code which is not yet fully executable (e.g. Bytecode)

## Interpreter Pro-Con
+ fast for development; errors found fast
- errors are only found at execution of the faulty line of code
- the source code has to be shared with all users
- the interpreter is required to run the program

## Compiler Pro-Con
+ the executable can be distributed on its own
+ source code stays secret
+ only the object code required
+ faster on runtime
- less secure as it might contain hidden viruses
- slower at development -> recompile again for every error

## Java
*   Java is extra :)
*   source code is converted to universal 'Java byte code'
*   byte code is interpreted by system-specific 'Java Virtual Machine'
    *   => Java byte code works for all Java VMs

## IDEs
Integrated Development Environment
### Prettyprinting:
*   more comprehensible code representation that automatically occurs?
    - color-coding
    - formatting, etc

### Content-Sensitive Prompts:
*   code recommendation
*   autocomplete
*   2025 edit: vibe coding x)

### Dynamic Syntax Checks:
### Expanding & collapsing code blocks
### Debugging support
*   => breakpoints: program stops when reached
*   => line-by-line execution (manual)
*   => examine current program state -> variables, etc.

---

## Exam Style 3, 4
### 3. a)
An assembler exclusively translates **assembly code** to machine code, while Interpreters and Compilers translate **high-level languages** to intermediate or object code.

### b) i
| Interpreter | Compiler |
| --- | --- |
| * Compiles at runtime<br>* Stops when encountering an error<br>* requires source code and interpreter at runtime<br>* produces intermediate code | * compiles to an executable first *(doesn't execute)*<br>* creates a list with all errors found<br>* Only requires object code to execute the program<br>* produces object code *(a form of intermediate code lol?)* |

### ii
+ Interpreter is faster during development -> errors found fast
- errors only found when specific line is executed
- slower at runtime as it is compiled while being executed
- Interpreter and sourcecode are needed to execute the program

### iii
A Java Virtual Machine is used. *(to run the code)*

### 4. a)
*   **Prettyprinting**:
    - automated color coding
    - comprehensible text formatting (automatic indentation)
*   **Context-sensitive prompts**:
    - code completion and recommendation (at current insertion point)
*   **Dynamic Syntax Check**
    - IDE checks for syntax mistakes (constantly)! *after a line has been typed*
*   **Debugging**
    - The process of finding *and correcting!* mistakes in the code, often assisted by tools offered through the IDE

### b)
*   **Breakpoints**: markers that allow the program to be stopped at a specific line
*   **manual line-by-line execution**: The coder can cycle through every line manually.
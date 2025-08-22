# 4.1 Central Processing Unit
The CPU controlls manipulation of data
CPU = Processor

## CPU Architecture:
### Arithmetic/Logic Unit (ALU)
- performs all calculations/operations

```
+-----------------------------------+
|         ALU       |    Registers  |
+-----------------------------------+
|               CU                  |
+-----------------------------------+
```

### Registers
- super-high speed close stores of data inside the CPU

### Control Unit (CU)
- coordinates all activities of the CPU
- checks that instructions are handled correctly

## Von Neumann Architecture:
- all modern computers are based on this architecture

```
<-- System Bus -->
+-------------+      +-----------------+      +---------------+
| Main Memory | <--> | ALU             | <--> | Input/Output  |
+-------------+      |                 |      +---------------+
                     | CU              |
                     +-----------------+
                         (CPU)
```

- both data and instructions are stored together = stored program concept
- Instructions are executed sequentially -> one instruction at a time is fetched from memory and executed
- von Neumann bottleneck refers to the issue that a bus as fast as the CPU is required
- Computers use a system clock to syncronize circuits
    -> not time but delivers a constant pulse `_|-|_|-`
    -> located on motherboard
- Each instruction takes a certain amount of cycles/ticks

## Fetch - Execute Cycle:
### Fetch:
CPU retrieves next instruction from main memory

### Decode:
The instruction is broken down into smaller components
- what operation should be done
- which data should be used

Operator, operands: `ADD R1 R5` / R5 is read and placed into R1

### Execute:
- CU activates required circuits for data transfer and the operation inside the ALU
- The output is stored in a register
- Data might be read/written to/from main memory

If the clockspeed is higher, this cycle happens faster

## General Purpose Registers:
Registers which can be used by programmers. If there is only one general purpose register, it has to be the ACC. This is only in simple CPUs.

### Accumulator (ACC):
- holds the result of an operation performed by the ALU

## Special Purpose Registers
### Program Counter (PC):
- holds the memory address for the next instruction (highly important)
- increments after being fetched (usually)
- usually instructions are being stored sequentially, not always

### Memory Address Register (MAR):
- stores the memory address of the data which the CPU needs to access

### Memory Data Register (MDR):
(aka MBR (B=buffer)) (memory buffer register)
- holds data which is being transfered between CPU and memory location
(Note: MAR and MDR are linked)

**When reading:** data at the address in MAR is stored to MDR
**When writing:** data inside the MDR is stored to the address in MAR
-> might seem redundant *BUT*... act as buffer registers and compensate for different speeds of CPU and RAM

### Current instruction register (CIR):
- stores current instruction while it's being decoded and executed

### Index Register (IX):
- holds a single value that describes a relative range of addresses, starting from a base address that is stored somewhere else.
    -> used for 'Index addressing'

### Status Register (SR):
- stores single bits of helpful data that helps the CPU make decisions
- e.g. "the result is negative == 1", or "overflow == 0"
- consists of multiple bits where each bit is considered a boolean **Flag**, and each bit has a predetermined meaning.
    - result is zero
    - negative
    - overflow
    - interrupt

> [!NOTE]
> All special purpose registers, except status register contain **one value only**

## More Accurate CPU Architecture

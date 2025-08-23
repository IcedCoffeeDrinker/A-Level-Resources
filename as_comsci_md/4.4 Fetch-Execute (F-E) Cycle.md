# 4.4 Fetch-Execute (F-E) Cycle

## The Fetch-Execute Cycle Flowchart
1.  **START**
2.  **Check**: Any instructions to execute?
    *   **NO**: Loop back to check again.
    *   **YES**: Proceed to Fetch.
3.  **Fetch**: Fetch next instruction.
4.  **Decode**: Decode instruction.
5.  **Execute**: Execute instruction.
6.  **Check for Interrupts**: Any interrupts to be processed?
    *   **NO**: Loop back to step 2 (Check for instructions).
    *   **YES**: Transfer control to interrupt handling program, then loop back to step 2 (Check for instructions).

---

## Example when program already running: 
(each point one cycle)
*   (Program counter already stored next address)
*   address from PC copied to MAR
*   At the same time:
    *   data at address in MAR is fetched into MDR
    *   PC is incremented
*   Instruction stored in MDR is transferred to CIR
*   Instruction is interpreted by CU and ALU might be activated if arithmetic is involved

## Note:
*   The system clock is used, as data from outside the processor is fetched.
*   PC isn't always simply incremented: e.g. when there is a 'jump' instruction then an entirely different address might be loaded.

## Register transfer notation
*   describes operations between registers
*   e.g. the fetch part of the F-E cycle

$$MAR \leftarrow [PC]$$
$$PC \leftarrow [PC] + 1; MDR \leftarrow [[MAR]]$$
$$CIR \leftarrow [MDR]$$

## Notation:
*   first item is data destination
*   abbreviations are used (e.g. MAR)
*   second item is the data's definition (where it came from)
*   square brackets indicate a register's data is being moved
*   arrow underlines flow of data
*   tasks separated by a semicolon happen at the same time
*   The double brackets mean that not the address in MAR but the data at the address in MAR is being transferred.

## Interrupt handling
*   some reasons for interrupts:
    *   fatal error
    *   user interaction
    *   need to start I/O processing
    *   a timer signal
    *   hardware fault
*   interrupts have different priorities
*   some interrupts will erase the current process, others just pause it
*   a way for the processor to identify the type of interrupt would be an 'interrupt register' (IR)
    *   -> works similar to status register with flags.

### how interrupts are handled:
*   content of program counter and other registers saved to memory
*   an 'interrupt service routine' (ISR) is chosen according to the problem.
    *   -> start address loaded into PC
*   at end of execution, check if there are still other interrupts
*   further interrupts are processed
*   if no interrupts, load original data from memory, resume

---

# Exam-style questions: 3, 4b,c,d, 5

### 3. a)
On the left there is the destination. On the right is the data description (from where it is transferred). The arrow underlines the flow of data. Single brackets mean that the information of the register in brackets is being moved. Double brackets mean that the data stored at the address which is located in the register is transferred. A semicolon dividing two operations in the same row indicates that they occur simultaneously.

First the address stored in the PC (Program counter) is transferred to the MAR (memory address register). Then the PC is incremented while the data stored at the address inside the MAR is transferred to the MDR (memory data register). Finally the data from the MDR is loaded on to the CIR (current instruction register).

### b)
When data is fetched from the address stored inside the MAR, the address bus is used to send the according address to a memory controller. The memory controller responds with the matching data and sends it over the data bus to the CPU. MRD

### 4. b)
i. The address stored in the program counter gets incremented.
ii. The data at the address stored in the memory address register gets copied into the memory data register.
iii. The instruction stored in the memory data register gets copied to the current instruction register.

### c)
not in chapter? LDD 35 loads address 35 into MAR, the whole F-E cycle follows -> data stored at the address is loaded into the accumulator.

### d)
i. An interrupt is a **signal** which causes a pause in the current process that allows for multiple programs running at once, despite the fact that only one process can be executed at a time.
    *   pause the program

ii. 
1. Store register content to memory
2. Identify the interrupt and load the matching interrupt service program
3. Execute the ISR
4. Immediately check if any more interrupts are waiting
5. Resolve any other interrupts
6. load back original memory into registers

### 5.
**Program counter**: holds the next address to be fetched
*   address is loaded into MAR
*   contents of the address is stored to MDR; Program counter is incremented
*   data is copied from MDR to CIR

---

1. B ✅
2. D, A, C ✅
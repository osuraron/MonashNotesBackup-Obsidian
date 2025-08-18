###### **CPU**
- **AC (Accumulator)** – A single general-purpose register used for arithmetic and logic operations.
    
- **IR (Instruction Register)** – Holds the current instruction being executed.
    
- **MAR (Memory Address Register)** – Holds the address in memory that is being accessed (for read/write).
    
- **MBR (Memory Buffer Register, sometimes MDR)** – Holds the data being transferred to/from memory.
    
- **PC (Program Counter)** – Holds the address of the next instruction to fetch.
    
- **InREG (Input Register)** – Holds input data from input devices.
    
- **OutREG (Output Register)** – Holds data ready to be sent to output devices.
    
- **Control Unit** – Directs the operation of all components, including instruction decoding and sequencing.
    
- **ALU (Arithmetic Logic Unit)** – Performs arithmetic and logical operations, using the AC as input/output.
![[Pasted image 20250817231927.png]]
The **Control Unit** connects everything.
- Responsible for executing the program  
- Switches all other components on/off according to individual instructions

- **PC → MAR → MBR → Memory** handles instruction/data fetch.
- **IR** decodes instructions.
- **AC + ALU** process data.
- **InREG/OutREG** handle I/O.

**Registers**
- Very fast memory inside the CPU 
- Store temporary results 
- Help move data around (from/to memory and I/O)

So there are **7 registers** in MARIE.
- AC (Accumulator) -*16 bits*
- IR (Instruction Register) - *16 bits*
- MAR (Memory Address Register) - *12 bits*
- MBR (Memory Buffer Register / MDR) -*16 bits*
- PC (Program Counter) -*12 bits*
- InREG (Input Register) -*16 bits*
- OutREG (Output Register) -*16 bits*
 
Both **instructions and data are 16 bits (2 bytes)** long in MARIE.
    
- An instruction is split into:
    - **4-bit opcode** (operation code)
    - **12-bit address field** (operand)

So memory can hold **16-bit words**.

The **Control Unit** and **ALU** are _not registers_ — they are functional units.  
The **Memory** is also separate (main memory, not part of CPU registers).
*Each memory location holds 16 bits*

![[20250817_213245.jpg]]
**Interpreter and Compiler**

- An interpreter is a program (usually machine code) that directly executes a high-level program.
- A compiler is a program that translates programs from a higher level language into a lower level language

**Clock Speeds**

- This time is determined by the clock  
- An *oscillator circuit*: output constantly changes from 0 to 1 and back 
- Each such change is called a clock cycle 
- Number of cycles per second: Hertz (Hz) 
- Typical clock speeds: billions of cycles per second (GHz)
###### **Fetch–Decode–Execute Cycle**
###### The **Fetch–Decode–Execute (FDE) cycle** describes how the CPU processes instructions step by step:
---
###### 1. **Fetch**

- The CPU fetches (reads) the next instruction from memory.
- The **Program Counter (PC)** holds the address of this instruction.
- That address is copied into the **MAR**, the memory is accessed, and the instruction is placed in the **MBR**.
- The instruction is then moved into the **IR (Instruction Register)**.
- The **PC** is incremented to point to the next instruction.
---
###### 2. **Decode**

- The **Control Unit** looks at the instruction in the **IR**.
- It separates the **opcode** (what operation to do) from the **operand** (the address/data to use).
- The CPU now knows whether this is, for example, a `LOAD`, `ADD`, `STORE`, or `JUMP` instruction.
---
###### 3. **Execute**

- The CPU carries out the decoded instruction:
    
    - If it’s an **arithmetic instruction** (e.g. `ADD`), the **ALU** performs the operation using the **AC (Accumulator)**.
    - If it’s a **memory instruction** (e.g. `LOAD` or `STORE`), the **MAR** and **MBR** are used to fetch or write data.
    - If it’s an **I/O instruction**, data moves between the **InREG / OutREG** and the **AC**.
    - If it’s a **branch instruction** (e.g. `JUMP`), the **PC** is updated to a new address.

**Steps (Fetch–Decode–Execute)**

```cpp
//Fetch
1. MAR ← PC //load PC into memory address register 
2. MBR ← M[MAR] //load value from memory (M) into memory buffer register 
3. IR ← MBR //load value from MBR into instruction register 
4. PC ← PC+1 //increment PC to point at next instruction
//Encode
5. MAR ← X //load address X from IR into MAR 
6. MBR ← M[MAR] //load value from memory into MBR
//Execute
7. AC ← AC + MBR //place result of addition in AC
```

**Control Signals and RTL (Register Transfer Language)** 
- Each RTL step determines which control signals to switch on and off.

**Von Neumann Architecture**

![[Pasted image 20250818231833.png]]

8 KB 
4 KW

Assume, you have a computer with opcode using 8 bits and the address field is 24 bits long. How many instructions are there in this computer’s ISA? What are the total memory addresses this computer can have or can handle?

2^24
=256 opcode



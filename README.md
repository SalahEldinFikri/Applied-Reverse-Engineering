# Compilation Process in c
# The Compilation Process
The compilation process in C transforms a human-readable code into a machine-readable format. For C programming language, it happens before a program starts executing to check the syntax and semantics of the code. The compilation process in C involves four steps: pre-processing, compiling, assembling, and linking then, we run the obtained executable file to get an output on the screen.
![image](https://user-images.githubusercontent.com/71356170/215872181-1b360ca8-529e-474a-a842-8937c294192e.png)


## Compilation process in C involves four steps:
### 1- Preprocessing.
### 2- Compiling.
### 3- Assembling.
### 4- Linking.
![image](https://user-images.githubusercontent.com/71356170/215872816-d5236044-9d64-43ab-93c9-dfa26ce7aa6f.png)


## The Microarchitecture
A microarchitecture (sometimes written as "micro-architecture") is the digital logic that allows an instruction set to be executed. It is the combined implementation of registers, memory, arithmetic logic units, multiplexers, and any other digital logic blocks. All of this, together, forms the processor.

A microarchitecture combined with an instruction set architecture (ISA) makes up the system's computer architecture as a whole. Different microarchitectures can implement the same ISA, but with trade-offs in things like power efficiency or execution speed. The most basic processor will include a register file, an ALU, system memory, and a control unit that allows the processor to make decisions based on the instruction it's executing.

## The ARM Register File
To perform operations on data, there needs to be a place to temporarily store that data. This is what a processor's register file is for. The register file is a bank of registers that are used to store temporary values and perform actions on those values. Outside of the registers, data can be retrieved and stored in the computer's memory. While this is a slower operation, far more can be stored out in memory than in the relatively few registers available. The register file usually comes in the form of SRAM.

Let's use a 32-bit ARM core as an example. In this case, we will focus on 32-bit ARMV7 instructions and 32-bit registers. 

A 32-bit, or four-byte, quantity corresponds to a word in the ARM instruction set. The ARM register file contains sixteen registers used to execute instructions. A status register also exists to store information about the results of an operation and allow the processor to make decisions based on that result.

##Register Denotations
A register is denoted with the letter R and a number.

- R0–R3 are used to store temporary values or variables, but also play a role during subroutine calls.
- R4–R12 are general purpose.
- R13, or SP, is the stack pointer. The stack pointer contains a memory address where the program can store information that it will need to retrieve later.
- R14 is the link register, used with branching instructions to return to a previous spot in the program.
- R15, called PC for program counter, stores the address of the next instruction to be executed. This gives the PC a huge responsibility, as it controls what instruction executes on the processor. Put the wrong value in the PC and your program could suddenly stop running; this is usually referred to as a crash.

## Register Flags
The current program status register (CPSR), mentioned earlier, contains a number of flags that can be set when an instruction executes.

These flags are the N, Z, C, and V flags:

- N stands for negative and is used when the result of an instruction is negative.
- Z for zero, is set when the result is zero.
- C stands for carry and is set when the instruction results in a carry out.
- V stands for overflow and is set when an overflow occurs.

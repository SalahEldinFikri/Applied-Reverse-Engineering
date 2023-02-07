# Compilation Process in c
## The Compilation Process
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


# Stack
To understand this concept of stack we need to understand the memory organization of computer. So any process of program which is loaded in to the memory of the computer is not loaded randomly it has some precise area dedicated in memory for its operations. For example, global hard code which is written for the program is resides at particular location and environmental variables have different location it memory lay out.

I won’t dive in to detail of memory lay out here instead I will try to explain a very simple overview of the memory layout here as per below image.

![image](https://user-images.githubusercontent.com/71356170/216231285-6f279d3f-c982-4422-a630-aa215dc546b7.png)


So as you can see in figure 1 lower memory region of the program contains DATA section and HEAP section, while upper or higher memory region contains KERNEL and STACK section, Now let’s take a look of these each section briefly (stack in detail of course….. -_- )

DATA: Also know and text section and code section where the actual text is copied in to the memory. It contains the all logic and the instruction for the code. It’s placed below heap to protect it from over-writing.

HEAP: Heap is a segment where the dynamic allocation of the memory take place. This region is managed by functions like malloc(),alloc() & free(). Its grows upward i.e. from lower memory to higher memory.

KERNEL: Now this area dedicated to the kernel of the operating system where command line arguments, thread and processes resides.

Now, after seeing this we know where exactly the stack is in the memory. Stack resides just below kernel segment and above the free area and stack always grow downward towards heap. Keep this in mind, stack always written from higher memory to lower memory

To write this computer take help of two 64-bit register BSS (Base Stack Segment) & RSP (Stack Pointer Register) in more precise way we can say that BSS manages the RSP. Two important instructions are use to manipulate stack are PUSH and POP. PUSH is use to put data in to the stack and POP is use to retrieve data from the stack.

Here we need to understand that last pushed values are always top of the stack like demonstrated in below image.

![image](https://user-images.githubusercontent.com/71356170/216231322-f879e461-2af8-4b1b-831f-688ac408ab64.png)


Here we have two instructions

PUSH 44

PUSH 88

First push will put data 44 on the top of the stack at this time RSP is pointing at the highest location of the stack let say it’s just RSP+0 I have called it RSP, now as second push instruction is executed it put data 88 on the top of the stack and now is decremented by 8 bytes and new RSP will point at the RSP+8 which is now the top of the stack, here you can see stack is growing downwards and last pushed value is at top of the stack.


# Exceptions And Interrupts

An exception is a problem that arises during the execution of a program. A C++ exception is a response to an exceptional circumstance that arises while a program is running, such as an attempt to divide by zero.

Exceptions provide a way to transfer control from one part of a program to another. C++ exception handling is built upon three keywords: try, catch, and throw.

throw − A program throws an exception when a problem shows up. This is done using a throw keyword.

catch − A program catches an exception with an exception handler at the place in a program where you want to handle the problem. The catch keyword indicates the catching of an exception.

try − A try block identifies a block of code for which particular exceptions will be activated. It's followed by one or more catch blocks.

Assuming a block will raise an exception, a method catches an exception using a combination of the try and catch keywords. A try/catch block is placed around the code that might generate an exception. Code within a try/catch block is referred to as protected code, and the syntax for using try/catch as follows −

![image](https://user-images.githubusercontent.com/71356170/217266376-841653c5-dada-49ca-a8a8-863b86ffcb37.png)

You can list down multiple catch statements to catch different type of exceptions in case your try block raises more than one exception in different situations.

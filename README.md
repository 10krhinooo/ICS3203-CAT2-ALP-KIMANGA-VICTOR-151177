# ICS3203-CAT2-ALP-KIMANGA-VICTOR-151177
## Task 1: Classifying Numbers as Positive, Negative, or Zero

### Overview
This program is an assembly implementation that prompts the user to input a number, processes the input, and classifies it as either positive, negative, or zero. The program demonstrates basic integer operations, string handling, and system calls in Linux assembly using NASM.

---

### Instructions for Compiling and Running

1. *Prerequisites*:
   - A Linux environment.
   - NASM assembler and the ld linker installed.

2. *Steps to Compile and Run*:
   - Open a terminal and navigate to the directory containing the assembly code q1.asm.
   - Assemble the code :
     bash
     ~ nasm -g -f elf q1.asm
     
   - Link the object file :
     bash
     ld -m elf_i386 -g -o q1 q1.o
     
   - Run the program:
     bash
     ./q1
     
   - Enter an integer when prompted. The program will display whether the number is POSITIVE, NEGATIVE, or ZERO.

---

### Insights and Challenges

#### Insights:
- System Calls for I/O: Demonstrates the use of sys_write and sys_read for user interaction, showcasing basic input and output handling in Linux assembly.
- Control Flow: Efficiently classifies input using conditional and unconditional jumps (je, jne, jmp), emphasizing logical flow in assembly programming.
- Character Encoding: Highlights the need to understand ASCII-to-integer conversion for accurate user input processing.

#### Challenges Encountered:
1. *Input Conversion*:
   - Initially encountered difficulties converting input strings to integers. This was resolved by implementing proper ASCII-to-integer logic, subtracting the ASCII value of '0'.

2. *Special Case Handling*:
   - Accurately classifying zero required additional checks to prevent misclassification as positive or negative.
     
# Task 2: Reverse Array Program

## Overview

This program reverses an array of 5 user-inputted numbers. It takes the numbers as input, reverses the array in place using assembly language, and then prints the reversed array.

## Instructions for Compiling and Running

### Steps to Compile and Run:

1. *Assemble the code*:
   - Open a terminal and navigate to the directory containing task2.asm.
   - Assemble the code using NASM:
     bash
     nasm -g -f elf q2.asm
     
   
2. *Link the object file*:
   - Link the object file using the ld linker:
     bash
     ld -m elf_i386 -g -o q2 q2.o
     

3. *Run the program*:
   - Run the program:
     bash
     ./q2
     

The program will prompt you to enter 5 numbers, reverse the input array, and display the reversed array.

### Insights

-The Insights Manual Array management makes use of pointer-based strategies; effective in-place array reversing is made possible by source (esi) and destination (edi) pointers.
-Low-Level I/O: Uses Linux system calls for input and output; its arguments and behaviour must be understood.
-Direct Memory Manipulation: Draws attention to the accuracy needed when processing characters and arrays straight from memory.


###Challenges
-Pointer Complexity: While handling pointers for array traversal and reversal added challenges, it also emphasised how crucial memory management is.
-Input Format Sensitivity: Accurate formatting was necessary to prevent errors when interpreting input as ASCII characters.


## Task 3: Factorial Calculation Program

### Overview

This program calculates the factorial of a user-inputted number.

The program relies on Linux system calls to handle input/output and demonstrates fundamental concepts like recursion, integer-to-string conversion, and system call usage in assembly.

### Instructions for Compiling and Running

1. *Assemble the code*:
   - Open a terminal and navigate to the directory containing task3.asm.
   - Assemble the code using NASM:
     bash
      nasm -g -f elf q3.asm
     

2. *Link the object file*:
   - Link the object file using the ld linker:
     bash
      ld -m elf_i386 -g -o q3 q3.o
     

3. *Run the program*:
   - Run the program:
     bash
     ./q3
     

   The program will prompt you to enter a number, calculate the factorial of the number, and display the result.

### Insights 

-Recursive logic uses stack-based function calls and management to implement recursion for factorial calculations.
-For assembly display, the Integer-to-String Conversion example shows how to convert integers to strings step-by-step.
-System Interaction: Uses Linux system calls for input and output to demonstrate the usefulness of low-level OS interactions.

###Challenges
- *Stack Management*: To guarantee that intermediate values were maintained and to avoid overflow, recursion necessitated exact stack management.
- *Manual Conversion* : It was difficult to convert integers to ASCII characters for output, and multi-digit figures needed precise mathematics.



## Task 4: Water Level Sensor and Motor Control Program

### Overview

This assembly program simulates a water level sensor and controls a motor and alarm based on the sensor's value. The program is designed to:

1. Prompt the user to enter a sensor value (simulating a water level).
2. Convert the input from ASCII to an integer.
3. Control a motor and alarm based on the water level:
   - *Low water level (value < 2)*: Turns the motor off and displays a "low" water level message.
   - *Moderate water level (value between 2 and 5)*: Turns the motor off and displays a "moderate" water level message.
   - *High water level (value > 5)*: Turns the motor off and triggers the alarm with a "high" water level message.
4. Handles invalid inputs (non-numeric or out-of-range values).

The program uses Linux system calls for input/output operations and demonstrates basic concepts like memory management, integer conversion, and conditional branching in assembly.

---

### Instructions for Compiling and Running

1. *Assemble the code*:
   - Open a terminal and navigate to the directory containing task4.asm.
   - Assemble the code using NASM:
     bash
      nasm -g -f elf q4.asm
     

2. *Link the object file*:
   - Link the object file using the ld linker:
     bash
      ld -m elf_i386 -g -o q4 q4.o
     

3. *Run the program*:
   - Run the program:
     bash
     ./q4
     
### Insights and Challenges

### Insights
1. *System-Level I/O*: Uses Linux system calls to handle input and output to show how to communicate with the operating system.
2. *Input Validation* : Highlights the significance of verifying unprocessed user data and manual ASCII-to-integer conversion.
3. Using conditional jumps to provide a structured control flow, branching logic efficiently controls operations based on water level thresholds.


### Challenges
1. *Single-Digit Input Restriction*: The program only accepts single-digit values (0–9), limiting its ability to handle more complex inputs.
2. *Memory Access Risks*: Manual memory handling increases the risk of errors, such as incorrect reads or writes.
3. *Debugging Difficulties*: Debugging low-level assembly and system calls is intricate and requires detailed analysis.

# Documentation Of The *6503 CPU*

- This is the *6503 CPU* it i a cpu deigned a a experiment to find and tinker with a combinations of allot of architectures. in thei ducmentation we will cover

## INDEX
- Introduction

- Architecture

- Fundamentall Principles

- Intruction set

- Memory Map

- 6503 Assembly

- 6503 Assembly Assembler

- External Pinout

- Example Code

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Introduction

- This is the intro to the 6503 CPU's design 
- I Eshaan Godbole Will take you on the journey of the 6503 CPU
- I watched some ben eat er videos and tought the 6502 CPU is very difficult like you have to conform everything to that CPU so i wanted to create my own CPU to cater to the needs i want hence the conception of the 6503 CPU
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Architecture

- The CPU fundamentally is a 16 bit processor because all registers and the maximum value that can be processed is 16 bits but not all the busses are 16 bit

- lets talk about the busses in a bit more detail

- Their are 4 busses the system usses
    - Data Bus (16 bits)
    - Adress Bus (16 bits)
    - Instruction Bus (32 bits)
    - ROM Bus (13 bits)

- the purpose of having 4 busses it that Instructions can be accepted and addressed seperately the advantage of this is smoother transition and less clock cycles are involved.

- The process works like this 
    1. ROM adress bus is controlled bu clock counter the adress is loaded
    2. Data is fetched and put on the Instruction BUS
    3. If the instruction involves and externel adress adress nbus is usssed
    4. if the output or input then the data bus is ussed

- Now we will talk about the CPUs memory.
- The CPU has 8KB of internel SRAM which can be trreated as ROM and one more sectoin of 4KB treated as RAM
- the CPU does not have any cache as theri is no speed advantage  Nor does the CPU have a stack memory 

- Now we will Come to the two main part the deffinning one of the CPUs architecture
- The CPU relies on Processes it functions by ussing processes
- The CPU has 8 process P0-7

- they are in a heirachical order where P0 attains the most power and P7 the least 
- when the CPU starts executing code it is signalled via the P7 process is enabled by deffault The P7 process executes code from `$0000 - $2000` where rom space is 

- where as the other Processes can be programmed and enabled since P6 has a higher order that p7 you can enable it with the adresses to read the first 1 kb of code.

- a process can be interrupted or killed by disablling it you kill the process where as when interrupting it you enable a higher order process to take its place to function.

- the difference is a interrupt allows the process to countinue where it is left of where killing it forcess a restrts from the starting point

- Now let us discuss how to use them 

- Returning to main body 
    - say you have jumpped to another process by interupting P7 then you want to go back keep in mind the only way to do this is by killing the process since p7 is the lowest either you have to wait for all qued process to finish or kill the all

- 

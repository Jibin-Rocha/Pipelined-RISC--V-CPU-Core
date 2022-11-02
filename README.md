# Pipelined-RISC--V-CPU-Core
The following repository contains all the information and codes that's needed to a build a 4-stage Pipelined RISC-V Core which is designed during the RISC-V MYTH Workshop. The core supports the RV32I Base Integer Instruction Set. It is developed and implemented in TL-Verilog on Makerchip platform
# Table of Contents
* [Introduction to RISC-V ISA](#introduction-to-risc-v-isa)
* [GNU Compiler Toolchain](#gnu-compiler-toolchain)


































# Introduction to RISC-V ISA 
* RISC-V is an open standard instruction set architecture (ISA) based on established RISC principles. Unlike most other ISA designs, RISC-V is provided under open source licenses that do not require fees to use. A number of companies are offering or have announced RISC-V hardware, open source operating systems with RISC-V support are available, and the instruction set is supported in several popular software toolchains.
* The base RISC-V ISA has fixed-length 32-bit instructions that must be naturally aligned on 32-bit boundaries. However, the standard RISC-V encoding scheme is designed to support ISA extensions
  with variable-length instructions, where each instruction can be any number of 16-bit instruction parcels in length and parcels are naturally aligned on 16-bit boundaries.
* As a RISC architecture, the RISC-V ISA is a load–store architecture. Its floating-point instructions use IEEE 754 floating-point. Notable features of the RISC-V ISA include instruction bit field locations chosen to simplify the use of multiplexers in a CPU, a design that is architecturally neutral, and most-significant bits of immediate values placed at a fixed location to speed sign extension
* In the base RV32I ISA, there are four core instruction formats (R/I/S/U). All are a fixed 32 bits in length and must be aligned on a four-byte boundary in memory.

# GNU Compiler Toolchain
The GNU toolchain is a broad collection of programming tools produced by the GNU Project. These tools form a toolchain (a suite of tools used in a serial manner) 
used for developing software applications and operating systems. Toolchain is simply a set of tools used to compile a piece of code to produce an executable program (TL Verilog in our case). 
Similar to other ISAs, RISC-V also has its own toolchain.

Mentioned below are steps to use RISC-V toolchain,

  * Command to use the risc-v gcc compiler:

    `riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o <object filename> <C filename>`
    here the -o refers to the output and the object filename which is automatically created afte running this command.

    Different available options for the command:

    `riscv64-unknown-elf-gcc <compiler option -O1 ; Ofast> <ABI specifier -lp64; -lp32; -ilp32> <architecture specifier -RV64 ; RV32> -o <object filename> <C      filename>`
* Command to view the assembly code:
    
    `riscv64-unknown-elf-objdump -d <object filename>`
    
  * Command to use SPIKE simualtor to run risc-v obj file:
  
    `spike pk <object filename>`
    
    Command to use SPIKE as debugger:
    
    `spike -d pk <object Filename>` with degub command as `until pc 0 <pc of your choice>`
     By using this until command we can perfoem a line by line execution of the assembly code.
     

**Outputs for the above mentioned commands**
*sum from 1 to 5
1[](
     
     

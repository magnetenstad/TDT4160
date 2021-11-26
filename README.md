
# Notes from STRUCTURED COMPUTER ORGANIZATION SIXTH EDITION

Based on Odd Runes *TDT4160 Haust 2021 Pensum og
stikkord*.

Note: this will only include information which is regarded as "non-trivial".

# Table of contents
<!-- @import "[TOC]" {cmd="toc" depthFrom=1 depthTo=6 orderedList=false} -->

<!-- code_chunk_output -->

- [Notes from STRUCTURED COMPUTER ORGANIZATION SIXTH EDITION](#notes-from-structured-computer-organization-sixth-edition)
- [Table of contents](#table-of-contents)
- [General principles](#general-principles)
  - [1.1 Structured computer organization](#11-structured-computer-organization)
  - [2.1 Processors](#21-processors)
    - [2.1.2 Instruction execution](#212-instruction-execution)
    - [2.1.3 RISC vs CISC](#213-risc-vs-cisc)
    - [2.1.4 Design principles for modern computers](#214-design-principles-for-modern-computers)
    - [2.1.5 Instruction-level parallelism (ILP)](#215-instruction-level-parallelism-ilp)
      - [Pipelining](#pipelining)
      - [Superscalar architectures](#superscalar-architectures)
    - [2.1.6 Processor-level parallelism](#216-processor-level-parallelism)
      - [Data parallel computers](#data-parallel-computers)
      - [Multiprocessors](#multiprocessors)
      - [Multicomputers](#multicomputers)
  - [2.2 Primary memory](#22-primary-memory)
    - [2.2.5 Cache memory](#225-cache-memory)
      - [Locality principle](#locality-principle)
      - [Mean access time](#mean-access-time)
  - [2.3 Secondary memory](#23-secondary-memory)
    - [2.3.1 Memory hierarchies](#231-memory-hierarchies)
  - [2.4 Input and output (IO)](#24-input-and-output-io)
    - [2.4.1 Buses](#241-buses)
      - [Interrupt handler](#interrupt-handler)
      - [Bus arbiter](#bus-arbiter)
- [Digital logic level](#digital-logic-level)
  - [Sekvensiell logikk, kompendium på BB](#sekvensiell-logikk-kompendium-på-bb)
  - [3.1 Gates and boolean algebra](#31-gates-and-boolean-algebra)
  - [3.2 Basic digital logic circuits](#32-basic-digital-logic-circuits)
    - [3.2.2 Combinational circuits](#322-combinational-circuits)
      - [Multiplexers](#multiplexers)
      - [Decoders](#decoders)
    - [3.2.3 Arithmetic circuits](#323-arithmetic-circuits)
      - [Adders](#adders)
        - [Half adder](#half-adder)
        - [Full adder](#full-adder)
        - [Ripple carry adder](#ripple-carry-adder)
    - [3.2.4 Clocks](#324-clocks)
  - [3.3 Memory](#33-memory)
    - [3.3.2 Flip-flops](#332-flip-flops)
    - [3.3.3 Registers](#333-registers)
    - [3.3.6 RAMs and ROMs](#336-rams-and-roms)
      - [SRAM vs DRAM](#sram-vs-dram)
  - [3.4 CPU chips and buses](#34-cpu-chips-and-buses)
    - [3.4.2 Computer buses](#342-computer-buses)
      - [Bus protocol](#bus-protocol)
    - [3.4.3 Bus width](#343-bus-width)
      - [Multiplexed bus](#multiplexed-bus)
    - [3.4.4 Bus clocking](#344-bus-clocking)
      - [Synchronous buses](#synchronous-buses)
      - [Asynchronous buses](#asynchronous-buses)
    - [3.4.5 Bus arbitration](#345-bus-arbitration)
    - [3.4.6 Bus operations](#346-bus-operations)
  - [3.7 Interfacing](#37-interfacing)
    - [3.7.2 Address decoding](#372-address-decoding)
- [Microarchitecture level](#microarchitecture-level)
  - [4.2](#42)
  - [4.3](#43)
  - [4.4](#44)
  - [4.5](#45)
  - [8.1](#81)
- [Instruction set architecture level (ISA)](#instruction-set-architecture-level-isa)
  - [5.1](#51)
  - [5.3](#53)
  - [5.4](#54)
  - [5.5](#55)
  - [5.6](#56)
  - [7.1](#71)
  - [7.3](#73)
- [Virtual memory](#virtual-memory)
  - [6.1](#61)

<!-- /code_chunk_output -->

# General principles

## 1.1 Structured computer organization

| Level | Description
|---|---|
|5|Problem-oriented language level
|4|Assembly language level
|3|Operating system machine level (OS)
|2|Instruction set architecture level (ISA)
|1|Microarchitecture level
|0|Digital logic level

Note that the following sections (after *General principles*) are dedicated to the bottom three levels, starting with level zero.

## 2.1 Processors

### 2.1.2 Instruction execution
1. Fetch the next instruction from memory into the instruction register.
2. Change the program counter to point to the following instruction.
3. Determine the type of instruction just fetched.
4. If the instruction uses a word in memory, determine where it is.
5. Fetch the word, if needed, into a CPU register.
6. Execute the instruction.
7. Go to step 1 to begin executing the following instruction.

This sequence of steps is frequently referred to as the fetch-decode-execute cycle. It is central to the operation of all computers.

### 2.1.3 RISC vs CISC
We love RISC but there is the issue of backward compatibility and the billions of dollars companies have invested in software for the Intel line (CISC) 🥵.

RISC|CISC
---|---
Few, simple and generic instructions|Many, complex and specialized instructions
Register-to-register, LOAD/STORE-architecture| Memory-to-memory, load/store incorporated in instructions
Few cycles per instruction|Many cycles per instruction

### 2.1.4 Design principles for modern computers
- All instructions are directly executed by hardware
- Maximize the rate at which instructions are issued
- Instructions should be easy to decode
- Only loads and stores should reference memory
- Provide plenty of registers

These are sometimes called the RISC design principles.

### 2.1.5 Instruction-level parallelism (ILP)
Parallelism is exploited within individual instructions to get more instructions per second out of the machine.
#### Pipelining
`TODO`

#### Superscalar architectures
`TODO`

### 2.1.6 Processor-level parallelism
Multiple CPUs work together on the same problem.

####  Data parallel computers
`TODO`

#### Multiprocessors
`TODO`

#### Multicomputers
`TODO`

## 2.2 Primary memory
`TODO: introduction`

### 2.2.5 Cache memory
`TODO`

#### Locality principle
- Temporal locality
- Spatial locality

#### Mean access time
Let $c$ be the cache access time, $m$ the main memory access time, and $h$ the hit ratio. We can calculate the mean access time as follows:
$$t_{mean} = c + (1 - h)m$$


## 2.3 Secondary memory
`TODO: introduction`

### 2.3.1 Memory hierarchies
`TODO: draw rectangle`

## 2.4 Input and output (IO)

### 2.4.1 Buses

#### Interrupt handler
A controller that reads or writes data to or from memory without CPU intervention is said to be performing *Direct Memory Access* (DMA). When the transfer is completed, the controller normally causes an *interrupt*, forcing the CPU to immediately suspend running its current program and start running a special procedure, called an *interrupt handler*, to check for errors, take any special action needed, and inform the operating system that the I/O is now finished. When the interrupt handler is finished, the CPU continues with the program that was suspended when the interrupt occurred.

#### Bus arbiter
What happens if the CPU and an I/O controller want to use the bus at the same time? The answer is that a chip called a bus arbiter decides who goes next. In general, I/O devices are given preference over the CPU, because disks and other moving devices cannot be stopped, and forcing them to wait would result in lost data. When no I/O is in progress, the CPU can have all the bus cycles for itself to reference memory.

# Digital logic level

## Sekvensiell logikk, kompendium på BB
`TODO: take a look`

## 3.1 Gates and boolean algebra
Regarded as trivial.

## 3.2 Basic digital logic circuits

### 3.2.2 Combinational circuits

#### Multiplexers
A multiplexer is a circuit with $2^n$ data inputs, one data output, and $n$ control inputs that select one of the data inputs.

#### Decoders
A decoder is a circuit that takes an $n$-bit number as input and uses it to select (i.e., set to $1$) exactly one of the $2^n$ output lines.

### 3.2.3 Arithmetic circuits

#### Adders

##### Half adder
A half adder takes two 1-bit inputs $A$ and $B$ and outputs $S$, the sum of the inputs, and $C$, the carry bit. It is built from one AND-gate and one XOR-gate. 

##### Full adder
A full adder takes three 1-bit inputs $A$, $B$ and $C_{in}$, (carry in) and outputs $S$, the sum of the inputs, and $C_{out}$, the carry bit. It is built from two half adders.

##### Ripple carry adder
To build an adder for, say, two 16-bit words, one just replicates the full adder 16 times. The carry out of a bit is used as the carry into its left neighbor. The carry into the rightmost bit is wired to 0. This type of adder is called a *ripple carry adder*, because in the worst case, adding 1 to 111...111 (binary), the addition cannot complete until the carry has rippled all the way from the rightmost bit to the leftmost bit. Adders that do not have this delay, and hence are faster, also exist and are usually preferred.

### 3.2.4 Clocks
Regarded as trivial.

## 3.3 Memory

### 3.3.2 Flip-flops
`TODO`

### 3.3.3 Registers
`TODO`

### 3.3.6 RAMs and ROMs
`TODO`

#### SRAM vs DRAM
`TODO`

## 3.4 CPU chips and buses

### 3.4.2 Computer buses
`TODO`

#### Bus protocol
`TODO`

### 3.4.3 Bus width
`TODO`

#### Multiplexed bus
`TODO`

### 3.4.4 Bus clocking
`TODO`

#### Synchronous buses
`TODO`

#### Asynchronous buses
`TODO`

### 3.4.5 Bus arbitration
`TODO`

### 3.4.6 Bus operations
`TODO`

## 3.7 Interfacing
`TODO`

### 3.7.2 Address decoding
`TODO`


# Microarchitecture level

## 4.2

## 4.3

## 4.4

## 4.5

## 8.1

# Instruction set architecture level (ISA)

## 5.1

## 5.3

## 5.4

## 5.5

## 5.6

## 7.1

## 7.3

# Virtual memory

## 6.1


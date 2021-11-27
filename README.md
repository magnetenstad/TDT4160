
# Notes from STRUCTURED COMPUTER ORGANIZATION SIXTH EDITION

Based on Odd Runes *TDT4160 Haust 2021 Pensum og
stikkord*.

Note: this will only include information which is regarded as "non-trivial".

This document is hosted at [magne.dev](https://magne.dev/TDT4160)

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
      - [Cache design](#cache-design)
  - [2.3 Secondary memory](#23-secondary-memory)
    - [2.3.1 Memory hierarchies](#231-memory-hierarchies)
  - [2.4 Input and output (I/O)](#24-input-and-output-io)
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
  - [4.2 An example ISA: IJVM](#42-an-example-isa-ijvm)
    - [4.2.1 Stacks](#421-stacks)
    - [4.2.2 The IJVM memory model](#422-the-ijvm-memory-model)
    - [4.2.3 The IJVM instruciton set](#423-the-ijvm-instruciton-set)
  - [4.3 An example implementation](#43-an-example-implementation)
    - [4.3.1 Microinstructions and notation](#431-microinstructions-and-notation)
    - [4.3.2 Implementation of IJVM using the mic-1](#432-implementation-of-ijvm-using-the-mic-1)
  - [4.4 Design of the microarchitecture level](#44-design-of-the-microarchitecture-level)
    - [4.4.1 Speed versus cost](#441-speed-versus-cost)
    - [4.4.2 Reducing the execution path length](#442-reducing-the-execution-path-length)
    - [4.4.3 A design with prefetching: the mic-2](#443-a-design-with-prefetching-the-mic-2)
    - [4.4.4 A pipelined design: the mic-3](#444-a-pipelined-design-the-mic-3)
    - [4.4.5 A seven-stage pipeline: the mic-4](#445-a-seven-stage-pipeline-the-mic-4)
  - [4.5 Improving performance](#45-improving-performance)
    - [4.5.1 Cache memory](#451-cache-memory)
    - [4.5.2 Branch prediction](#452-branch-prediction)
  - [8.1 On-chip parallelism](#81-on-chip-parallelism)
    - [8.1.1 Instruction-level parallelism (ILA)](#811-instruction-level-parallelism-ila)
    - [8.1.2 On-chip multithreading](#812-on-chip-multithreading)
- [Instruction set architecture level (ISA)](#instruction-set-architecture-level-isa)
  - [5.1 Overview of the ISA level](#51-overview-of-the-isa-level)
    - [5.1.1 Properties of the ISA level](#511-properties-of-the-isa-level)
    - [5.1.2 Memory models](#512-memory-models)
    - [5.1.3 Registers](#513-registers)
  - [5.3 Instruction formats](#53-instruction-formats)
    - [5.3.1 Design criteria for instruction formats](#531-design-criteria-for-instruction-formats)
    - [5.3.1 Expanding opcodes](#531-expanding-opcodes)
  - [5.4 Addressing](#54-addressing)
  - [5.5 Instruction types](#55-instruction-types)
  - [5.6 Flow of control](#56-flow-of-control)
    - [5.6.1 Sequential flow of control and branches](#561-sequential-flow-of-control-and-branches)
    - [5.6.2 Procedures](#562-procedures)
  - [7.1 Introduction to the Assembly language](#71-introduction-to-the-assembly-language)
  - [7.3 The Assembly process](#73-the-assembly-process)
- [Virtual memory](#virtual-memory)
  - [6.1 Virtual memory](#61-virtual-memory)
    - [6.1.1 Paging](#611-paging)
    - [6.1.2 Implementation of paging](#612-implementation-of-paging)
    - [6.1.3 Demand paging and the working-set model](#613-demand-paging-and-the-working-set-model)
    - [6.1.4 Page-replacement policy](#614-page-replacement-policy)
    - [6.1.5 Page size and fragmentation](#615-page-size-and-fragmentation)

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
We believe RISC is best but there is the issue of backward compatibility and the billions of dollars companies have invested in software for the Intel line (CISC).

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
Computer architects are constantly striving to improve performance of the machines they design. Making the chips run faster by increasing their clock speed is one way, but for every new design, there is a limit to what is possible by brute force at that moment in history. Consequently, most computer architects look to parallelism (doing two or more things at once) as a way to get even more performance for a given clock speed. In instruction-level parallelism, parallelism is exploited within individual instructions to get more instructions per second out of the machine.

#### Pipelining
It has been known for years that the actual fetching of instructions from memory is a major bottleneck in instruction execution speed. In a pipeline, instruction execution is often divided into many (often a dozen or more) parts, each one handled by a dedicated piece of hardware, all of which can run in parallel. Pipelining allows a trade-off between *latency* (how long it takes to execute an instruction), and *processor bandwidth* (how many instructions that can be executed per second). The maximum clock frequency of the CPU is decided by the slowest stage of the pipeline.

#### Superscalar architectures
The definition of "superscalar" has evolved somewhat over time. It is now used to describe processors that issue multiple instructions—often four or six—in a single clock cycle. Of course, a superscalar CPU must have multiple functional units to hand all these instructions to. 

### 2.1.6 Processor-level parallelism
Instruction-level parallelism helps a little, but pipelining and superscalar operation rarely win more than a factor of five or ten. To get gains of 50, 100, or more, the only way is to design computers with multiple CPUs, so we will now take a look at how some of these are organized.

####  Data parallel computers
A substantial number of problems in computational domains such as the physical sciences, engineering, and computer graphics involve loops and arrays, or otherwise have a highly regular structure. Often the same calculations are performed repeatedly on many different sets of data. The regularity and structure of these programs makes them especially easy targets for speed-up through parallel execution. Two primary methods have been used to execute these highly regular programs quickly and efficiently: SIMD processors and vector processors.

- A *Single Instruction-stream Multiple Data-stream* or SIMD processor consists of a large number of identical processors that perform the same sequence of instructions on different sets of data.

- A *vector processor* appears to the programmer very much like a SIMD processor. Like a SIMD processor, it is very efficient at executing a sequence of operations on pairs of data elements. But unlike a SIMD processor, all of the operations are performed in a single, heavily pipelined functional unit.

#### Multiprocessors
The processing elements in a data parallel processor are not independent CPUs, since there is only one control unit shared among all of them. Our first parallel system with multiple full-blown CPUs is the multiprocessor, a system with more than one CPU sharing a common memory, like a group of people in a room sharing a common blackboard. Since each CPU can read or write any part of memory, they must coordinate (in software) to avoid getting in each other’s way.

#### Multicomputers
Although multiprocessors with a modest number of processors (≤ 256) are relatively easy to build, large ones are surprisingly difficult to construct. The difficulty is in connecting so many the processors to the memory. To get around these problems, many designers have simply abandoned the idea of having a shared memory and just build systems consisting of large numbers of interconnected computers, each having its own private memory, but no common memory. These systems are called multicomputers. The CPUs in a multicomputer are said to be *loosely coupled*, to contrast them with the *tightly coupled* multiprocessor CPUs.

## 2.2 Primary memory
The memory is that part of the computer where programs and data are stored.

### 2.2.5 Cache memory
Historically, CPUs have always been faster than memories. What this imbalance means in practice is that after the CPU issues a memory request, it will not get the word it needs for many CPU cycles. The slower the memory, the more cycles the CPU will have to wait.

Actually, the problem is not technology, but economics. Engineers know how to build memories that are as fast as CPUs, but to run them at full speed, they have to be located on the CPU chip (because going over the bus to memory is very slow). What we would prefer is a large amount of fast memory at a low price. Interestingly enough, techniques are known for combining a small amount of fast memory with a large amount of slow memory to get the speed of the fast memory (almost) and the capacity of the large memory at a moderate price. The small, fast memory is called a cache.

The basic idea behind a cache is simple: the most heavily used memory words are kept in the cache. When the CPU needs a word, it first looks in the cache. Only if the word is not there does it go to main memory. Ifasubstantial fraction of the words are in the cache, the average access time can be greatly reduced.

#### Locality principle
The locality principle is the observation that the memory references made in any short time interval tend to use only a small fraction of the total memory.

- Temporal Locality: Programs tend to access the same data repeatedly over time. That is, if a program has used a variable recently, it’s likely to use that variable again soon.

- Spatial Locality: Programs tend to access data that is nearby other, previously-accessed data. "Nearby" here refers to the data’s memory address. For example, if a program accesses data at addresses N and N+4, it’s likely to access N+8 soon.

The general idea is that when a word is referenced, it and some of its neighbors are brought from the large slow memory into the cache, so that the next time it is used, it can be accessed quickly.

#### Mean access time
Let $c$ be the cache access time, $m$ the main memory access time, and $h$ the hit ratio. We can calculate the mean access time as follows:
$$t_{mean} = c + (1 - h)m$$

#### Cache design
1. **Cache size**: the bigger the cache, the better it performs, but also the slower it is to access and the more it costs.
2. **Cache line size**: Example: a 16-KB cache can be divided up into 1024 lines of 16 bytes, 2048 lines of 8 bytes, and other combinations.
3. **Organization of the cache**: how does the cache keep track of which memory words are currently being held?
4. **Unified or split cache**: should instructions and data use the same cache?
5. **Number of caches**: It is common these days to have chips with a primary cache on chip, a secondary cache off chip but in the same package as the CPU chip, and a third cache still further away (L1, L2, L3).

## 2.3 Secondary memory
No matter how big the main memory is, it is generally way too small to hold all the data people want to store.

### 2.3.1 Memory hierarchies
![A visualization of the memory hierarchy](https://diveintosystems.org/book/C11-MemHierarchy/_images/MemoryHierarchy.png)
Credit: https://diveintosystems.org/book/C11-MemHierarchy/mem_hierarchy.html

## 2.4 Input and output (I/O)
As we mentioned at the start of this chapter, a computer system has three major components: the CPU, the memories (primary and secondary), and the I/O (Input/Output).

### 2.4.1 Buses
External devices exchange information with the CPU in the same way we generally exchange information in a computer, through *buses*.

#### Interrupt handler
A controller that reads or writes data to or from memory without CPU intervention is said to be performing *Direct Memory Access* (DMA). When the transfer is completed, the controller normally causes an *interrupt*, forcing the CPU to immediately suspend running its current program and start running a special procedure, called an *interrupt handler*, to check for errors, take any special action needed, and inform the operating system that the I/O is now finished. When the interrupt handler is finished, the CPU continues with the program that was suspended when the interrupt occurred.

#### Bus arbiter
What happens if the CPU and an I/O controller want to use the bus at the same time? The answer is that a chip called a bus arbiter decides who goes next. In general, I/O devices are given preference over the CPU, because disks and other moving devices cannot be stopped, and forcing them to wait would result in lost data. When no I/O is in progress, the CPU can have all the bus cycles for itself to reference memory.

# Digital logic level

## Sekvensiell logikk, kompendium på BB
`TODO: take a look`

## 3.1 Gates and boolean algebra
*Regarded as trivial*

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
*Regarded as trivial*

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

## 4.2 An example ISA: IJVM
*Low priority*
### 4.2.1 Stacks
*Low priority*
### 4.2.2 The IJVM memory model
*Low priority*
### 4.2.3 The IJVM instruciton set
*Low priority*

## 4.3 An example implementation

### 4.3.1 Microinstructions and notation

### 4.3.2 Implementation of IJVM using the mic-1

## 4.4 Design of the microarchitecture level

### 4.4.1 Speed versus cost

### 4.4.2 Reducing the execution path length

### 4.4.3 A design with prefetching: the mic-2

### 4.4.4 A pipelined design: the mic-3

### 4.4.5 A seven-stage pipeline: the mic-4

## 4.5 Improving performance

### 4.5.1 Cache memory

### 4.5.2 Branch prediction

## 8.1 On-chip parallelism

### 8.1.1 Instruction-level parallelism (ILA)

### 8.1.2 On-chip multithreading

# Instruction set architecture level (ISA)

## 5.1 Overview of the ISA level

### 5.1.1 Properties of the ISA level

### 5.1.2 Memory models

### 5.1.3 Registers

## 5.3 Instruction formats

### 5.3.1 Design criteria for instruction formats

### 5.3.1 Expanding opcodes

## 5.4 Addressing
`TODO: Addressing modes 5.4.2-5.4.7`

## 5.5 Instruction types
`TODO: Instruction types 5.5.1-5.5.7`

## 5.6 Flow of control

### 5.6.1 Sequential flow of control and branches

### 5.6.2 Procedures

## 7.1 Introduction to the Assembly language
*Regarded as trivial.*

## 7.3 The Assembly process
*Regarded as trivial.*

# Virtual memory

## 6.1 Virtual memory

### 6.1.1 Paging

### 6.1.2 Implementation of paging

### 6.1.3 Demand paging and the working-set model

### 6.1.4 Page-replacement policy

### 6.1.5 Page size and fragmentation
 
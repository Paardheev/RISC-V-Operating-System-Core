# RISC-V Systems Programming Lab

This repository contains a series of hands-on lab assignments designed to build a deep understanding of low-level systems programming on the RISC-V architecture. The labs involve direct manipulation of hardware-level constructs, with implementations in RISC-V assembly and C, focused on core operating system mechanisms.

The project covers topics such as privilege level management, timer-driven multitasking, virtual memory via Sv39 paging, and custom trap handling for page faults—all implemented in a bare-metal environment without any operating system support.

---

## Table of Contents

- [Overview](#overview)  
- [Lab Modules](#lab-modules)  
- [Technologies Used](#technologies-used)  
- [Setup and Usage](#setup-and-usage)

---

## Overview

These labs emphasize practical exploration of RISC-V system-level features by interacting with:

- Control and Status Registers (CSRs)
- Memory-mapped I/O
- Privilege specification and trap handling
- Low-level stack and interrupt control

Concepts implemented include:

- Transitions between Machine, Supervisor, and User privilege modes  
- Timer interrupts and cooperative context switching  
- Virtual memory management using Sv39 page tables  
- Dynamic instruction/data page fault handling  
- Interfacing between RISC-V assembly and C

---

## Lab Modules

### Lab 4: C and Assembly Interfacing
- Established bidirectional function calls between C and RISC-V assembly
- Demonstrated manual memory access and string handling across language boundaries

### Lab 5: Privilege Switching
- Controlled transitions between Machine, Supervisor, and User modes
- Implemented basic exception and trap handling using CSRs

### Lab 6: Timer-Based Multitasking
- Enabled timer interrupts to simulate cooperative multitasking
- Designed a context switch mechanism to save and restore task state

### Lab 7: Virtual Memory with Sv39
- Configured multi-level Sv39 page tables for virtual address translation
- Transitioned to user-mode execution using mapped virtual addresses

### Lab 8: Page Fault Handling
- Implemented trap handlers for detecting and resolving page faults
- Dynamically updated page tables and loaded memory pages on demand

---

## Technologies Used

- **RISC-V ISA (RV64)**  
- **RISC-V Assembly** and **C**  
- **Spike** – RISC-V ISA Simulator  
- **GNU Toolchain** – `riscv64-unknown-elf-gcc`, `objdump`  
- **Bare-metal Development** – No operating system or runtime library  

---

## Setup and Usage

### Prerequisites

Ensure the following tools are installed:

- RISC-V GCC Toolchain: [`riscv64-unknown-elf-gcc`](https://github.com/riscv-collab/riscv-gnu-toolchain)  
- Spike Simulator: [`spike`](https://github.com/riscv/riscv-isa-sim)  

### Compilation and Execution

```bash
# Compile the lab file (replace labX.S with the appropriate lab)
riscv64-unknown-elf-gcc -nostartfiles -T linker.ld labX.S -o labX.out

# Run in Spike simulator with debug mode
spike -d labX.out

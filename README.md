# Kernel Hacking with xv6

## Overview
This project involves adding two new system calls to the xv6 operating system, a small Unix version 6 like operating system for x86 processors. This exercise aims to provide familiarity with the xv6 codebase and experience with kernel-level programming in C.

## Features
- Addition of `getnextpid` system call to return the next available PID.
- Addition of `getprocstate` system call to retrieve the state of a process based on its PID.

## Prerequisites
- Familiarity with C programming and basic operating system concepts.
- Access to a UNIX-like development environment (Linux preferred).
- Understanding of system call mechanics in operating systems.

## Installation
1. Obtain the xv6 source code:
cp ~cs537-1/public/xv6.tar.gz .
tar -xvf xv6.tar.gz

2. Navigate to the xv6 source directory and make modifications as described below.
3. Compile the modified xv6 source code: make qemu-nox

## Usage
After compiling the modified xv6, run it using the QEMU emulator to test the new system calls: make qemu-nox

To exit the emulator, press `Ctrl-a x`.

## System Calls Implementation
1. **getnextpid**
   - Returns the next available PID by accessing the `nextpid` variable in the process table.
2. **getprocstate**
   - Finds the process with the given PID in the process table and returns its state as a string.

## Debugging
Use GDB for debugging the xv6 kernel:
1. Run xv6 under QEMU with GDB support: make qemu-nox-gdb

2. In another terminal, start gdb and connect to the xv6 QEMU session: gdb

## Implementation Details
- Modify `proc.c` and `proc.h` to implement the new system calls.
- Update `syscall.c` and `syscall.h` to register the new system calls.
- Ensure that `usys.S` is updated to include the user-space stubs for the system calls.

## Acknowledgments
This project is based on the xv6 operating system, a teaching operating system developed at MIT, inspired by Unix Version 6. More information can be found in the [xv6 book](https://pdos.csail.mit.edu/6.828/2018/xv6/book-rev11.pdf).

## Submission
Submit the modified xv6 source code and a screenshot demonstrating the use of GDB to debug the kernel as per the project instructions.



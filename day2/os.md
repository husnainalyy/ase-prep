# Day 2 — OS

**Topic:** Fundamentals

---

## 1. Difference between a 32-bit and a 64-bit operating system.

### Answer

The bit number is how much data the processor handles in one step, and how much memory the operating system can address.

- A 32-bit operating system uses 32-bit addresses. It can use about 4 GB of RAM.
- A 64-bit operating system uses 64-bit addresses. It can use far more than 4 GB of RAM.
- A 64-bit operating system runs 64-bit programs, and it can usually run 32-bit programs as well.
- A 32-bit operating system cannot run 64-bit programs.
- A 64-bit program can use larger registers, so some work moves in bigger pieces. Pointers are also larger, so the same program can use a little more memory.
- The operating system and the processor must match. A 64-bit operating system needs a 64-bit processor.

### Interview

A 32-bit operating system addresses about 4 GB of RAM and runs 32-bit programs. A 64-bit operating system can use much more RAM, runs 64-bit programs, and can usually run 32-bit programs too. A 32-bit operating system cannot run a 64-bit program. The processor must support the version you install.

#### Example

A laptop has 16 GB of RAM. A 32-bit Windows install can see only about 4 GB of it, so 12 GB sits unused. A 64-bit Windows install can use the full 16 GB. A 64-bit game installs on the 64-bit system and refuses to install on the 32-bit system.

---

## 2. Difference between a kernel and an operating system.

### Answer

The kernel is the core of the operating system. The operating system is the kernel plus the programs around it.

- The kernel manages the CPU, memory, processes, and devices. It is the first part that stays running.
- Applications cannot touch the hardware directly. They ask the kernel through a system call.
- The operating system also includes the shell, file utilities, libraries, and often a desktop.
- You type in the terminal or click the desktop. Those programs pass the real work to the kernel.
- If the kernel stops, the computer stops. A normal application can crash and the kernel keeps running.
- Linux names are easy to mix up. Linux is the kernel. Ubuntu is an operating system built around that kernel.

### Interview

The kernel is the core that manages the CPU, memory, processes, and hardware. The operating system is the kernel plus the shell, tools, libraries, and desktop around it. Programs reach the hardware by asking the kernel with a system call. Linux is the kernel. Ubuntu is an operating system that includes that kernel and the rest of the software you use.

#### Example

You run `mkdir notes` in the terminal. The terminal is part of the operating system, not the kernel. It asks the kernel to create the folder. The kernel checks permission, updates the disk, and reports success. The terminal then prints the prompt again.

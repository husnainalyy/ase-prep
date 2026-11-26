# Day 3 — OS

**Topic:** Fundamentals

---

## 1. What is a system call?

### Answer

A system call is a request from a program to the kernel. The program asks the operating system to do something the program is not allowed to do itself.

- Normal code runs in user mode. The kernel runs in kernel mode and is allowed to touch the hardware.
- A system call is the controlled switch from user mode into the kernel, and then back.
- Opening a file, reading it, creating a process, and sending data over the network are system calls.
- A library function often hides the call. `printf` prepares the text, then a system call such as `write` sends it out.
- The kernel checks the request. A program cannot skip that check and use the disk on its own.

### Interview

A system call is how a program asks the kernel for a service, such as reading a file or starting another process. The program runs in user mode, and the call switches into kernel mode for that one job, then returns. Functions like `printf` and `fopen` are library calls that end up making a system call.

#### Example

A program calls `open` on `notes.txt`. That is a system call. The CPU switches to kernel mode, the kernel checks that the user may read the file, and it returns a file handle. The program then uses that handle. It never talks to the disk itself.

---

## 2. What are the different types of system calls?

### Answer

System calls are grouped by the job they do. Five groups cover the ones asked in interviews.

- **Process control:** create, end, or wait for a process. Examples: `fork`, `exit`, `wait`.
- **File management:** create, open, read, write, and close files. Examples: `open`, `read`, `write`, `close`.
- **Device management:** ask for a device, release it, or send it a command. Reading from the keyboard and writing to the screen fall here.
- **Information maintenance:** ask the system for a fact. Examples: the process id, the current time, and system details.
- **Communication:** pass data between processes. Examples: `pipe`, shared memory, and sockets.

### Interview

There are five common groups. Process control creates and ends processes. File management opens, reads, writes, and closes files. Device management works with hardware such as the screen and the disk. Information maintenance reads facts such as the time or the process id. Communication moves data between processes, using pipes or sockets.

#### Example

Starting a program uses more than one group. `fork` is process control and makes a new process. `open` and `read` are file management and load the program's file. `getpid` is information maintenance and returns the new process id. A `pipe` is communication if that program must send text to another program.

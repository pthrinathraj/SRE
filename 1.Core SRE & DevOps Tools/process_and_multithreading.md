# Save the detailed README content to a markdown (.md) file

readme_content = """
# 🧠 Linux Process Management and Context Switching

This document provides a comprehensive overview of **processes** in Linux, covering their lifecycle, attributes, states, creation, termination, scheduling, synchronization, IPC, and context switching.

## 🔹 What is a Process?
A **process** is an instance of a program in execution. It includes:
- Program code
- Current activity (e.g., program counter, registers)
- Stack and heap memory
- Open files and signals
- One or more **threads** of execution

## 🔹 Components of a Process
- **Program Code**
- **Memory Layout**:
  - Text Segment
  - Data Segment
  - Heap
  - Stack
- **Process Control Block (PCB)**:
  - PID
  - Process state
  - Program counter
  - CPU registers
  - Memory management data
  - I/O and accounting info

## 🔹 Process States
- **New**
- **Ready**
- **Running**
- **Waiting**
- **Terminated**

### Linux-specific states:
- R: Running or ready to run
- S: Interruptible sleep
- D: Uninterruptible sleep
- T: Stopped
- Z: Zombie

## 🔹 Process Attributes
- PID, PPID, UID/GID, State, Priority, Command

## 🔹 Process Scheduling
- **Algorithms**: FCFS, SJN, Round Robin, Priority, Multilevel Queue
- **Linux Scheduler**: CFS (Completely Fair Scheduler)
- **Policies**:
  - SCHED_OTHER
  - SCHED_FIFO
  - SCHED_RR

## 🔹 Process Lifecycle
### 1. Creation
- `fork()` – Duplicates parent
- `exec()` – Replaces memory with a new program
- `clone()` – Fine-grained sharing for threads

### 2. Kernel Task States
- TASK_RUNNING
- TASK_INTERRUPTIBLE
- TASK_UNINTERRUPTIBLE
- TASK_STOPPED
- TASK_TRACED
- TASK_ZOMBIE
- TASK_DEAD

### 3. Termination
- Normal: `exit()`
- Signal: `kill -SIGTERM`
- Abnormal: Error/Crash
- Cleanup: `wait()` or `waitpid()`

### 4. Reaping
- Zombies: Reaped using `wait()`/`waitpid()`
- Orphan zombies adopted by `init` (PID 1)

## 🔹 Inter-Process Communication (IPC)
- Pipes
- FIFOs (Named Pipes)
- Message Queues
- Shared Memory
- Semaphores
- Sockets

## 🔹 Process Synchronization
- Mutexes
- Semaphores
- Monitors

## 🔹 Process vs Thread
| Feature      | Process         | Thread           |
|--------------|------------------|------------------|
| Memory Space | Isolated         | Shared           |
| Overhead     | High             | Low              |
| Isolation    | Full             | Partial          |

## 🔹 Context Switching
**Context Switching** is storing current process state and restoring another’s.

### Components:
- Program Counter
- CPU Registers
- Memory Maps
- PCB

### Overhead:
- CPU cycles
- Cache flush
- System call latency

### Optimization:
- Processor affinity
- Efficient scheduling
- Minimize unnecessary system calls

## 📚 References
- https://tldp.org/LDP/tlk/kernel/processes.html
- https://opensource.com/article/19/4/interprocess-communication-linux-storage
- https://www.halolinux.us/kernel-architecture/process-life-cycle.html
- http://www.linux-tutorial.info/?page_id=245
- https://www.geeksforgeeks.org/context-switch-in-operating-system/
- https://www.netdata.cloud/blog/understanding-context-switching-and-its-impact-on-system-performance/
"""

# Write to a file
output_path = "/mnt/data/Linux_Process_Context_Switching_README.md"
with open(output_path, "w") as f:
    f.write(readme_content)

output_path

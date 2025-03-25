# 🧠 Stack vs Heap Memory

This document explains the difference between **Stack** and **Heap** memory in programming — how they are used, their characteristics, performance implications, and when to choose one over the other.

---

## 🗂️ What is Stack Memory?

The **stack** is a region of memory used for storing:
- Local (automatic) variables
- Function call parameters
- Return addresses

It uses a **Last In, First Out (LIFO)** structure. Memory allocation and deallocation are managed automatically.

### ✅ Key Characteristics

| Property            | Stack Memory                                  |
|---------------------|-----------------------------------------------|
| **Size**            | Small and fixed per thread                    |
| **Speed**           | Very fast                                      |
| **Lifetime**        | Tied to function call                         |
| **Access**          | Private to the thread                         |
| **Management**      | Automatically managed by compiler             |

### 📋 Example

```c
void example() {
    int x = 10; // Stored on the stack
}

The variable x is created on the stack and automatically destroyed when the function returns.

🧳 What is Heap Memory?
The heap is a memory region used for dynamic memory allocation, where variables are created and destroyed manually or by a garbage collector.

✅ Key Characteristics
Property	Heap Memory
Size	Large (limited by system memory)
Speed	Slower due to allocation overhead
Lifetime	Until explicitly freed (or GC in high-level langs)
Access	Shared across threads
Management	Manual (malloc/free, new/delete) or automatic (GC)
Example
int* p = malloc(sizeof(int)); // Allocated on the heap
*p = 20;
free(p); // Must free manually
🔍 Stack vs Heap – Comparison
Feature	Stack	Heap
Allocation	Automatic	Manual or Garbage Collected
Speed	Faster	Slower
Lifetime	Limited to scope	Until explicitly deallocated
Size Limit	Small (e.g., 1–8MB default)	Very large (system dependent)
Thread Safety	Thread-specific	Shared across threads
Common Errors	Stack overflow	Memory leak, dangling pointers
Use Cases	Function calls, local variables	Dynamic data structures, long-lived data
🧠 When to Use Stack vs Heap
Scenario	Use
Temporary, scoped variables	Stack
Recursive function calls	Stack
Data whose size changes at runtime	Heap
Long-lived objects or buffers	Heap
🚨 Common Pitfalls
Stack overflow: Too much recursive depth or large local arrays.

Memory leaks: Forgetting to free memory on the heap.

Dangling pointers: Accessing heap memory after it's freed.

----------
STACK:

This is the memory area used by our thread of execution.
When a function is called the local variables and return addresses are stored here.
The space becomes available when the function  exits.
The user doesn't need to take care of the memory allocation and deallocation( happens automatically).

HEAP:

It is the memory set aside for dynamic allocation.
Generally, an application is given a separate heap memory and it allocates the memory from the given heap on need basis.
WE can allocate and free heap anytime.
User must take care of deallocation of memory when he doesn't need it.
To get heap memory we use malloc and calloc if we are in user space and if we are in kernel space we use kmalloc, vmalloc.
We must free the memory allocated by using free, kfree and vfree respectively.
---------

Summary
Use the stack for fast, short-lived data tied to function calls.

Use the heap for large, long-lived, or dynamically sized data.

Be cautious with heap memory in low-level languages (e.g., C/C++) — always clean up!

📚 References
Stack vs Heap – GeeksforGeeks

C Programming: Stack vs Heap

Memory Management in Java



# 🧠 Memory Leaks, Garbage Collection & Generational GC Explained

This document covers **memory management fundamentals** including:

- What is a memory leak and when it happens
- What is garbage collection (GC)
- Different types of GC strategies
- Detailed overview of **Generational GC** and **G1GC**

---

## 🧨 What is a Memory Leak?

A **memory leak** occurs when a program **allocates memory** but **fails to release it** after it's no longer needed.

### 🔍 Why is it bad?
- Gradual increase in memory usage
- Reduced system performance
- Can lead to **OutOfMemoryError** or system crashes

### 🧪 When Does It Happen?

| Example | Language | Description |
|--------|----------|-------------|
| `malloc()` without `free()` | C/C++ | Manual memory leak |
| Holding references to unused objects | Java, Python | GC can’t reclaim |
| Event listeners on removed DOM elements | JavaScript | Retained references |

---

## ♻️ What is Garbage Collection?

**Garbage Collection (GC)** is an **automatic process** of identifying and reclaiming memory that is no longer in use.

### ✅ Benefits:
- Prevents memory leaks
- Automates memory management
- Improves developer productivity

### Languages with GC:
✅ Java, Python, JavaScript, Go, C#  
❌ C, C++ (manual memory management)

---

## 🔄 Types of Garbage Collection

### 1. Reference Counting
- Every object tracks how many references point to it.
- ✅ Immediate collection
- ❌ Fails on circular references

### 2. Mark and Sweep
- **Mark phase**: Finds reachable objects  
- **Sweep phase**: Deletes unreachable objects  
- ✅ Handles cycles  
- ❌ May cause pauses

### 3. Copying Collector
- Copies live objects to a new memory space  
- Old memory is cleared  
- ✅ Fast allocation  
- ❌ Wastes space

### 4. Generational GC ✅ (See below for full details)

### 5. Concurrent / Incremental GC
- GC runs in **parallel with the application**  
- ✅ Reduces pause time  
- ❌ Complex to implement

---

## 🧬 Generational Garbage Collection

Generational GC divides the heap into **three generations** based on object lifespan:

### 👶 Young Generation
- Newly created objects
- Most objects die here
- Subdivided into:
  - Eden
  - Survivor Spaces (S0, S1)
- Triggered frequently (Minor GC)

📌 **Example**:
```java
for (int i = 0; i < 100000; i++) {
  String temp = new String("data");
}

Old Generation (Tenured)
Objects that survived multiple GCs

Long-lived objects: caches, sessions

Triggered less frequently (Major/Full GC)

📦 Heap Structure (Java JVM Example)      
                ┌────────────────────────────────────────────┐
                │                  Heap                      │
                ├───────────────┬────────────────────────────┤
                │ Young Gen     │    Old (Tenured) Gen       │
                ├────┬────┬─────┤                            │
                │Eden│S0  │S1   │                            │
                └────┴────┴─────┴────────────────────────────┘



📌 Example:

java
Copy
Edit
Map<String, Object> sessionCache = new HashMap<>();
🧠 Permanent Generation / Metaspace
Stores class metadata, method names, interned strings

Removed in Java 8+ → replaced by Metaspace (uses native memory)

📌 Example:

java
Copy
Edit
class MyClass {
  static final String CONSTANT = "fixed";
}
🚀 G1GC – Garbage First Garbage Collector
G1GC is the default GC in Java 9+ and a modern GC for large heaps with predictable pause times.

🧩 Key Features:
Heap divided into equal-sized regions

Prioritizes regions with most garbage (hence "Garbage First")

Supports concurrent and parallel collection

Reduces Full GC frequency

🔬 G1GC Phases
Young GC (Minor) – Collects Eden + Survivor

Concurrent Marking – Finds garbage-rich regions

Mixed GC – Collects young + some old regions

Full GC – Fallback (rare)

✅ Benefits of G1GC
Feature	Description
Predictable pauses	Use -XX:MaxGCPauseMillis=200
Region-based heap	Improves collection flexibility
Concurrent marking	Reduces stop-the-world pauses
Suitable for large heaps	Better than CMS or Parallel GC
⚙️ Recommended JVM Options for G1GC
bash
Copy
Edit
-XX:+UseG1GC
-XX:MaxGCPauseMillis=200
-XX:+PrintGCDetails
-XX:+PrintGCTimeStamps
🛑 Common GC-Related Issues
Problem	Cause	Solution
Memory leak	Unused objects not dereferenced	Nullify, use weak references
GC pauses	Full GC in old generation	Tune heap sizes, use G1GC
OOM errors	Heap too small, too many objects	Profile & increase heap
📚 References
Java G1GC Tuning Guide

Java Memory Management

Python Garbage Collection

Understanding GC Logs

🧠 Good memory management = fewer bugs, better performance, and scalable apps.

yaml
Copy
Edit


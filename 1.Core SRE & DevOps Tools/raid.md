# 💾 RAID – Redundant Array of Independent Disks

**RAID** is a data storage virtualization technology that combines multiple physical disk drives into one logical unit to improve **performance**, **fault tolerance**, or both.

---

## 🔧 Why Use RAID?

- ✅ Improve **read/write speed**
- ✅ Increase **data availability and redundancy**
- ✅ Protect against **disk failures**
- ✅ Optimize **storage efficiency**

---

## 📚 Common RAID Levels

### ⚡ RAID 0 – Striping

**How it works:**
- Data is split evenly (striped) across two or more disks.
- No redundancy or fault tolerance.

**Use Case:**  
High-performance environments where data loss is acceptable (e.g., video editing, temporary caches).

**Pros:**
- High read and write speed
- Full disk capacity usage

**Cons:**
- If one disk fails, all data is lost
- No fault tolerance

---

### 🛡️ RAID 1 – Mirroring

**How it works:**
- Data is duplicated across two or more disks.
- Each disk is a mirror of the other.

**Use Case:**  
Critical systems that require high availability and fault tolerance (e.g., database servers).

**Pros:**
- Excellent redundancy
- Fast reads (from either disk)

**Cons:**
- 50% storage efficiency (1TB + 1TB = 1TB usable)
- Higher cost due to duplication

---

### ⚙️ RAID 5 – Striping with Distributed Parity

**How it works:**
- Data and parity information are striped across at least three disks.
- Parity allows recovery from a single disk failure.

**Use Case:**  
File and application servers that need a good balance of performance and fault tolerance.

**Pros:**
- Good storage efficiency
- Can tolerate one disk failure
- Read performance is good

**Cons:**
- Slower write performance (due to parity calculation)
- Cannot tolerate more than one disk failure

---

### 🚀 RAID 10 (1+0) – Mirrored Stripes

**How it works:**
- Combines RAID 1 and RAID 0: data is striped across mirrored pairs.
- Requires at least 4 disks.

**Use Case:**  
High-performance, high-availability systems (e.g., databases, virtualization).

**Pros:**
- High read/write performance
- Can survive multiple disk failures (as long as they’re not in the same mirror pair)

**Cons:**
- 50% storage efficiency
- Requires minimum 4 disks

---

## 🧠 Other RAID Levels (Less Common)

- **RAID 2, 3, 4** – Early designs, rarely used in modern systems
- **RAID 6** – Similar to RAID 5 but with double parity (tolerates 2 disk failures)
- **RAID 50, 60** – Nested RAID levels for enterprise setups

---

## 📝 Summary Comparison Table

| RAID Level | Min Disks | Redundancy | Performance | Usable Storage | Fault Tolerance |
|------------|-----------|-------------|-------------|----------------|------------------|
| RAID 0     | 2         | ❌ None     | 🔼 High     | 🔁 100%        | ❌ None          |
| RAID 1     | 2         | ✅ Mirrored | 🔼 Read     | 50%            | ✅ 1 disk        |
| RAID 5     | 3         | ✅ Parity   | 🔼 Read     | N-1 disks       | ✅ 1 disk        |
| RAID 6     | 4         | ✅ 2 Parity | 🔼 Read     | N-2 disks       | ✅ 2 disks       |
| RAID 10    | 4         | ✅ Mirror+Stripe | 🔼🔼 High | 50%            | ✅ Multiple pairs|

---

## 📚 References

- [RAID Wiki](https://en.wikipedia.org/wiki/RAID)
- [Intel RAID Levels Explained](https://www.intel.com/content/www/us/en/support/articles/000005837.html)
- [Difference Between RAID Levels – GeeksforGeeks](https://www.geeksforgeeks.org/raid-levels/)

---

> Need a RAID calculator or performance benchmark comparison? Let me know!


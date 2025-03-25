# 🧵 Linux cgroups (Control Groups)

## 📌 What are cgroups?

**cgroups** (Control Groups) is a Linux kernel feature that allows you to **limit, monitor, and isolate resource usage** (CPU, memory, I/O, etc.) for groups of processes.

---

## 🎯 Key Features

- **Resource Limiting:** Restrict CPU, memory, etc.
- **Prioritization:** Allocate more resources to critical apps.
- **Accounting:** Track how much resources each group uses.
- **Isolation:** Separate workloads to prevent interference.
- **Freezing/Throttling:** Pause or slow down groups of processes.

---

## 📦 Real-World Usage

| Tool / Platform | How it uses cgroups |
|-----------------|---------------------|
| Docker / Kubernetes | Enforce container resource limits |
| Systemd            | Manages service resources          |
| Cloud providers    | Multi-tenant workload isolation    |
| Linux desktops     | Prevent background apps from hogging resources |

---

## 🆚 cgroups vs Namespaces

| Feature   | cgroups                     | namespaces                    |
|-----------|-----------------------------|-------------------------------|
| Purpose   | Resource limitation         | Resource isolation            |
| Example   | Limit CPU/memory per group  | Isolate network, PID, mount   |

---

## ⚙️ How It Works

1. Mount the cgroup filesystem:  
   `mount -t cgroup -o memory none /sys/fs/cgroup/memory`

2. Create a cgroup directory:  
   `mkdir /sys/fs/cgroup/memory/mygroup`

3. Apply resource limits:  
   `echo 104857600 > /sys/fs/cgroup/memory/mygroup/memory.limit_in_bytes`

4. Add a process to the group:  
   `echo 1234 > /sys/fs/cgroup/memory/mygroup/cgroup.procs`

---

## 🧬 cgroups v1 vs v2

| Feature            | v1                              | v2                              |
|--------------------|----------------------------------|----------------------------------|
| Controller model   | Separate hierarchies per resource | Unified hierarchy               |
| Interface           | Fragmented                      | Simplified                      |
| Example distros     | CentOS 7, Ubuntu 18.04          | Fedora, Ubuntu 20.04+, Arch     |

---

## 🛠️ Tools for Managing cgroups

- `systemd` (preferred for modern Linux)
- `cgroup-tools`
- Container runtimes: Docker, CRI-O, containerd
- `cgexec`, `cgclassify` (legacy tools)

---

## 🔒 Best Practices

- Use systemd or orchestrators instead of manual cgroup management.
- Don't allow userland processes to modify cgroup files directly.
- Monitor performance and group usage regularly.

---

## 📚 Resources

- [Linux Kernel Docs – cgroups](https://www.kernel.org/doc/html/latest/admin-guide/cgroup-v2.html)
- `man cgroups`
- Tools: `htop`, `systemd-cgls`, `systemd-cgtop`

---


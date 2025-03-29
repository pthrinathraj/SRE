
# Network Interface Card (NIC) – Detailed Guide

A **NIC (Network Interface Card)** is a hardware component that enables a device (such as a computer or server) to connect to a network. It plays a critical role in networking at the hardware and data-link layers.

---

## 🔧 What is a NIC?

- Acts as the bridge between your device and the network
- Sends and receives data through wired (Ethernet) or wireless (Wi-Fi) connections
- Operates at **Layer 1 (Physical)** and **Layer 2 (Data Link)** of the OSI model

---

## 🧩 Key Functions of a NIC

| Function | Description |
|----------|-------------|
| **MAC Address** | Provides a unique hardware identifier |
| **Frame Handling** | Encapsulates data into network frames |
| **Signal Conversion** | Converts data into signals suitable for transmission |
| **Error Checking** | Detects errors in transmitted frames |

---

## 🖥️ Types of NICs

| Type | Description |
|------|-------------|
| **Ethernet NIC** | For wired LAN connections |
| **Wireless NIC** | Wi-Fi network access (802.11 standards) |
| **Fiber NIC** | For high-speed fiber optic connections |
| **Virtual NIC (vNIC)** | Software-based NICs in virtualized environments |

---

## 🛠️ Example (Linux)

To list NICs on a Linux machine:
```bash
ip link show
```
Example output:
```
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 ...
```

---

## 🧠 Interview Tip

**Q:** What OSI layers does a NIC operate on?  
**A:** Primarily Layer 1 (Physical) and Layer 2 (Data Link)

---

## 🔢 How Many NICs Does a Server Usually Have?

The number of NICs depends on server role and networking needs.

| Server Type | Typical # of NICs | Purpose |
|-------------|-------------------|---------|
| Basic Rack Server | 1–2 | Data access, redundancy or management |
| Enterprise Server | 4–8 | High availability, traffic separation |
| Hypervisor Host | 6–10+ | VMs, storage, vMotion, management |
| HPC Node | 2–4 | High-speed, low-latency interconnects |
| Cloud/Datacenter | Varies | Physical and virtual NICs (SR-IOV) |

---

## 📦 Common Server NIC Uses

- **Primary Data Network**: Frontend user traffic
- **Management Network**: iDRAC/iLO, SSH
- **Storage Network**: iSCSI, NFS
- **Cluster Heartbeat**: HA failover communication
- **Backup and Monitoring**
- **VM Migration**: vMotion or similar

---

## 🛡️ NIC Bonding/Teaming

Servers often **bond** NICs for redundancy and performance:
- **Active/Passive**: Failover
- **Active/Active**: Load balancing

Check bonding config:
```bash
cat /proc/net/bonding/bond0
```

---

## 🧠 Interview Tip

**Q:** Why would a server have multiple NICs?  
**A:** To separate traffic types, ensure redundancy, and enhance throughput using NIC bonding.

---

This guide covers everything you need to understand Network Interface Cards (NICs), from basics to real-world usage in modern servers.

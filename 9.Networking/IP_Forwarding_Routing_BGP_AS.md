
# IP Forwarding, Routing, Dynamic Routing & BGP – Detailed Guide

This guide covers the differences between IP forwarding and routing, dives into dynamic routing protocols, and provides an in-depth look at BGP including the concept of Autonomous Systems (ASes).

---

## 🔀 IP Forwarding vs Routing

### 📤 IP Forwarding
- **Definition:** The process where a device receives an IP packet and decides to send it out another interface based on its destination IP address.
- **Focus:** Operational behavior — the *act* of forwarding a packet.
- **Where:** Happens on any Layer 3 device (e.g., router, Layer 3 switch, Linux host with IP forwarding enabled).

**Linux Example:**
```bash
# Check if IP forwarding is enabled
cat /proc/sys/net/ipv4/ip_forward

# Enable it temporarily
sudo sysctl -w net.ipv4.ip_forward=1
```

**Use Case:** Turning a Linux server into a router or firewall between networks.

---

### 🧭 Routing
- **Definition:** The *decision-making logic* for determining which path a packet should take through the network.
- **Focus:** Configuration and path determination using routing tables.
- **Where:** Implemented on routers and Layer 3 devices.

**Key Concepts:**
- **Routing Table:** A set of rules for forwarding packets.
- **Next Hop:** The IP address where the router forwards the packet.
- **Default Route:** A fallback route when no specific path is known.

**Linux Example:**
```bash
ip route show
```

**Routing Table Example:**
| Destination | Gateway | Interface |
|-------------|---------|-----------|
| 0.0.0.0/0   | 192.168.1.1 | eth0    |
| 10.0.0.0/8  | 10.0.0.1    | eth1    |

**Summary:** IP forwarding is the action; routing is the logic that determines the action.

---

## 🔄 Dynamic Routing Protocols

Dynamic routing protocols enable routers to automatically discover and update routes in response to changes in the network topology.

### 🔹 Key Benefits
- Automatically adapts to topology changes
- Ideal for large and growing networks
- Reduces human error in route management

### 🔸 Common Dynamic Routing Protocols
| Protocol | Type | Usage | Key Traits |
|---------|------|-------|------------|
| RIP     | Distance Vector | Small LANs | Simple, hop-count metric |
| OSPF    | Link-State      | Enterprises | Fast convergence, cost-based |
| EIGRP   | Hybrid           | Cisco environments | Combines vector and link-state |
| BGP     | Path Vector      | Internet | Scalable, policy-based |

---

## 🌐 BGP: Border Gateway Protocol (In-Depth)

### 🌍 What is BGP?
**BGP (Border Gateway Protocol)** is the internet's backbone routing protocol. It exchanges routing and reachability information **between autonomous systems (ASes)**.

### 🏢 What is an Autonomous System (AS)?
- An **Autonomous System** is a collection of IP networks under the control of a single organization that presents a **unified routing policy** to the internet.
- Each AS is identified by a unique **AS Number (ASN)**, assigned by a regional internet registry.
- ASes can be **ISPs**, **content delivery networks**, **enterprises**, or **cloud providers**.

**Examples:**
- Google: AS15169
- Cloudflare: AS13335
- Comcast: AS7922

Not all ASes are ISPs, but most ISPs are ASes.

---

### 🔸 BGP Essentials
- **Type:** Path Vector Protocol
- **Port:** TCP 179
- **Used For:** Inter-domain routing (between ASes)
- **Core Principle:** Policy-based routing

### 🔧 BGP Route Selection
BGP chooses the best path using multiple **path attributes**, such as:
- **AS_PATH** – List of ASes a route has traversed
- **LOCAL_PREF** – Preference for internal routes
- **MED** – Multi-exit discriminator
- **NEXT_HOP** – IP of the next hop router

### 🧠 BGP Concepts
- **iBGP** – Between routers in the same AS
- **eBGP** – Between routers in different ASes
- **Route Advertisement** – Sharing prefixes a router can reach
- **Route Filtering** – Enforcing routing policies

---

### 🔒 BGP Security
- **Threats:** Route hijacking, prefix leaks
- **Mitigations:** TCP MD5 authentication, TTL security, RPKI (Resource Public Key Infrastructure)

---

### ⚙️ Configuration Example (Cisco-style)
```bash
router bgp 65001
  neighbor 203.0.113.1 remote-as 65002
  network 192.0.2.0 mask 255.255.255.0
```

---

### 📌 Real-World Use Case
BGP connects ISPs, cloud providers, enterprises, and content networks globally. It's what allows traffic from your ISP to reach websites hosted on AWS, GCP, or Cloudflare.

---

This concludes the in-depth guide on **IP Forwarding, Routing, Dynamic Routing Protocols, BGP, and Autonomous Systems (ASes)**.

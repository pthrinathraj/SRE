
# IP Addressing and Subnetting – In-Depth Guide

This guide provides a comprehensive breakdown of IP addressing concepts including IPv4, IPv6, address classes, public vs private IPs, static and dynamic assignment, subnetting, masks, and CIDR notation.

---

## 🌐 IPv4 (Internet Protocol version 4)

- 32-bit address written in dotted decimal format (e.g., `192.168.1.1`)
- Supports ~4.3 billion unique addresses
- Structured as: `Network Portion` + `Host Portion`
- Divided into 4 octets (8 bits each), separated by dots

---

## 🧮 IPv4 Address Classes

| Class | Range | Default Subnet Mask | # of Networks | # of Hosts per Network | Purpose |
|-------|-------|----------------------|---------------|------------------------|---------|
| A | 0.0.0.0 – 127.255.255.255 | 255.0.0.0 (/8) | 128 | ~16 million | Very large networks |
| B | 128.0.0.0 – 191.255.255.255 | 255.255.0.0 (/16) | 16,384 | ~65,000 | Medium-sized networks |
| C | 192.0.0.0 – 223.255.255.255 | 255.255.255.0 (/24) | ~2 million | 254 | Small networks |
| D | 224.0.0.0 – 239.255.255.255 | N/A | N/A | N/A | Multicast |
| E | 240.0.0.0 – 255.255.255.255 | N/A | N/A | N/A | Reserved/Research |

---

## 🔢 IPv6 (Internet Protocol version 6)

- 128-bit address written in hexadecimal (e.g., `2001:0db8:85a3::8a2e:0370:7334`)
- Supports ~340 undecillion addresses (2^128)
- Colons separate 8 groups of 4 hexadecimal digits
- Designed to replace IPv4 and solve address exhaustion
- Supports auto-configuration and built-in security

---

## 🏠 Public vs Private IP Addresses

### Public IP
- Routable on the Internet
- Assigned by ISPs or IANA
- Globally unique

### Private IP
- Used within local networks (LANs)
- Non-routable on the Internet
- Require NAT for internet access


# IP Address Classes – Detailed Guide

This guide provides an in-depth explanation of IPv4 address classes, who uses them, and some advanced and lesser-known details to deepen your understanding.

---

## 📚 What Are IP Address Classes?

IPv4 addresses are divided into five classes based on the leading bits of the address. These classes historically defined the size of networks and were used to allocate address blocks before CIDR was introduced.

---

## 🧾 IPv4 Address Classes and Who Uses Them

### 🅰️ Class A
- **Range:** 0.0.0.0 – 127.255.255.255
- **Default Subnet Mask:** 255.0.0.0 (/8)
- **Hosts per Network:** ~16 million
- **Used By:** Very large organizations, ISPs, early adopters
- **Special Range:** `127.0.0.0/8` reserved for loopback testing (e.g., `127.0.0.1`)

### 🅱️ Class B
- **Range:** 128.0.0.0 – 191.255.255.255
- **Default Subnet Mask:** 255.255.0.0 (/16)
- **Hosts per Network:** ~65,000
- **Used By:** Universities, government agencies, large enterprises

### 🅲️ Class C
- **Range:** 192.0.0.0 – 223.255.255.255
- **Default Subnet Mask:** 255.255.255.0 (/24)
- **Hosts per Network:** 254
- **Used By:** Small businesses, home networks, typical office LANs

### 🅳️ Class D
- **Range:** 224.0.0.0 – 239.255.255.255
- **Purpose:** Multicast only (no subnet mask)
- **Used By:** Streaming services, routing protocols (e.g., OSPF, EIGRP)

### 🅴️ Class E
- **Range:** 240.0.0.0 – 255.255.255.255
- **Purpose:** Experimental and reserved
- **Used By:** Research, development, not routable publicly

---

## 🧠 Advanced and Little-Known Details about Address Classes

### 1. Classful Addressing is Obsolete
- Modern IP addressing uses **CIDR** (Classless Inter-Domain Routing)
- CIDR allows flexible subnetting beyond fixed class boundaries

### 2. Not All IPs in a Class Are Usable
- First IP: **Network Address**
- Last IP: **Broadcast Address**
- These two addresses are **not assignable to hosts**

### 3. Loopback Addresses Reside in Class A
- Entire range `127.0.0.0/8` is reserved
- Most common: `127.0.0.1` (used for local host testing)

### 4. Reserved Ranges Exist in Class B/C
- **APIPA/Link-local:** `169.254.0.0/16` auto-assigned when DHCP fails

### 5. Legacy Allocations Still Exist
- Early organizations received full Class A or B blocks
- These are subnetted internally (e.g., HP, IBM, MIT)

### 6. Class D Has Subcategories for Multicast
| Range | Use |
|-------|-----|
| `224.0.0.x` | Local subnet routing (e.g., OSPF) |
| `224.0.1.x` | Internet multicast |
| `239.0.0.0/8` | Private multicast (enterprise scope) |

### 7. Class E is Disabled by Most Systems
- Packets with Class E addresses are dropped by default on most routers and OSs

### 8. Subnetting Replaced the Need for Class-Based Allocation
- With CIDR, any address can be subnetted flexibly using `/n` notation
- No need to conform to class A/B/C limits

---

## ✅ Summary Table

| Class | Range | Subnet Mask | Usage |
|-------|-------|-------------|-------|
| A | 0.0.0.0 – 127.255.255.255 | 255.0.0.0 (/8) | ISPs, large enterprises |
| B | 128.0.0.0 – 191.255.255.255 | 255.255.0.0 (/16) | Universities, governments |
| C | 192.0.0.0 – 223.255.255.255 | 255.255.255.0 (/24) | Small businesses, homes |
| D | 224.0.0.0 – 239.255.255.255 | N/A | Multicast-only |
| E | 240.0.0.0 – 255.255.255.255 | N/A | Experimental/research |

---

This guide provides all the historical, technical, and advanced context you need to fully understand IPv4 address classes. Ideal for interviews, certifications, and real-world network design.


## 📌 Static vs Dynamic IP Addresses

### Static IP
- Manually configured
- Persistent, does not change
- Common for servers, printers, routers

### Dynamic IP
- Assigned automatically (e.g., via DHCP)
- Can change over time or when reconnecting
- Suitable for end-user devices

---

## 📏 Subnetting: What and Why?

- Divides a network into smaller subnetworks
- Improves performance and security
- Each subnet can represent a department, building, or service type

### Subnet Mask
- Used to determine which part of the IP is network vs host
- Example: `255.255.255.0` (or /24) means first 3 octets are the network portion

#### Example:
- IP: `192.168.1.10`
- Subnet Mask: `255.255.255.0`
- Network: `192.168.1.0`
- Host Range: `192.168.1.1 – 192.168.1.254`
- Broadcast: `192.168.1.255`

---

## 🧮 CIDR – Classless Inter-Domain Routing

- CIDR notation: `IP/prefix` (e.g., `192.168.1.0/24`)
- Allows flexible subnetting
- Replaces classful addressing system

### Common CIDR Blocks

| CIDR | Subnet Mask | # of Hosts |
|------|-------------|------------|
| /8 | 255.0.0.0 | 16,777,214 |
| /16 | 255.255.0.0 | 65,534 |
| /24 | 255.255.255.0 | 254 |
| /30 | 255.255.255.252 | 2 |
| /32 | 255.255.255.255 | 1 (used for loopback, host routes) |

---

## 🧠 Interview Tips

- **Q:** What’s the difference between a public and private IP?  
  **A:** Public IPs are internet-routable and globally unique, while private IPs are used in local networks and require NAT for internet access.

- **Q:** Why is subnetting used?  
  **A:** To divide a large network into smaller, efficient segments and isolate traffic.

- **Q:** What’s the difference between /24 and /30?  
  **A:** /24 gives 254 usable IPs; /30 gives only 2 (used in point-to-point links).

---

This guide covers the most essential and detailed concepts for understanding IP addressing and subnetting in both IPv4 and IPv6 environments.

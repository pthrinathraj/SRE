# 📡 DHCP Process – Dynamic Host Configuration Protocol

This document explains the **DHCP process** used to automatically assign IP addresses and network configuration to clients on a network.

---

## 🧠 What is DHCP?

**DHCP** (Dynamic Host Configuration Protocol) is a client/server protocol that automatically provides IP addresses, subnet masks, default gateways, and DNS servers to network devices.

---

## 🔄 DHCP DORA Process

The process includes **four main steps**, known as **DORA**:

| Step     | Description                                                                 |
|----------|-----------------------------------------------------------------------------|
| 🔍 **Discover** | Client broadcasts `DHCPDISCOVER` to find available DHCP servers.         |
| 📢 **Offer**     | Server replies with `DHCPOFFER`, suggesting an IP address and config.   |
| ✅ **Request**   | Client sends `DHCPREQUEST`, indicating it wants the offered config.     |
| 📨 **Acknowledge** | Server responds with `DHCPACK`, confirming lease of IP and settings.    |

---

## 🧱 Additional DHCP Messages

- **DHCPNAK** – Sent by server if request is invalid or IP is unavailable.
- **DHCPRELEASE** – Sent by client to return the IP before lease expires.
- **DHCPINFORM** – Sent by client to obtain config settings without IP.

---

## ⏳ DHCP Lease

- IPs are assigned for a specific **lease time** (e.g., 24 hours).
- Clients must renew the lease before it expires or request a new one.

---

## 🔁 DHCP Packet Flow

```text
Client                                Server
   |   ----------- DHCPDISCOVER --------->   |
   |   <------------ DHCPOFFER --------------   |
   |   ----------- DHCPREQUEST ------------>   |
   |   <------------ DHCPACK ----------------   |


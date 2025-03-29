# 🌐 DNS – Domain Name System

This README provides an in-depth overview of **DNS (Domain Name System)**, including:

- What DNS is and how it works
- DNS resolution flow
- DNS query types (recursive, iterative, non-recursive) with examples
- DNS record types
- Common DNS interview questions

---

## 📌 What is DNS?

**DNS (Domain Name System)** is like the **internet’s phonebook** – it converts **domain names** (e.g., `example.com`) into **IP addresses** (e.g., `93.184.216.34`) so browsers and other services can load the correct content.

---

## 🔄 What is DNS Resolution?

**DNS resolution** is the process of converting a **domain name** into an **IP address** through a series of lookups between the client and various DNS servers.

### 🧭 Typical Resolution Flow

1. **Client** queries the **Recursive Resolver**
2. If not cached, resolver queries:
   - **Root DNS Server** ➝ refers to TLD
   - **TLD Server** (e.g., `.com`) ➝ refers to authoritative server
   - **Authoritative DNS Server** ➝ returns the IP
3. Resolver sends the IP back to the client

---

## 🔍 Types of DNS Queries

### 🔁 1. Recursive Query

In a **recursive query**, the client (like your browser or OS) asks a **recursive DNS resolver** to resolve the domain **fully**. The resolver then takes responsibility for completing the request – querying other servers as needed – and finally returns the answer to the client.

#### ✅ Example (using `dig` to force recursion):

```bash
dig +recurse example.com @8.8.8.8

Here, Google's public DNS (8.8.8.8) acts as the recursive resolver.

🔄 2. Iterative Query
In an iterative query, the DNS client or server queries another DNS server, which responds with the best answer it has – either:

the final answer, or

a referral to another DNS server (e.g., a root or TLD server)

The client is responsible for making additional queries to follow the trail.

✅ Example:
bash
Copy
Edit
dig +norecurse example.com @a.root-servers.net
This asks a root DNS server. The root won't resolve the domain, but it will refer you to the appropriate TLD servers.

⚡ 3. Non-Recursive Query
A non-recursive query is made when the DNS resolver already knows the answer (from cache or authority) and directly returns it.

No further lookup is required.

✅ Example:
bash
Copy
Edit
dig +norecurse example.com @8.8.8.8
If the server has the answer in its cache or is authoritative for the domain, it will respond. Otherwise, it may return a referral or nothing.

🧾 Types of DNS Records
Record	Purpose
A	Maps a domain to an IPv4 address
AAAA	Maps a domain to an IPv6 address
CNAME	Alias for another domain name
MX	Mail server responsible for email delivery
NS	Name server for a domain
PTR	Reverse lookup: IP ➝ domain
SOA	Contains admin info & settings for the domain
TXT	Arbitrary text (often used for SPF, DKIM, verification)
SRV	Defines location of services (e.g., SIP, LDAP)
CAA	Specifies which CAs are allowed to issue certs
📡 Types of DNS Servers
Server Type	Description
Recursive Resolver	Handles client queries and does full resolution
Root Name Server	Directs to appropriate TLD server
TLD Server	Handles top-level domains like .com, .org
Authoritative Server	Provides final DNS records for a domain
🧠 Common DNS Interview Questions
🧩 Basics
What is DNS and why is it needed?

Explain the purpose of an A record.

How does DNS resolution work?

⚙️ Intermediate
What’s the difference between recursive and iterative queries?

What is a CNAME record, and how is it used?

What happens if a DNS server is down?

🚀 Advanced
What is DNS caching and TTL?

What is DNS poisoning/spoofing?

How does DNSSEC improve security?

How can you troubleshoot DNS with dig, nslookup, or tcpdump?

🛠️ Useful Commands
🔍 Lookup A record:
bash
Copy
Edit
dig example.com
📋 Check authoritative name servers:
bash
Copy
Edit
dig NS example.com
📩 Mail server (MX record):
bash
Copy
Edit
dig MX example.com
🔄 Reverse DNS lookup:
bash
Copy
Edit
dig -x 93.184.216.34
🔬 Detailed tracing of DNS resolution:
bash
Copy
Edit
dig +trace example.com
📚 Resources
How DNS Works – Cloudflare

IANA Root Servers

RFC 1035 – DNS Protocol

✅ Summary
Type	Who Resolves It	Example Scenario
Recursive	Resolver does full lookup	Client ➝ Google DNS (8.8.8.8)
Iterative	Each DNS server gives referral	Resolver ➝ Root ➝ TLD ➝ Authoritative
Non-Recursive	Resolver answers from cache	Fast response if recently queried
 

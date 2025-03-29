
# 2.1 Essential Networking Tools – In-Depth Guide

This guide explores essential command-line and GUI-based networking tools every system administrator, network engineer, or SRE should know. Each tool includes usage, sample output, and output interpretation.

---

## 🛠️ 1. `ping`
- **Purpose:** Checks host reachability and round-trip time.
- **Protocol:** ICMP Echo Request/Reply

### 🔹 Common Usage:
```bash
ping google.com
ping -c 5 8.8.8.8   # send 5 packets
```

### 📤 Sample Output:
```
PING google.com (142.250.190.78) 56(84) bytes of data.
64 bytes from 142.250.190.78: icmp_seq=1 ttl=115 time=12.5 ms
64 bytes from 142.250.190.78: icmp_seq=2 ttl=115 time=11.8 ms

--- google.com ping statistics ---
5 packets transmitted, 5 received, 0% packet loss, time 4004ms
rtt min/avg/max/mdev = 11.836/12.146/12.512/0.269 ms
```

### 🧠 Output Interpretation:
- RTT (`time=12.5 ms`) indicates latency.
- `0% packet loss` confirms host is reachable.
- TTL (Time To Live) suggests number of hops left.

---

## 🛠️ 2. `traceroute` / `tracert`
- **Purpose:** Displays the path packets take to a destination.

### 🔹 Usage:
```bash
traceroute google.com     # Linux
tracert google.com        # Windows
```

### 📤 Sample Output:
```
 1  192.168.1.1 (192.168.1.1)  1.123 ms  0.678 ms  0.574 ms
 2  10.0.0.1 (10.0.0.1)  5.034 ms  4.897 ms  5.112 ms
 3  * * *
 4  172.217.3.110 (172.217.3.110)  20.123 ms  19.984 ms  20.011 ms
```

### 🧠 Output Interpretation:
- Each line is a router hop.
- `* * *` means no response (possibly filtered ICMP).
- Final hop is destination IP and response time.

---

## 🛠️ 3. `nslookup` / `dig`
- **Purpose:** Performs DNS queries.

### 🔹 `nslookup` Example:
```bash
nslookup example.com
```

### 📤 Output:
```
Server:  8.8.8.8
Address: 8.8.8.8#53

Non-authoritative answer:
Name:    example.com
Address: 93.184.216.34
```

### 🔹 `dig` Example:
```bash
dig example.com
```

### 📤 Output:
```
;; QUESTION SECTION:
;example.com.       IN  A

;; ANSWER SECTION:
example.com.  3600  IN  A  93.184.216.34
```

### 🧠 Output Interpretation:
- Shows DNS resolution path.
- IP address found in `ANSWER SECTION`.
- TTL and DNS server info also displayed.

---

## 🛠️ 4. `ip` and `ifconfig`
- **Purpose:** View and manage network interfaces, IPs, and routes.

### 🔹 Examples:
```bash
ip addr show
ip link set eth0 up
ip route show
```

### 📤 Sample Output (`ip addr show`):
```
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500
    inet 192.168.1.100/24 brd 192.168.1.255 scope global dynamic eth0
```

### 🧠 Output Interpretation:
- `eth0` is interface name.
- `inet` line shows assigned IP, subnet, and broadcast.
- `UP` means interface is active.

---

## 🛠️ 5. `netstat` / `ss`
- **Purpose:** Displays active connections and listening ports.

### 🔹 Usage:
```bash
ss -tulnp
netstat -an | grep LISTEN
```

### 📤 Output (`ss -tulnp`):
```
Netid State      Local Address:Port   Peer Address:Port  Process
udp   UNCONN     0.0.0.0:68           0.0.0.0:*           -
tcp   LISTEN     0.0.0.0:22           0.0.0.0:*           1234/sshd
```

### 🧠 Output Interpretation:
- `LISTEN` indicates a service is awaiting connections.
- Port `22` used by SSH.
- `1234/sshd` shows process ID and name.

---

## 🛠️ 6. `tcpdump`
- **Purpose:** Captures and analyzes network packets in real time.

### 🔹 Basic Usage:
```bash
tcpdump -i eth0 port 80
```

### 📤 Sample Output:
```
12:01:55.123456 IP 192.168.1.100.54321 > 93.184.216.34.80: Flags [S], seq 12345678, win 64240, length 0
```

### 🧠 Output Interpretation:
- Shows source IP and port (`192.168.1.100.54321`) connecting to destination (`93.184.216.34.80`).
- `Flags [S]` indicates a SYN packet (start of TCP handshake).

---

## 🛠️ 7. `nmap`
- **Purpose:** Network scanner used to discover hosts and services.

### 🔹 Examples:
```bash
nmap -sP 192.168.1.0/24       # Ping scan
nmap -sV 192.168.1.10         # Service version detection
```

### 📤 Sample Output (`nmap -sV`):
```
PORT     STATE SERVICE VERSION
22/tcp   open  ssh     OpenSSH 7.9
80/tcp   open  http    Apache httpd 2.4.29
```

### 🧠 Output Interpretation:
- Shows open ports and associated services.
- `22/tcp` is SSH with version info.
- Helps identify exposed and vulnerable services.

---

## 🧪 8. Wireshark
- **Purpose:** GUI-based packet capture and analysis tool

### 🔹 Usage:
- Start capture on desired interface
- Use filters like `http`, `tcp.port == 443`, `ip.addr == 192.168.1.100`

### 📤 Output (GUI):
- Packet list pane (timestamp, source/destination, protocol)
- Packet details (headers, flags, payloads)

### 🧠 Output Interpretation:
- Inspect handshake, latency, retransmissions, and malformed packets
- Color-coded protocols for quick analysis

---

## ✅ Summary Table

| Tool | Purpose | Sample Command | Output Interprets |
|------|---------|----------------|-------------------|
| `ping` | Host reachability | `ping google.com` | ICMP RTT, packet loss |
| `traceroute` | Path to host | `traceroute 8.8.8.8` | Hop-by-hop latency |
| `dig` / `nslookup` | DNS query | `dig example.com` | DNS server & A record |
| `ip` / `ifconfig` | Interface config | `ip addr show` | IPs, status, MAC |
| `ss` / `netstat` | Open ports | `ss -tulnp` | Listening services |
| `tcpdump` | Capture traffic | `tcpdump -i eth0` | Low-level packets |
| `nmap` | Scan hosts/ports | `nmap -sV 192.168.1.10` | Open ports, services |
| `Wireshark` | GUI packet analysis | GUI tool | Full packet dissection |

---

This concludes **2.1 – Essential Networking Tools** with complete usage and interpretation. Next: 2.2 – Network Interface Management.

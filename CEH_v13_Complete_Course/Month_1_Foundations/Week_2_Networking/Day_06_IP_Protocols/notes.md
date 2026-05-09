# Day 06 — IP Addressing, Ports & Protocols

## [TOPIC OVERVIEW]
IP addressing is the foundation of all network communication. Every device on a network needs a unique identifier — an IP address — to send and receive data. As an ethical hacker, you must be fluent in IP addressing, subnetting, and the core protocols that make networks function, because reconnaissance, scanning, and exploitation all depend on this knowledge. You cannot target what you cannot address.

**CEH v13 connection:** Module 03 (Scanning Networks) assumes complete fluency in IP addressing and protocols. Subnet calculations appear directly on the exam.

---
## [KEY CONCEPTS]

### IPv4 Address Structure
IPv4 addresses are 32-bit numbers written in dotted-decimal: `192.168.1.100`
Each octet = 8 bits = values 0–255.

**Address Classes:**
| Class | Range | Default Mask | Purpose |
|-------|-------|-------------|---------|
| A | 1.0.0.0–126.255.255.255 | /8 (255.0.0.0) | Large networks |
| B | 128.0.0.0–191.255.255.255 | /16 (255.255.0.0) | Medium networks |
| C | 192.0.0.0–223.255.255.255 | /24 (255.255.255.0) | Small networks |
| D | 224.0.0.0–239.255.255.255 | N/A | Multicast |
| E | 240.0.0.0–255.255.255.255 | N/A | Reserved/Research |

**Private IP Ranges (RFC 1918):**
| Range | CIDR | Class |
|-------|------|-------|
| 10.0.0.0–10.255.255.255 | 10.0.0.0/8 | A |
| 172.16.0.0–172.31.255.255 | 172.16.0.0/12 | B |
| 192.168.0.0–192.168.255.255 | 192.168.0.0/16 | C |

**Loopback:** 127.0.0.1 — always refers to "this machine"
**APIPA:** 169.254.0.0/16 — auto-assigned when DHCP fails

### CIDR Notation & Subnetting
CIDR (Classless Inter-Domain Routing) uses a prefix to define the network portion:

| CIDR | Subnet Mask | Hosts | Usable Hosts |
|------|------------|-------|-------------|
| /8 | 255.0.0.0 | 16,777,216 | 16,777,214 |
| /16 | 255.255.0.0 | 65,536 | 65,534 |
| /24 | 255.255.255.0 | 256 | 254 |
| /25 | 255.255.255.128 | 128 | 126 |
| /26 | 255.255.255.192 | 64 | 62 |
| /27 | 255.255.255.224 | 32 | 30 |
| /28 | 255.255.255.240 | 16 | 14 |
| /30 | 255.255.255.252 | 4 | 2 |

**Example — 192.168.1.0/26:**
- Network address: 192.168.1.0
- Broadcast: 192.168.1.63
- Usable range: 192.168.1.1 – 192.168.1.62
- Total usable hosts: 62

### IPv6 Basics
IPv6 = 128-bit addresses written as 8 groups of 4 hex digits:
`2001:0db8:85a3:0000:0000:8a2e:0370:7334`
Shorthand: consecutive zero groups → `::` (only once)
`2001:db8::1`

**Key IPv6 types:**
- Global Unicast: `2000::/3` — routable on internet
- Link-Local: `fe80::/10` — same link only (like 169.254.x.x)
- Loopback: `::1` (equivalent of 127.0.0.1)

### TCP vs UDP Comparison
| Feature | TCP | UDP |
|---------|-----|-----|
| Connection | Yes (3-way handshake) | No |
| Reliability | Guaranteed | Best-effort |
| Speed | Slower | Faster |
| Use case | HTTP, SSH, FTP | DNS, VoIP, DHCP |
| Header | 20 bytes | 8 bytes |

### DNS Resolution Process
```
User types: www.google.com
    ↓
1. Check local cache (/etc/hosts on Linux, browser cache)
    ↓
2. Query Recursive Resolver (your ISP or 8.8.8.8)
    ↓
3. Resolver queries Root Server → learns TLD (.com) nameserver
    ↓
4. Resolver queries .com TLD server → learns google.com nameserver
    ↓
5. Resolver queries google.com nameserver → gets IP
    ↓
6. Resolver returns IP to client → browser connects
```

### ARP — Address Resolution Protocol
ARP maps IP addresses (Layer 3) to MAC addresses (Layer 2):
```
Who has 192.168.1.1? Tell 192.168.1.50   ← ARP Request (broadcast)
192.168.1.1 is at 00:1A:2B:3C:4D:5E     ← ARP Reply (unicast)
```
ARP has NO authentication — this is why ARP spoofing works.

### TLS Handshake (HTTPS)
```
Client → Server: ClientHello (TLS version, cipher suites)
Server → Client: ServerHello + Certificate
Client verifies certificate against trusted CAs
Client → Server: ClientKeyExchange (encrypted pre-master secret)
Both sides derive session keys
Client → Server: ChangeCipherSpec + Finished
Server → Client: ChangeCipherSpec + Finished
Encrypted communication begins
```

---
## [CEH EXAM FOCUS]
1. Subnet calculation — given CIDR, find network/broadcast/range/host count
2. Private vs public IP ranges — know all three RFC 1918 ranges
3. DNS record types (covered Day 11 in depth)
4. TCP vs UDP — which protocol for which service
5. ARP — how it works, why it's vulnerable

### Tricky Areas
- Class D (224–239) is multicast, NOT private
- /31 has 2 IPs (no usable hosts traditionally, but RFC 3021 allows point-to-point use)
- DNS uses UDP for queries but TCP for zone transfers AND responses >512 bytes

---
## [REAL-WORLD CONTEXT]
### BGP Hijacking — Pakistan Telecom vs YouTube (2008)
Pakistan Telecom accidentally announced a more-specific BGP route for YouTube's IP block (Layer 3 routing attack), redirecting global YouTube traffic through their network for ~2 hours. This demonstrates how IP routing protocols have minimal authentication — a fundamental Layer 3 weakness.

---
**Key Takeaway:** Mastering IP addressing is non-negotiable. You cannot scan, enumerate, or exploit targets without knowing exactly which IPs belong to the scope and what their network boundaries are. Practice subnet calculation until it is automatic.

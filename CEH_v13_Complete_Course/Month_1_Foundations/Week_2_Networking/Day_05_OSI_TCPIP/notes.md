# Day 05 — OSI Model & TCP/IP Stack

## [TOPIC OVERVIEW]

The **OSI (Open Systems Interconnection) model** is a conceptual framework that standardizes how different network systems communicate. Created by ISO in 1984, it divides network communication into **7 layers**, each with a specific role. While modern networks use the TCP/IP model in practice, the OSI model remains the universal language for describing network behavior — and it is heavily tested on the CEH exam.

Understanding these models helps you know exactly *where* an attack occurs in the network stack, which determines which tools to use and which defenses apply. A SYN flood attacks Layer 4. ARP spoofing attacks Layer 2. DNS poisoning attacks Layer 7. This layer-awareness is the mark of a professional.

**CEH v13 connection:** Module 02 and Module 03 reference OSI/TCP-IP extensively. Roughly 8-10% of CEH exam questions reference layer-specific behavior or protocol placement.

---

## [KEY CONCEPTS]

### The 7 OSI Layers

**Mnemonic (top-down):** "All People Seem To Need Data Processing"
**Mnemonic (bottom-up):** "Please Do Not Throw Sausage Pizza Away"

| Layer | Name | PDU | Key Protocols | Devices |
|-------|------|-----|--------------|---------|
| 7 | Application | Data | HTTP, HTTPS, FTP, SMTP, DNS, SSH | Proxy, WAF |
| 6 | Presentation | Data | SSL/TLS, JPEG, MPEG, ASCII, encryption | - |
| 5 | Session | Data | NetBIOS, RPC, SQL sessions | - |
| 4 | Transport | Segment | TCP, UDP | Firewall |
| 3 | Network | Packet | IP, ICMP, OSPF, BGP | Router |
| 2 | Data Link | Frame | Ethernet, ARP, MAC, 802.11 (Wi-Fi) | Switch |
| 1 | Physical | Bit | Ethernet cable, fiber, radio waves | Hub, NIC |

**Layer 7 — Application:** Where user-facing protocols live. HTTP requests, DNS queries, FTP transfers. Attacks: XSS, SQLi, phishing, DNS poisoning.

**Layer 6 — Presentation:** Data formatting, encryption/decryption, compression. SSL/TLS operates here (though some argue Layer 4-7). Attacks: SSL stripping, weak cipher negotiation.

**Layer 5 — Session:** Manages communication sessions between applications. Attacks: session hijacking.

**Layer 4 — Transport:** Reliable (TCP) or unreliable (UDP) delivery. Port numbers live here. Attacks: SYN flood, port scanning, UDP flood.

**Layer 3 — Network:** IP addressing and routing. Packets hop between routers here. Attacks: IP spoofing, ICMP attacks, BGP hijacking.

**Layer 2 — Data Link:** MAC addresses, frame delivery on local network. Attacks: ARP spoofing, MAC flooding, VLAN hopping.

**Layer 1 — Physical:** Raw bits over physical medium. Attacks: physical cable tap, jamming wireless signals.

---

### TCP vs UDP

| Feature | TCP | UDP |
|---------|-----|-----|
| Connection | Connection-oriented (3-way handshake) | Connectionless |
| Reliability | Guaranteed delivery, retransmission | Best-effort, no retransmission |
| Speed | Slower (overhead) | Faster (no overhead) |
| Order | Packets delivered in order | No ordering guarantee |
| Use cases | HTTP, SSH, FTP, SMTP | DNS, VoIP, video streaming, DHCP |
| Header size | 20 bytes minimum | 8 bytes |

---

### TCP 3-Way Handshake

```
Client                    Server
  |                          |
  |-------- SYN ----------->|   (Client wants to connect, sends ISN)
  |                          |
  |<------ SYN-ACK ---------|   (Server acknowledges, sends its ISN)
  |                          |
  |-------- ACK ----------->|   (Client acknowledges server's ISN)
  |                          |
  |===== Connection Established =====|
```

**SYN flood attack:** Attacker sends thousands of SYN packets but never completes the handshake. Server allocates resources for each half-open connection until it runs out of memory. Defense: SYN cookies.

### TCP 4-Way Termination

```
Client ----FIN----> Server    (Client done sending)
Client <---ACK----- Server    (Server acknowledges)
Client <---FIN----- Server    (Server done sending)
Client ----ACK----> Server    (Client acknowledges)
```

---

### Common Ports — Must Memorize

| Port | Protocol | Service |
|------|---------|---------|
| 20/21 | TCP | FTP (data/control) |
| 22 | TCP | SSH |
| 23 | TCP | Telnet (unencrypted) |
| 25 | TCP | SMTP (email sending) |
| 53 | TCP/UDP | DNS |
| 67/68 | UDP | DHCP (server/client) |
| 80 | TCP | HTTP |
| 110 | TCP | POP3 (email receive) |
| 143 | TCP | IMAP |
| 161/162 | UDP | SNMP |
| 389 | TCP | LDAP |
| 443 | TCP | HTTPS |
| 445 | TCP | SMB |
| 3306 | TCP | MySQL |
| 3389 | TCP | RDP |
| 8080 | TCP | HTTP-alt / proxy |

---

### TCP/IP 4-Layer Model

The TCP/IP model (DoD model) is what the internet actually uses:

| TCP/IP Layer | Corresponds to OSI | Protocols |
|-------------|-------------------|----------|
| Application | Layers 5, 6, 7 | HTTP, DNS, FTP, SMTP |
| Transport | Layer 4 | TCP, UDP |
| Internet | Layer 3 | IP, ICMP, ARP |
| Network Access | Layers 1, 2 | Ethernet, 802.11 |

---

## [CEH EXAM FOCUS]

1. **Layer identification** — "ARP operates at which OSI layer?" (Layer 2)
2. **TCP vs UDP** — When each is used and why
3. **3-way handshake** — Sequence of flags: SYN → SYN-ACK → ACK
4. **Port numbers** — Know the table above cold
5. **PDU names** — Bit (L1), Frame (L2), Packet (L3), Segment (L4), Data (L5-7)

### Tricky Areas
- **ARP is Layer 2**, not Layer 3, even though it resolves IP (Layer 3) addresses
- **DNS uses both TCP and UDP** — UDP for queries (port 53), TCP for zone transfers (port 53)
- **HTTPS is Layer 7**, not Layer 6 — TLS encryption happens within the Layer 7 protocol
- OSI layers 5, 6, 7 are often collapsed in practice; focus on 1-4 for attacks

---

## [REAL-WORLD CONTEXT]

### Case Study: Mirai Botnet DDoS (2016)

Mirai infected IoT devices (cameras, routers, DVRs) with default credentials and used them to launch massive UDP and TCP SYN flood attacks against Dyn DNS at Layer 3/4. The attack peaked at 1.2 Tbps, taking down DNS resolution for Twitter, Netflix, Reddit, and GitHub for hours.

**Layer analysis:** The attack was a Layer 3 (IP-level) and Layer 4 (UDP flood, SYN flood) attack. Defense required volumetric scrubbing at Layer 3 before the traffic could be inspected at higher layers. Cloudflare and similar CDN-based DDoS mitigation services absorb these attacks across distributed infrastructure.

---

**Key Takeaway:** Every tool and attack in this course operates at a specific OSI layer. Always ask "which layer?" — it tells you which protocol is involved, which tool to use, and which defense applies.

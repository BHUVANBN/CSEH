# Day 06 — Practical: IP Configuration & Protocol Analysis

> **Time Estimate:** 1.5 hours
> **⚠️ Safety Warning:** Use only your lab VMs and your own network interfaces.

---
## [ENVIRONMENT NEEDED]
- OS: Kali Linux
- Tools: ip, ping, traceroute, nslookup, dig, curl, arp (pre-installed)
- Install if missing: `sudo apt install iproute2 dnsutils curl net-tools -y`

---
## [STEP-BY-STEP PRACTICAL]

### Part 1: IP & Routing

**1.** View your IP addresses:
```bash
ip addr show
```
Note eth0 (NAT), eth1 (Host-Only) IP addresses.

**2.** View routing table:
```bash
ip route show
```
Identify: default gateway, connected networks.

**3.** Ping tests:
```bash
ping -c 4 8.8.8.8           # Internet (via NAT)
ping -c 4 192.168.56.102    # Metasploitable2 (Host-Only)
```

**4.** Trace the path to Google:
```bash
traceroute 8.8.8.8
traceroute -n 8.8.8.8       # No DNS resolution
```
Expected: Hops through your router, ISP, then Google infrastructure.

### Part 2: DNS Queries with dig

**5.** Basic A record lookup:
```bash
dig google.com
```

**6.** Query specific record types:
```bash
dig google.com MX            # Mail records
dig google.com NS            # Nameservers
dig google.com TXT           # Text records (SPF, DKIM)
dig google.com AAAA          # IPv6 address
```

**7.** Reverse DNS lookup:
```bash
dig -x 8.8.8.8
```

**8.** nslookup (alternative):
```bash
nslookup google.com
nslookup -type=MX google.com
nslookup -type=NS google.com
```

### Part 3: HTTP Headers with curl

**9.** View full HTTP transaction:
```bash
curl -v http://example.com 2>&1 | head -50
```

**10.** View response headers only:
```bash
curl -I http://example.com
```

**11.** Simulate a POST request:
```bash
curl -X POST -d "user=admin&pass=test" http://httpbin.org/post
```

### Part 4: ARP Table

**12.** View ARP cache:
```bash
arp -a
```
Expected: IP to MAC mappings of devices on your local network.

**13.** Generate ARP entries by pinging:
```bash
ping -c 1 192.168.56.102
arp -a | grep 192.168.56
```

### Part 5: Subnet Calculation Practice

**14.** Calculate manually, then verify with `ipcalc`:
```bash
sudo apt install ipcalc -y
ipcalc 192.168.1.0/26
ipcalc 10.0.0.0/8
ipcalc 172.16.50.0/28
```
Expected: Network, broadcast, first host, last host, total hosts.

---
## [TOOL REFERENCE]

```bash
ip addr show                 # Interface IPs
ip route show                # Routing table
ping -c 4 <host>             # ICMP ping
traceroute <host>            # Path tracing
dig <domain>                 # DNS lookup
dig <domain> <type>          # Specific record type
nslookup <domain>            # DNS lookup (interactive)
curl -v <url>                # Verbose HTTP request
curl -I <url>                # Headers only
arp -a                       # ARP cache
ipcalc <cidr>                # Subnet calculator
```

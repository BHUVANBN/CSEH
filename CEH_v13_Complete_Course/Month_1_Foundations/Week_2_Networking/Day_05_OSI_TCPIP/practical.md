# Day 05 — Practical: Capturing & Analyzing Network Traffic

> **Time Estimate:** 1.5–2 hours
> **⚠️ Safety Warning:** Capture traffic only on your own lab network (Host-Only VirtualBox network). Never capture on public or corporate Wi-Fi networks without explicit authorization.

---

## [ENVIRONMENT NEEDED]

- **OS:** Kali Linux
- **Tools:** wireshark, tcpdump, nmap, netstat/ss (pre-installed)
- Install if needed: `sudo apt install wireshark tcpdump nmap -y`
- **Target:** Metasploitable2 VM (from Day 01 setup)

---

## [STEP-BY-STEP PRACTICAL]

### Part 1: View Open Ports on Your Kali Machine

**1.** List all listening ports:
```bash
ss -tuln
```
Expected: Table showing protocol, local address, port, process.

**2.** Alternative with netstat:
```bash
netstat -tuln
```

**3.** Show ports with process names:
```bash
sudo ss -tulnp
```

### Part 2: Capture Traffic with tcpdump

**4.** Start a basic capture:
```bash
sudo tcpdump -i eth1 -n
```
Expected: Real-time packet output. Press Ctrl+C to stop.

**5.** Filter for TCP only:
```bash
sudo tcpdump -i eth1 tcp -n
```

**6.** Capture TCP handshake — open another terminal and ping Metasploitable2:
```bash
# Terminal 1: Start capture
sudo tcpdump -i eth1 -n 'tcp[tcpflags] & (tcp-syn|tcp-ack) != 0'

# Terminal 2: Generate TCP traffic
nmap -sT 192.168.56.102 -p 22
```
Expected: See SYN, SYN-ACK, ACK sequences in output.

**7.** Save capture to file:
```bash
sudo tcpdump -i eth1 -w ~/CEH_Labs/Week2/Day05/capture.pcap -c 100
```

### Part 3: Analyze Traffic with Wireshark

**8.** Launch Wireshark:
```bash
sudo wireshark &
```

**9.** Open your saved capture:
File → Open → navigate to `~/CEH_Labs/Week2/Day05/capture.pcap`

**10.** Apply display filters:
```
tcp.flags.syn == 1                    # Show only SYN packets
tcp.flags.syn == 1 && tcp.flags.ack == 0   # Show only initial SYN
tcp.port == 22                        # SSH traffic
http                                  # HTTP only
dns                                   # DNS queries
```

**11.** Capture a live DNS query:
```bash
# Terminal 1: Capture DNS
sudo tcpdump -i eth0 port 53 -n -w dns_capture.pcap

# Terminal 2: Generate DNS query
nslookup google.com
```
Open dns_capture.pcap in Wireshark — you can see the query and response.

### Part 4: Scan Ports with Nmap

**12.** TCP connect scan:
```bash
nmap -sT 192.168.56.102
```

**13.** View listening services on Metasploitable2 from Kali:
```bash
nmap -sT -p 1-1024 192.168.56.102
```
Expected: Long list of open ports (Metasploitable2 is intentionally vulnerable).

---

## [TOOL REFERENCE]

### tcpdump Cheatsheet

```bash
tcpdump -i eth0               # Capture on interface eth0
tcpdump -i eth0 -n            # No DNS resolution (faster)
tcpdump -i eth0 -v            # Verbose output
tcpdump -i eth0 -w file.pcap  # Write to file
tcpdump -r file.pcap          # Read from file
tcpdump host 192.168.1.1      # Filter by host
tcpdump port 80               # Filter by port
tcpdump tcp                   # Filter by protocol
tcpdump -c 100                # Capture only 100 packets
```

### Wireshark Display Filters

```
http                          # HTTP traffic
tcp.port == 80                # TCP port 80
ip.addr == 192.168.1.1        # Traffic to/from IP
tcp.flags.syn == 1            # SYN packets
dns                           # DNS traffic
http.request.method == "POST" # HTTP POST requests
```

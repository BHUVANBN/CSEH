# Day 06 — Assignment: IP Addressing & Protocols

> **Difficulty:** Beginner
> **Estimated Time:** 1.5 hours

---
## [THEORY QUESTIONS]

**Q1.** Calculate for 192.168.10.0/27: network address, broadcast, usable IP range, number of usable hosts.

**Q2.** What is the difference between a public and private IP address? Why can't two devices on the internet have the same private IP if millions of networks use 192.168.1.0/24?

**Q3.** Explain the ARP process. Why is ARP considered a security weakness? What attack exploits it?

**Q4.** What is the purpose of DNS TTL (Time to Live)? How can a short TTL be used by an attacker?

**Q5.** Why does HTTPS not fully protect against all attacks? Name two things HTTPS does NOT protect against.

---
## [PRACTICAL TASK]

Perform subnet calculations for these 5 CIDR blocks and document results in a table:
- 10.0.0.0/24
- 192.168.100.0/26
- 172.16.0.0/20
- 10.10.10.128/25
- 192.168.1.240/28

For each: Network address, Broadcast, First usable, Last usable, Total usable hosts.

Use dig to find DNS records for 3 websites of your choice. Document: A, MX, NS, TXT records.

```bash
nano ~/CEH_Labs/Week2/Day06/dns_records.md
```

---
## [CHALLENGE]

Write a bash script that takes a CIDR as input and outputs: network, broadcast, and all usable IPs:
```bash
nano ~/CEH_Labs/Week2/Day06/subnet_calc.sh
```

---
## [REFLECTION]

**R1.** NAT (Network Address Translation) allows thousands of devices to share one public IP. How does this affect an attacker trying to trace an attack back to a specific device?

**R2.** IPv6 eliminates the need for NAT. Does this make tracking attackers easier or harder? Explain.

---
## [SELF-CHECK]
- [ ] I can calculate network/broadcast/range from CIDR notation
- [ ] I know all three RFC 1918 private IP ranges
- [ ] I know what DNS records A, MX, NS, TXT, CNAME, PTR mean
- [ ] I ran dig, nslookup, and curl successfully
- [ ] I understand how ARP works and why it's vulnerable
- [ ] I understand the TLS handshake process
- [ ] I completed the subnet calculation table

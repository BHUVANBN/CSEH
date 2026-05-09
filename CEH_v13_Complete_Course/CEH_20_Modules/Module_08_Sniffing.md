# CEH Module 08 — Sniffing

## Module Overview
**Module 08: Sniffing** is an official EC-Council CEH v13 module covering: passive vs active sniffing, promiscuous mode, ARP poisoning MITM, Wireshark filters, tcpdump, Ettercap Bettercap, SSL stripping, HSTS, MAC flooding, DHCP starvation.

**Maps to course days:** Day 19

---
## Key Concepts & Definitions

This module introduces the following core concepts that are directly tested on the CEH exam:

**Primary topics:** passive vs active sniffing, promiscuous mode, ARP poisoning MITM, Wireshark filters, tcpdump, Ettercap Bettercap, SSL stripping, HSTS, MAC flooding, DHCP starvation

For each concept, understand:
- **Definition** — What it is in plain English
- **Mechanism** — How it works technically  
- **Attack use** — How attackers exploit it
- **Defense** — How defenders detect/prevent it

### Concept Deep Dive

The topics in this module (passive vs active sniffing, promiscuous mode, ARP poisoning MITM, Wireshark filters, tcpdump, Ettercap Bettercap, SSL stripping, HSTS, MAC flooding, DHCP starvation) build on each other sequentially. Review the corresponding day notes for full explanations, ASCII diagrams, and comparison tables.

**Key relationships:**
- Each tool in this module has a specific use case — know when to use each
- Each attack technique has a corresponding defensive control
- Each protocol weakness has a specific CVE category (check NVD for examples)

---
## Tools Covered in This Module

**Primary tools:** sudo wireshark, tcpdump -i eth0 -w cap.pcap, bettercap -iface eth0, arp.spoof on

### Syntax Reference

```bash
# Tools for Module 08: Sniffing
sudo wireshark, tcpdump -i eth0 -w cap.pcap, bettercap -iface eth0, arp.spoof on

# General usage pattern:
# tool [options] [target]
# Always check: tool --help for full flag list
```

### Tool Comparison

| Tool | Purpose | When to Use | Key Flag |
|------|---------|------------|---------|
| (See tools list above) | Refer to day notes | Based on target/objective | -h for help |

---
## CEH Exam Question Areas

**High-frequency exam topics for Module 08:**
1. Definitions and distinctions between related terms
2. Tool selection for specific scenarios
3. Protocol mechanics and vulnerability exploitation
4. Defensive countermeasures and detection methods
5. Legal and ethical considerations

**Common question formats:**
- "Which tool is BEST suited for..."
- "An attacker wants to... which technique?"
- "What is the PRIMARY difference between X and Y?"
- "Which of the following is NOT a characteristic of..."

---
## Practice Questions with Answers

**Q1:** ARP poisoning works because ARP: A) Uses encryption B) Has no authentication mechanism C) Requires root access D) Only works on IPv6

**Answer:** B) Has no authentication mechanism

**Explanation:** This is a core concept tested in Module 08. Know the exact definition and be able to distinguish it from similar options.

---

**Q2:** Which Wireshark filter shows only HTTP POST requests? A) http B) tcp.port==80 C) http.request.method=="POST" D) post

**Answer:** C) http.request.method=="POST"

**Explanation:** CEH exam frequently tests tool knowledge and scan/attack type identification. Memorize which tool does what and which flag triggers which behavior.

---

**Q3:** MAC flooding attacks: A) Routers B) Network switches, converting them to hubs C) Firewalls D) DNS servers

**Answer:** B) Network switches, converting them to hubs

**Explanation:** Scenario-based questions require applying conceptual knowledge. Always eliminate obviously wrong answers first, then distinguish between the two most plausible options.

---
## Quick Reference Cheatsheet

```bash
# ── MODULE 08: SNIFFING ──────────────────────────────
# Topics: passive vs active sniffing, promiscuous mode, ARP poisoning MITM, Wireshark filters, tcpdump, Ettercap Bettercap, SSL stripping, HSTS, MAC flooding, DHCP starvation
# Tools:  sudo wireshark, tcpdump -i eth0 -w cap.pcap, bettercap -iface eth0, arp.spoof on

# Core commands:
# (See practical.md for days: Day 19)

# Nmap for this module:
nmap -sV -sC --script default 192.168.56.102

# Save all output:
command 2>&1 | tee module08_output.txt

# Reference CVEs: Search NVD for terms in this module
# Reference TTP: Search MITRE ATT&CK for technique names
```

### Key Terms Glossary

Review all terms in: **passive vs active sniffing, promiscuous mode, ARP poisoning MITM, Wireshark filters, tcpdump, Ettercap Bettercap, SSL stripping, HSTS, MAC flooding, DHCP starvation**

For the CEH exam, be able to:
- Define each term in one sentence
- Give a real-world example
- Identify the correct tool or defense

---
## Mapping to Daily Course Content

| Day | Topic | Module 08 Connection |
|-----|-------|------------------------|
| Day 19 | See course calendar | Primary coverage |
| Day 19 | See course calendar | Extended coverage |

**Study sequence:** Read notes.md for the mapped days before reviewing this module file. The daily notes provide the detailed technical content; this module file provides the exam-focused synthesis.

---
*Module 08 of 20 | CEH v13 | Review with MASTER_NOTES.md for complete exam prep*

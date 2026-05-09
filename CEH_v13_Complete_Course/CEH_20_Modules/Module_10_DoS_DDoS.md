# CEH Module 10 — DoS & DDoS

## Module Overview
**Module 10: DoS & DDoS** is an official EC-Council CEH v13 module covering: volumetric protocol application layer attacks, SYN flood UDP flood ICMP flood Slowloris HTTP flood, botnets C2, amplification attacks DNS NTP SSDP, DDoS mitigation CDN scrubbing rate limiting.

**Maps to course days:** Days 05, 26

---
## Key Concepts & Definitions

This module introduces the following core concepts that are directly tested on the CEH exam:

**Primary topics:** volumetric protocol application layer attacks, SYN flood UDP flood ICMP flood Slowloris HTTP flood, botnets C2, amplification attacks DNS NTP SSDP, DDoS mitigation CDN scrubbing rate limiting

For each concept, understand:
- **Definition** — What it is in plain English
- **Mechanism** — How it works technically  
- **Attack use** — How attackers exploit it
- **Defense** — How defenders detect/prevent it

### Concept Deep Dive

The topics in this module (volumetric protocol application layer attacks, SYN flood UDP flood ICMP flood Slowloris HTTP flood, botnets C2, amplification attacks DNS NTP SSDP, DDoS mitigation CDN scrubbing rate limiting) build on each other sequentially. Review the corresponding day notes for full explanations, ASCII diagrams, and comparison tables.

**Key relationships:**
- Each tool in this module has a specific use case — know when to use each
- Each attack technique has a corresponding defensive control
- Each protocol weakness has a specific CVE category (check NVD for examples)

---
## Tools Covered in This Module

**Primary tools:** hping3 --flood --syn -p 80 target, slowloris.py, nmap --script dos (lab only)

### Syntax Reference

```bash
# Tools for Module 10: DoS & DDoS
hping3 --flood --syn -p 80 target, slowloris.py, nmap --script dos (lab only)

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

**High-frequency exam topics for Module 10:**
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

**Q1:** SYN flood exploits: A) UDP protocol B) TCP 3-way handshake half-open connections C) ICMP echo D) ARP broadcast

**Answer:** B) TCP 3-way handshake half-open connections

**Explanation:** This is a core concept tested in Module 10. Know the exact definition and be able to distinguish it from similar options.

---

**Q2:** Amplification attacks abuse services that: A) Return small responses B) Return much larger responses than the request C) Require authentication D) Use TCP

**Answer:** B) Return much larger responses than the request

**Explanation:** CEH exam frequently tests tool knowledge and scan/attack type identification. Memorize which tool does what and which flag triggers which behavior.

---

**Q3:** Slowloris is an example of: A) Volumetric DDoS B) Application-layer DoS keeping connections open C) Amplification attack D) SYN flood

**Answer:** B) Application-layer DoS keeping connections open

**Explanation:** Scenario-based questions require applying conceptual knowledge. Always eliminate obviously wrong answers first, then distinguish between the two most plausible options.

---
## Quick Reference Cheatsheet

```bash
# ── MODULE 10: DOS & DDOS ──────────────────────────────
# Topics: volumetric protocol application layer attacks, SYN flood UDP flood ICMP flood Slowloris HTTP flood, botnets C2, amplification attacks DNS NTP SSDP, DDoS mitigation CDN scrubbing rate limiting
# Tools:  hping3 --flood --syn -p 80 target, slowloris.py, nmap --script dos (lab only)

# Core commands:
# (See practical.md for days: Days 05, 26)

# Nmap for this module:
nmap -sV -sC --script default 192.168.56.102

# Save all output:
command 2>&1 | tee module10_output.txt

# Reference CVEs: Search NVD for terms in this module
# Reference TTP: Search MITRE ATT&CK for technique names
```

### Key Terms Glossary

Review all terms in: **volumetric protocol application layer attacks, SYN flood UDP flood ICMP flood Slowloris HTTP flood, botnets C2, amplification attacks DNS NTP SSDP, DDoS mitigation CDN scrubbing rate limiting**

For the CEH exam, be able to:
- Define each term in one sentence
- Give a real-world example
- Identify the correct tool or defense

---
## Mapping to Daily Course Content

| Day | Topic | Module 10 Connection |
|-----|-------|------------------------|
| Days 05 | See course calendar | Primary coverage |
| 26 | See course calendar | Extended coverage |

**Study sequence:** Read notes.md for the mapped days before reviewing this module file. The daily notes provide the detailed technical content; this module file provides the exam-focused synthesis.

---
*Module 10 of 20 | CEH v13 | Review with MASTER_NOTES.md for complete exam prep*

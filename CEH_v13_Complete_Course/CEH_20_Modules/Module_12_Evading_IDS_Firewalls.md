# CEH Module 12 — Evading IDS, Firewalls & Honeypots

## Module Overview
**Module 12: Evading IDS, Firewalls & Honeypots** is an official EC-Council CEH v13 module covering: packet fragmentation, decoy scanning, idle/zombie scan, source port manipulation, payload obfuscation, protocol tunneling DNS/ICMP, honeypot types low/high interaction Cowrie, Snort rules, evasion tools Fragroute.

**Maps to course days:** Days 13, 26

---
## Key Concepts & Definitions

This module introduces the following core concepts that are directly tested on the CEH exam:

**Primary topics:** packet fragmentation, decoy scanning, idle/zombie scan, source port manipulation, payload obfuscation, protocol tunneling DNS/ICMP, honeypot types low/high interaction Cowrie, Snort rules, evasion tools Fragroute

For each concept, understand:
- **Definition** — What it is in plain English
- **Mechanism** — How it works technically  
- **Attack use** — How attackers exploit it
- **Defense** — How defenders detect/prevent it

### Concept Deep Dive

The topics in this module (packet fragmentation, decoy scanning, idle/zombie scan, source port manipulation, payload obfuscation, protocol tunneling DNS/ICMP, honeypot types low/high interaction Cowrie, Snort rules, evasion tools Fragroute) build on each other sequentially. Review the corresponding day notes for full explanations, ASCII diagrams, and comparison tables.

**Key relationships:**
- Each tool in this module has a specific use case — know when to use each
- Each attack technique has a corresponding defensive control
- Each protocol weakness has a specific CVE category (check NVD for examples)

---
## Tools Covered in This Module

**Primary tools:** nmap -f (fragment), nmap -D RND:10 (decoy), nmap --source-port 53, fragroute

### Syntax Reference

```bash
# Tools for Module 12: Evading IDS, Firewalls & Honeypots
nmap -f (fragment), nmap -D RND:10 (decoy), nmap --source-port 53, fragroute

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

**High-frequency exam topics for Module 12:**
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

**Q1:** Idle scanning uses a zombie host because: A) Zombie has open ports B) Attacker's IP never appears in target logs C) Zombie is faster D) Zombie bypasses encryption

**Answer:** B) Attacker's IP never appears in target logs

**Explanation:** This is a core concept tested in Module 12. Know the exact definition and be able to distinguish it from similar options.

---

**Q2:** DNS tunneling is used to: A) Speed up DNS queries B) Exfiltrate data through DNS queries bypassing firewalls C) Amplify DDoS attacks D) Cache DNS records

**Answer:** B) Exfiltrate data through DNS queries bypassing firewalls

**Explanation:** CEH exam frequently tests tool knowledge and scan/attack type identification. Memorize which tool does what and which flag triggers which behavior.

---

**Q3:** A high-interaction honeypot: A) Simulates limited services B) Runs real services to capture attacker behavior C) Only logs connection attempts D) Is deployed in the cloud

**Answer:** B) Runs real services to capture attacker behavior

**Explanation:** Scenario-based questions require applying conceptual knowledge. Always eliminate obviously wrong answers first, then distinguish between the two most plausible options.

---
## Quick Reference Cheatsheet

```bash
# ── MODULE 12: EVADING IDS, FIREWALLS & HONEYPOTS ──────────────────────────────
# Topics: packet fragmentation, decoy scanning, idle/zombie scan, source port manipulation, payload obfuscation, protocol tunneling DNS/ICMP, honeypot types low/high interaction Cowrie, Snort rules, evasion tools Fragroute
# Tools:  nmap -f (fragment), nmap -D RND:10 (decoy), nmap --source-port 53, fragroute

# Core commands:
# (See practical.md for days: Days 13, 26)

# Nmap for this module:
nmap -sV -sC --script default 192.168.56.102

# Save all output:
command 2>&1 | tee module12_output.txt

# Reference CVEs: Search NVD for terms in this module
# Reference TTP: Search MITRE ATT&CK for technique names
```

### Key Terms Glossary

Review all terms in: **packet fragmentation, decoy scanning, idle/zombie scan, source port manipulation, payload obfuscation, protocol tunneling DNS/ICMP, honeypot types low/high interaction Cowrie, Snort rules, evasion tools Fragroute**

For the CEH exam, be able to:
- Define each term in one sentence
- Give a real-world example
- Identify the correct tool or defense

---
## Mapping to Daily Course Content

| Day | Topic | Module 12 Connection |
|-----|-------|------------------------|
| Days 13 | See course calendar | Primary coverage |
| 26 | See course calendar | Extended coverage |

**Study sequence:** Read notes.md for the mapped days before reviewing this module file. The daily notes provide the detailed technical content; this module file provides the exam-focused synthesis.

---
*Module 12 of 20 | CEH v13 | Review with MASTER_NOTES.md for complete exam prep*

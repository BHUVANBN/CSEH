# CEH Module 02 — Footprinting & Reconnaissance

## Module Overview
**Module 02: Footprinting & Reconnaissance** is an official EC-Council CEH v13 module covering: passive vs active recon, OSINT, whois, DNS footprinting, Shodan, Maltego, theHarvester, Netcraft, email footprinting.

**Maps to course days:** Day 09, Day 10, Day 11

---
## Key Concepts & Definitions

This module introduces the following core concepts that are directly tested on the CEH exam:

**Primary topics:** passive vs active recon, OSINT, whois, DNS footprinting, Shodan, Maltego, theHarvester, Netcraft, email footprinting

For each concept, understand:
- **Definition** — What it is in plain English
- **Mechanism** — How it works technically  
- **Attack use** — How attackers exploit it
- **Defense** — How defenders detect/prevent it

### Concept Deep Dive

The topics in this module (passive vs active recon, OSINT, whois, DNS footprinting, Shodan, Maltego, theHarvester, Netcraft, email footprinting) build on each other sequentially. Review the corresponding day notes for full explanations, ASCII diagrams, and comparison tables.

**Key relationships:**
- Each tool in this module has a specific use case — know when to use each
- Each attack technique has a corresponding defensive control
- Each protocol weakness has a specific CVE category (check NVD for examples)

---
## Tools Covered in This Module

**Primary tools:** whois domain.com, theHarvester -d domain -b google, maltego, shodan search

### Syntax Reference

```bash
# Tools for Module 02: Footprinting & Reconnaissance
whois domain.com, theHarvester -d domain -b google, maltego, shodan search

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

**High-frequency exam topics for Module 02:**
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

**Q1:** Passive footprinting differs from active because: A) It uses more tools B) It avoids direct contact with target C) It is illegal D) It requires authorization

**Answer:** B) It avoids direct contact

**Explanation:** This is a core concept tested in Module 02. Know the exact definition and be able to distinguish it from similar options.

---

**Q2:** Which tool maps domain infrastructure visually? A) Nmap B) Maltego C) Hydra D) Metasploit

**Answer:** B) Maltego

**Explanation:** CEH exam frequently tests tool knowledge and scan/attack type identification. Memorize which tool does what and which flag triggers which behavior.

---

**Q3:** DNS zone transfer is attempted using which command? A) dig any B) dig axfr C) nslookup -type=all D) whois dns

**Answer:** B) dig axfr

**Explanation:** Scenario-based questions require applying conceptual knowledge. Always eliminate obviously wrong answers first, then distinguish between the two most plausible options.

---
## Quick Reference Cheatsheet

```bash
# ── MODULE 02: FOOTPRINTING & RECONNAISSANCE ──────────────────────────────
# Topics: passive vs active recon, OSINT, whois, DNS footprinting, Shodan, Maltego, theHarvester, Netcraft, email footprinting
# Tools:  whois domain.com, theHarvester -d domain -b google, maltego, shodan search

# Core commands:
# (See practical.md for days: Day 09, Day 10, Day 11)

# Nmap for this module:
nmap -sV -sC --script default 192.168.56.102

# Save all output:
command 2>&1 | tee module02_output.txt

# Reference CVEs: Search NVD for terms in this module
# Reference TTP: Search MITRE ATT&CK for technique names
```

### Key Terms Glossary

Review all terms in: **passive vs active recon, OSINT, whois, DNS footprinting, Shodan, Maltego, theHarvester, Netcraft, email footprinting**

For the CEH exam, be able to:
- Define each term in one sentence
- Give a real-world example
- Identify the correct tool or defense

---
## Mapping to Daily Course Content

| Day | Topic | Module 02 Connection |
|-----|-------|------------------------|
| Day 09 | See course calendar | Primary coverage |
| Day 11 | See course calendar | Extended coverage |

**Study sequence:** Read notes.md for the mapped days before reviewing this module file. The daily notes provide the detailed technical content; this module file provides the exam-focused synthesis.

---
*Module 02 of 20 | CEH v13 | Review with MASTER_NOTES.md for complete exam prep*

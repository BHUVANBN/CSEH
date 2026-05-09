# CEH Module 03 — Scanning Networks

## Module Overview
**Module 03: Scanning Networks** is an official EC-Council CEH v13 module covering: nmap scan types, TCP flags, ping sweep, banner grabbing, masscan, IDS evasion fragmentation decoy idle scan, OS fingerprinting.

**Maps to course days:** Day 12, Day 13, Day 14

---
## Key Concepts & Definitions

This module introduces the following core concepts that are directly tested on the CEH exam:

**Primary topics:** nmap scan types, TCP flags, ping sweep, banner grabbing, masscan, IDS evasion fragmentation decoy idle scan, OS fingerprinting

For each concept, understand:
- **Definition** — What it is in plain English
- **Mechanism** — How it works technically  
- **Attack use** — How attackers exploit it
- **Defense** — How defenders detect/prevent it

### Concept Deep Dive

The topics in this module (nmap scan types, TCP flags, ping sweep, banner grabbing, masscan, IDS evasion fragmentation decoy idle scan, OS fingerprinting) build on each other sequentially. Review the corresponding day notes for full explanations, ASCII diagrams, and comparison tables.

**Key relationships:**
- Each tool in this module has a specific use case — know when to use each
- Each attack technique has a corresponding defensive control
- Each protocol weakness has a specific CVE category (check NVD for examples)

---
## Tools Covered in This Module

**Primary tools:** nmap -sS -sV -O, nmap -D RND:10, masscan -p1-65535 --rate 1000

### Syntax Reference

```bash
# Tools for Module 03: Scanning Networks
nmap -sS -sV -O, nmap -D RND:10, masscan -p1-65535 --rate 1000

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

**High-frequency exam topics for Module 03:**
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

**Q1:** A SYN scan (-sS) differs from a connect scan (-sT) because: A) SYN scan completes the handshake B) SYN scan is stealthier C) Connect scan uses UDP D) SYN scan requires no privileges

**Answer:** B) SYN scan is stealthier

**Explanation:** This is a core concept tested in Module 03. Know the exact definition and be able to distinguish it from similar options.

---

**Q2:** Which nmap flag performs OS detection? A) -sV B) -O C) -sC D) -A

**Answer:** B) -O

**Explanation:** CEH exam frequently tests tool knowledge and scan/attack type identification. Memorize which tool does what and which flag triggers which behavior.

---

**Q3:** Fragmented packets are used to: A) Speed up scanning B) Evade IDS/firewall detection C) Improve accuracy D) Enumerate users

**Answer:** B) Evade IDS/firewall detection

**Explanation:** Scenario-based questions require applying conceptual knowledge. Always eliminate obviously wrong answers first, then distinguish between the two most plausible options.

---
## Quick Reference Cheatsheet

```bash
# ── MODULE 03: SCANNING NETWORKS ──────────────────────────────
# Topics: nmap scan types, TCP flags, ping sweep, banner grabbing, masscan, IDS evasion fragmentation decoy idle scan, OS fingerprinting
# Tools:  nmap -sS -sV -O, nmap -D RND:10, masscan -p1-65535 --rate 1000

# Core commands:
# (See practical.md for days: Day 12, Day 13, Day 14)

# Nmap for this module:
nmap -sV -sC --script default 192.168.56.102

# Save all output:
command 2>&1 | tee module03_output.txt

# Reference CVEs: Search NVD for terms in this module
# Reference TTP: Search MITRE ATT&CK for technique names
```

### Key Terms Glossary

Review all terms in: **nmap scan types, TCP flags, ping sweep, banner grabbing, masscan, IDS evasion fragmentation decoy idle scan, OS fingerprinting**

For the CEH exam, be able to:
- Define each term in one sentence
- Give a real-world example
- Identify the correct tool or defense

---
## Mapping to Daily Course Content

| Day | Topic | Module 03 Connection |
|-----|-------|------------------------|
| Day 12 | See course calendar | Primary coverage |
| Day 14 | See course calendar | Extended coverage |

**Study sequence:** Read notes.md for the mapped days before reviewing this module file. The daily notes provide the detailed technical content; this module file provides the exam-focused synthesis.

---
*Module 03 of 20 | CEH v13 | Review with MASTER_NOTES.md for complete exam prep*

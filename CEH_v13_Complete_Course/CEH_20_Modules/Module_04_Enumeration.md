# CEH Module 04 — Enumeration

## Module Overview
**Module 04: Enumeration** is an official EC-Council CEH v13 module covering: NetBIOS 137-139, SNMP 161 community strings MIB, LDAP 389, SMB null sessions, SMTP VRFY EXPN, enum4linux, smbclient, snmpwalk, nbtscan.

**Maps to course days:** Day 15

---
## Key Concepts & Definitions

This module introduces the following core concepts that are directly tested on the CEH exam:

**Primary topics:** NetBIOS 137-139, SNMP 161 community strings MIB, LDAP 389, SMB null sessions, SMTP VRFY EXPN, enum4linux, smbclient, snmpwalk, nbtscan

For each concept, understand:
- **Definition** — What it is in plain English
- **Mechanism** — How it works technically  
- **Attack use** — How attackers exploit it
- **Defense** — How defenders detect/prevent it

### Concept Deep Dive

The topics in this module (NetBIOS 137-139, SNMP 161 community strings MIB, LDAP 389, SMB null sessions, SMTP VRFY EXPN, enum4linux, smbclient, snmpwalk, nbtscan) build on each other sequentially. Review the corresponding day notes for full explanations, ASCII diagrams, and comparison tables.

**Key relationships:**
- Each tool in this module has a specific use case — know when to use each
- Each attack technique has a corresponding defensive control
- Each protocol weakness has a specific CVE category (check NVD for examples)

---
## Tools Covered in This Module

**Primary tools:** enum4linux -a target, smbclient -L //target -N, snmpwalk -v2c -c public target, ldapsearch

### Syntax Reference

```bash
# Tools for Module 04: Enumeration
enum4linux -a target, smbclient -L //target -N, snmpwalk -v2c -c public target, ldapsearch

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

**High-frequency exam topics for Module 04:**
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

**Q1:** Default SNMP community string is: A) admin B) private C) public D) default

**Answer:** C) public

**Explanation:** This is a core concept tested in Module 04. Know the exact definition and be able to distinguish it from similar options.

---

**Q2:** SMTP user enumeration uses which command? A) HELO B) VRFY C) AUTH D) DATA

**Answer:** B) VRFY

**Explanation:** CEH exam frequently tests tool knowledge and scan/attack type identification. Memorize which tool does what and which flag triggers which behavior.

---

**Q3:** SMB null session allows: A) Password cracking B) Anonymous access to enumerate shares/users C) Remote code execution D) Packet capture

**Answer:** B) Anonymous access to enumerate shares/users

**Explanation:** Scenario-based questions require applying conceptual knowledge. Always eliminate obviously wrong answers first, then distinguish between the two most plausible options.

---
## Quick Reference Cheatsheet

```bash
# ── MODULE 04: ENUMERATION ──────────────────────────────
# Topics: NetBIOS 137-139, SNMP 161 community strings MIB, LDAP 389, SMB null sessions, SMTP VRFY EXPN, enum4linux, smbclient, snmpwalk, nbtscan
# Tools:  enum4linux -a target, smbclient -L //target -N, snmpwalk -v2c -c public target, ldapsearch

# Core commands:
# (See practical.md for days: Day 15)

# Nmap for this module:
nmap -sV -sC --script default 192.168.56.102

# Save all output:
command 2>&1 | tee module04_output.txt

# Reference CVEs: Search NVD for terms in this module
# Reference TTP: Search MITRE ATT&CK for technique names
```

### Key Terms Glossary

Review all terms in: **NetBIOS 137-139, SNMP 161 community strings MIB, LDAP 389, SMB null sessions, SMTP VRFY EXPN, enum4linux, smbclient, snmpwalk, nbtscan**

For the CEH exam, be able to:
- Define each term in one sentence
- Give a real-world example
- Identify the correct tool or defense

---
## Mapping to Daily Course Content

| Day | Topic | Module 04 Connection |
|-----|-------|------------------------|
| Day 15 | See course calendar | Primary coverage |
| Day 15 | See course calendar | Extended coverage |

**Study sequence:** Read notes.md for the mapped days before reviewing this module file. The daily notes provide the detailed technical content; this module file provides the exam-focused synthesis.

---
*Module 04 of 20 | CEH v13 | Review with MASTER_NOTES.md for complete exam prep*

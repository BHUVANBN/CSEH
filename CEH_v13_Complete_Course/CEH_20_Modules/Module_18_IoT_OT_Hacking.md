# CEH Module 18 — IoT & OT Hacking

## Module Overview
**Module 18: IoT & OT Hacking** is an official EC-Council CEH v13 module covering: IoT architecture perception network application layers, MQTT CoAP protocols, default credentials, firmware extraction analysis, Shodan IoT search, ICS SCADA OT protocols Modbus DNP3, air-gapped network attacks, Mirai botnet.

**Maps to course days:** Day 13 (Shodan context)

---
## Key Concepts & Definitions

This module introduces the following core concepts that are directly tested on the CEH exam:

**Primary topics:** IoT architecture perception network application layers, MQTT CoAP protocols, default credentials, firmware extraction analysis, Shodan IoT search, ICS SCADA OT protocols Modbus DNP3, air-gapped network attacks, Mirai botnet

For each concept, understand:
- **Definition** — What it is in plain English
- **Mechanism** — How it works technically  
- **Attack use** — How attackers exploit it
- **Defense** — How defenders detect/prevent it

### Concept Deep Dive

The topics in this module (IoT architecture perception network application layers, MQTT CoAP protocols, default credentials, firmware extraction analysis, Shodan IoT search, ICS SCADA OT protocols Modbus DNP3, air-gapped network attacks, Mirai botnet) build on each other sequentially. Review the corresponding day notes for full explanations, ASCII diagrams, and comparison tables.

**Key relationships:**
- Each tool in this module has a specific use case — know when to use each
- Each attack technique has a corresponding defensive control
- Each protocol weakness has a specific CVE category (check NVD for examples)

---
## Tools Covered in This Module

**Primary tools:** shodan search port:1883, nmap --script mqtt-subscribe, binwalk firmware.bin

### Syntax Reference

```bash
# Tools for Module 18: IoT & OT Hacking
shodan search port:1883, nmap --script mqtt-subscribe, binwalk firmware.bin

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

**High-frequency exam topics for Module 18:**
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

**Q1:** IoT devices are commonly compromised via: A) SQL injection B) Default unchanged credentials C) Buffer overflow only D) Certificate attacks

**Answer:** B) Default unchanged credentials

**Explanation:** This is a core concept tested in Module 18. Know the exact definition and be able to distinguish it from similar options.

---

**Q2:** Shodan is used to find: A) SQL vulnerabilities B) Internet-connected devices with open ports/services C) Email addresses D) Subdomains

**Answer:** B) Internet-connected devices with open ports/services

**Explanation:** CEH exam frequently tests tool knowledge and scan/attack type identification. Memorize which tool does what and which flag triggers which behavior.

---

**Q3:** SCADA systems are critical because they: A) Store user passwords B) Control physical infrastructure like power grids and water systems C) Host web applications D) Manage cloud storage

**Answer:** B) Control physical infrastructure like power grids and water systems

**Explanation:** Scenario-based questions require applying conceptual knowledge. Always eliminate obviously wrong answers first, then distinguish between the two most plausible options.

---
## Quick Reference Cheatsheet

```bash
# ── MODULE 18: IOT & OT HACKING ──────────────────────────────
# Topics: IoT architecture perception network application layers, MQTT CoAP protocols, default credentials, firmware extraction analysis, Shodan IoT search, ICS SCADA OT protocols Modbus DNP3, air-gapped network attacks, Mirai botnet
# Tools:  shodan search port:1883, nmap --script mqtt-subscribe, binwalk firmware.bin

# Core commands:
# (See practical.md for days: Day 13 (Shodan context))

# Nmap for this module:
nmap -sV -sC --script default 192.168.56.102

# Save all output:
command 2>&1 | tee module18_output.txt

# Reference CVEs: Search NVD for terms in this module
# Reference TTP: Search MITRE ATT&CK for technique names
```

### Key Terms Glossary

Review all terms in: **IoT architecture perception network application layers, MQTT CoAP protocols, default credentials, firmware extraction analysis, Shodan IoT search, ICS SCADA OT protocols Modbus DNP3, air-gapped network attacks, Mirai botnet**

For the CEH exam, be able to:
- Define each term in one sentence
- Give a real-world example
- Identify the correct tool or defense

---
## Mapping to Daily Course Content

| Day | Topic | Module 18 Connection |
|-----|-------|------------------------|
| Day 13 (Shodan context) | See course calendar | Primary coverage |
| Day 13 (Shodan context) | See course calendar | Extended coverage |

**Study sequence:** Read notes.md for the mapped days before reviewing this module file. The daily notes provide the detailed technical content; this module file provides the exam-focused synthesis.

---
*Module 18 of 20 | CEH v13 | Review with MASTER_NOTES.md for complete exam prep*

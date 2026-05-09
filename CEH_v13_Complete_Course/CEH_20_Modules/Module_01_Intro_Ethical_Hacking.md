# CEH Module 01 — Introduction to Ethical Hacking

## Module Overview
**Module 01: Introduction to Ethical Hacking** is an official EC-Council CEH v13 module covering: hacker types, 5 phases, legal frameworks, RoE, NDA, penetration testing vs red teaming.

**Maps to course days:** Day 01, Day 02

---
## Key Concepts & Definitions

This module introduces the following core concepts that are directly tested on the CEH exam:

**Primary topics:** hacker types, 5 phases, legal frameworks, RoE, NDA, penetration testing vs red teaming

For each concept, understand:
- **Definition** — What it is in plain English
- **Mechanism** — How it works technically  
- **Attack use** — How attackers exploit it
- **Defense** — How defenders detect/prevent it

### Concept Deep Dive

The topics in this module (hacker types, 5 phases, legal frameworks, RoE, NDA, penetration testing vs red teaming) build on each other sequentially. Review the corresponding day notes for full explanations, ASCII diagrams, and comparison tables.

**Key relationships:**
- Each tool in this module has a specific use case — know when to use each
- Each attack technique has a corresponding defensive control
- Each protocol weakness has a specific CVE category (check NVD for examples)

---
## Tools Covered in This Module

**Primary tools:** nmap -sn, whois

### Syntax Reference

```bash
# Tools for Module 01: Introduction to Ethical Hacking
nmap -sn, whois

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

**High-frequency exam topics for Module 01:**
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

**Q1:** What type of hacker operates without permission but without malicious intent? A) White Hat B) Grey Hat C) Black Hat D) Hacktivist

**Answer:** B) Grey Hat

**Explanation:** This is a core concept tested in Module 01. Know the exact definition and be able to distinguish it from similar options.

---

**Q2:** Which phase involves installing backdoors? A) Reconnaissance B) Scanning C) Maintaining Access D) Covering Tracks

**Answer:** C) Maintaining Access

**Explanation:** CEH exam frequently tests tool knowledge and scan/attack type identification. Memorize which tool does what and which flag triggers which behavior.

---

**Q3:** What document legally authorizes a penetration test? A) NDA B) Authorization Letter C) SoW D) RoE

**Answer:** B) Authorization Letter

**Explanation:** Scenario-based questions require applying conceptual knowledge. Always eliminate obviously wrong answers first, then distinguish between the two most plausible options.

---
## Quick Reference Cheatsheet

```bash
# ── MODULE 01: INTRODUCTION TO ETHICAL HACKING ──────────────────────────────
# Topics: hacker types, 5 phases, legal frameworks, RoE, NDA, penetration testing vs red teaming
# Tools:  nmap -sn, whois

# Core commands:
# (See practical.md for days: Day 01, Day 02)

# Nmap for this module:
nmap -sV -sC --script default 192.168.56.102

# Save all output:
command 2>&1 | tee module01_output.txt

# Reference CVEs: Search NVD for terms in this module
# Reference TTP: Search MITRE ATT&CK for technique names
```

### Key Terms Glossary

Review all terms in: **hacker types, 5 phases, legal frameworks, RoE, NDA, penetration testing vs red teaming**

For the CEH exam, be able to:
- Define each term in one sentence
- Give a real-world example
- Identify the correct tool or defense

---
## Mapping to Daily Course Content

| Day | Topic | Module 01 Connection |
|-----|-------|------------------------|
| Day 01 | See course calendar | Primary coverage |
| Day 02 | See course calendar | Extended coverage |

**Study sequence:** Read notes.md for the mapped days before reviewing this module file. The daily notes provide the detailed technical content; this module file provides the exam-focused synthesis.

---
*Module 01 of 20 | CEH v13 | Review with MASTER_NOTES.md for complete exam prep*

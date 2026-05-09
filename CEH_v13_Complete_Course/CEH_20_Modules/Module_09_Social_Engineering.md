# CEH Module 09 — Social Engineering

## Module Overview
**Module 09: Social Engineering** is an official EC-Council CEH v13 module covering: Cialdini 6 principles, phishing spear-phishing whaling vishing smishing baiting pretexting tailgating, GoPhish SET, BEC, SPF DKIM DMARC email authentication, security awareness training.

**Maps to course days:** Day 28

---
## Key Concepts & Definitions

This module introduces the following core concepts that are directly tested on the CEH exam:

**Primary topics:** Cialdini 6 principles, phishing spear-phishing whaling vishing smishing baiting pretexting tailgating, GoPhish SET, BEC, SPF DKIM DMARC email authentication, security awareness training

For each concept, understand:
- **Definition** — What it is in plain English
- **Mechanism** — How it works technically  
- **Attack use** — How attackers exploit it
- **Defense** — How defenders detect/prevent it

### Concept Deep Dive

The topics in this module (Cialdini 6 principles, phishing spear-phishing whaling vishing smishing baiting pretexting tailgating, GoPhish SET, BEC, SPF DKIM DMARC email authentication, security awareness training) build on each other sequentially. Review the corresponding day notes for full explanations, ASCII diagrams, and comparison tables.

**Key relationships:**
- Each tool in this module has a specific use case — know when to use each
- Each attack technique has a corresponding defensive control
- Each protocol weakness has a specific CVE category (check NVD for examples)

---
## Tools Covered in This Module

**Primary tools:** setoolkit, gophish, emkei.cz (spoofed email demo)

### Syntax Reference

```bash
# Tools for Module 09: Social Engineering
setoolkit, gophish, emkei.cz (spoofed email demo)

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

**High-frequency exam topics for Module 09:**
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

**Q1:** Which principle makes people comply because an authority figure requested it? A) Reciprocity B) Authority C) Scarcity D) Social proof

**Answer:** B) Authority

**Explanation:** This is a core concept tested in Module 09. Know the exact definition and be able to distinguish it from similar options.

---

**Q2:** Spear phishing differs from phishing because: A) It uses phone calls B) It is targeted at specific individuals C) It involves USB drops D) It requires physical access

**Answer:** B) It is targeted at specific individuals

**Explanation:** CEH exam frequently tests tool knowledge and scan/attack type identification. Memorize which tool does what and which flag triggers which behavior.

---

**Q3:** SPF records protect against: A) DDoS attacks B) Email spoofing by defining authorized mail servers C) SQL injection D) ARP poisoning

**Answer:** B) Email spoofing by defining authorized mail servers

**Explanation:** Scenario-based questions require applying conceptual knowledge. Always eliminate obviously wrong answers first, then distinguish between the two most plausible options.

---
## Quick Reference Cheatsheet

```bash
# ── MODULE 09: SOCIAL ENGINEERING ──────────────────────────────
# Topics: Cialdini 6 principles, phishing spear-phishing whaling vishing smishing baiting pretexting tailgating, GoPhish SET, BEC, SPF DKIM DMARC email authentication, security awareness training
# Tools:  setoolkit, gophish, emkei.cz (spoofed email demo)

# Core commands:
# (See practical.md for days: Day 28)

# Nmap for this module:
nmap -sV -sC --script default 192.168.56.102

# Save all output:
command 2>&1 | tee module09_output.txt

# Reference CVEs: Search NVD for terms in this module
# Reference TTP: Search MITRE ATT&CK for technique names
```

### Key Terms Glossary

Review all terms in: **Cialdini 6 principles, phishing spear-phishing whaling vishing smishing baiting pretexting tailgating, GoPhish SET, BEC, SPF DKIM DMARC email authentication, security awareness training**

For the CEH exam, be able to:
- Define each term in one sentence
- Give a real-world example
- Identify the correct tool or defense

---
## Mapping to Daily Course Content

| Day | Topic | Module 09 Connection |
|-----|-------|------------------------|
| Day 28 | See course calendar | Primary coverage |
| Day 28 | See course calendar | Extended coverage |

**Study sequence:** Read notes.md for the mapped days before reviewing this module file. The daily notes provide the detailed technical content; this module file provides the exam-focused synthesis.

---
*Module 09 of 20 | CEH v13 | Review with MASTER_NOTES.md for complete exam prep*

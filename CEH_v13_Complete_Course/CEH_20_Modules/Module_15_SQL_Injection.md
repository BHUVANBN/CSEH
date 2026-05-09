# CEH Module 15 — SQL Injection

## Module Overview
**Module 15: SQL Injection** is an official EC-Council CEH v13 module covering: in-band blind out-of-band SQLi, UNION-based error-based time-based blind, sqlmap automation, WAF bypass, parameterized queries stored procedures, ORM protection, database enumeration.

**Maps to course days:** Days 22, 23

---
## Key Concepts & Definitions

This module introduces the following core concepts that are directly tested on the CEH exam:

**Primary topics:** in-band blind out-of-band SQLi, UNION-based error-based time-based blind, sqlmap automation, WAF bypass, parameterized queries stored procedures, ORM protection, database enumeration

For each concept, understand:
- **Definition** — What it is in plain English
- **Mechanism** — How it works technically  
- **Attack use** — How attackers exploit it
- **Defense** — How defenders detect/prevent it

### Concept Deep Dive

The topics in this module (in-band blind out-of-band SQLi, UNION-based error-based time-based blind, sqlmap automation, WAF bypass, parameterized queries stored procedures, ORM protection, database enumeration) build on each other sequentially. Review the corresponding day notes for full explanations, ASCII diagrams, and comparison tables.

**Key relationships:**
- Each tool in this module has a specific use case — know when to use each
- Each attack technique has a corresponding defensive control
- Each protocol weakness has a specific CVE category (check NVD for examples)

---
## Tools Covered in This Module

**Primary tools:** sqlmap -u url --dbs --tables --dump, ' OR '1'='1, ' UNION SELECT 1,2,3--

### Syntax Reference

```bash
# Tools for Module 15: SQL Injection
sqlmap -u url --dbs --tables --dump, ' OR '1'='1, ' UNION SELECT 1,2,3--

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

**High-frequency exam topics for Module 15:**
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

**Q1:** Time-based blind SQL injection uses: A) UNION statements B) Error messages C) Time delays (SLEEP/WAITFOR) to infer data D) Out-of-band channels

**Answer:** C) Time delays (SLEEP/WAITFOR) to infer data

**Explanation:** This is a core concept tested in Module 15. Know the exact definition and be able to distinguish it from similar options.

---

**Q2:** Best defense against SQL injection is: A) Input length limit B) Parameterized queries / prepared statements C) Firewall rules D) HTTPS

**Answer:** B) Parameterized queries / prepared statements

**Explanation:** CEH exam frequently tests tool knowledge and scan/attack type identification. Memorize which tool does what and which flag triggers which behavior.

---

**Q3:** sqlmap flag to dump all databases is: A) --tables B) --dbs C) --dump D) --columns

**Answer:** B) --dbs

**Explanation:** Scenario-based questions require applying conceptual knowledge. Always eliminate obviously wrong answers first, then distinguish between the two most plausible options.

---
## Quick Reference Cheatsheet

```bash
# ── MODULE 15: SQL INJECTION ──────────────────────────────
# Topics: in-band blind out-of-band SQLi, UNION-based error-based time-based blind, sqlmap automation, WAF bypass, parameterized queries stored procedures, ORM protection, database enumeration
# Tools:  sqlmap -u url --dbs --tables --dump, ' OR '1'='1, ' UNION SELECT 1,2,3--

# Core commands:
# (See practical.md for days: Days 22, 23)

# Nmap for this module:
nmap -sV -sC --script default 192.168.56.102

# Save all output:
command 2>&1 | tee module15_output.txt

# Reference CVEs: Search NVD for terms in this module
# Reference TTP: Search MITRE ATT&CK for technique names
```

### Key Terms Glossary

Review all terms in: **in-band blind out-of-band SQLi, UNION-based error-based time-based blind, sqlmap automation, WAF bypass, parameterized queries stored procedures, ORM protection, database enumeration**

For the CEH exam, be able to:
- Define each term in one sentence
- Give a real-world example
- Identify the correct tool or defense

---
## Mapping to Daily Course Content

| Day | Topic | Module 15 Connection |
|-----|-------|------------------------|
| Days 22 | See course calendar | Primary coverage |
| 23 | See course calendar | Extended coverage |

**Study sequence:** Read notes.md for the mapped days before reviewing this module file. The daily notes provide the detailed technical content; this module file provides the exam-focused synthesis.

---
*Module 15 of 20 | CEH v13 | Review with MASTER_NOTES.md for complete exam prep*

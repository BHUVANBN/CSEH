# CEH Module 14 — Hacking Web Applications

## Module Overview
**Module 14: Hacking Web Applications** is an official EC-Council CEH v13 module covering: OWASP Top 10, SQLi, XSS stored reflected DOM, CSRF, IDOR, command injection, file upload bypass, directory traversal, SSRF, broken authentication, Burp Suite workflow, DVWA WebGoat.

**Maps to course days:** Days 21, 22, 23, 24

---
## Key Concepts & Definitions

This module introduces the following core concepts that are directly tested on the CEH exam:

**Primary topics:** OWASP Top 10, SQLi, XSS stored reflected DOM, CSRF, IDOR, command injection, file upload bypass, directory traversal, SSRF, broken authentication, Burp Suite workflow, DVWA WebGoat

For each concept, understand:
- **Definition** — What it is in plain English
- **Mechanism** — How it works technically  
- **Attack use** — How attackers exploit it
- **Defense** — How defenders detect/prevent it

### Concept Deep Dive

The topics in this module (OWASP Top 10, SQLi, XSS stored reflected DOM, CSRF, IDOR, command injection, file upload bypass, directory traversal, SSRF, broken authentication, Burp Suite workflow, DVWA WebGoat) build on each other sequentially. Review the corresponding day notes for full explanations, ASCII diagrams, and comparison tables.

**Key relationships:**
- Each tool in this module has a specific use case — know when to use each
- Each attack technique has a corresponding defensive control
- Each protocol weakness has a specific CVE category (check NVD for examples)

---
## Tools Covered in This Module

**Primary tools:** sqlmap -u url --dbs, burpsuite intercept, gobuster dir -u url -w wordlist

### Syntax Reference

```bash
# Tools for Module 14: Hacking Web Applications
sqlmap -u url --dbs, burpsuite intercept, gobuster dir -u url -w wordlist

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

**High-frequency exam topics for Module 14:**
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

**Q1:** IDOR vulnerability occurs when: A) SQL is injected B) Object references are not validated for authorization C) XSS payload executes D) CSRF token is missing

**Answer:** B) Object references are not validated for authorization

**Explanation:** This is a core concept tested in Module 14. Know the exact definition and be able to distinguish it from similar options.

---

**Q2:** Directory traversal uses: A) SQL quotes B) ../ sequences to access files outside web root C) Script tags D) URL encoding

**Answer:** B) ../ sequences to access files outside web root

**Explanation:** CEH exam frequently tests tool knowledge and scan/attack type identification. Memorize which tool does what and which flag triggers which behavior.

---

**Q3:** Command injection is possible when: A) Cookies are unencrypted B) User input is passed to OS commands without sanitization C) Session tokens are weak D) TLS is disabled

**Answer:** B) User input is passed to OS commands without sanitization

**Explanation:** Scenario-based questions require applying conceptual knowledge. Always eliminate obviously wrong answers first, then distinguish between the two most plausible options.

---
## Quick Reference Cheatsheet

```bash
# ── MODULE 14: HACKING WEB APPLICATIONS ──────────────────────────────
# Topics: OWASP Top 10, SQLi, XSS stored reflected DOM, CSRF, IDOR, command injection, file upload bypass, directory traversal, SSRF, broken authentication, Burp Suite workflow, DVWA WebGoat
# Tools:  sqlmap -u url --dbs, burpsuite intercept, gobuster dir -u url -w wordlist

# Core commands:
# (See practical.md for days: Days 21, 22, 23, 24)

# Nmap for this module:
nmap -sV -sC --script default 192.168.56.102

# Save all output:
command 2>&1 | tee module14_output.txt

# Reference CVEs: Search NVD for terms in this module
# Reference TTP: Search MITRE ATT&CK for technique names
```

### Key Terms Glossary

Review all terms in: **OWASP Top 10, SQLi, XSS stored reflected DOM, CSRF, IDOR, command injection, file upload bypass, directory traversal, SSRF, broken authentication, Burp Suite workflow, DVWA WebGoat**

For the CEH exam, be able to:
- Define each term in one sentence
- Give a real-world example
- Identify the correct tool or defense

---
## Mapping to Daily Course Content

| Day | Topic | Module 14 Connection |
|-----|-------|------------------------|
| Days 21 | See course calendar | Primary coverage |
| 24 | See course calendar | Extended coverage |

**Study sequence:** Read notes.md for the mapped days before reviewing this module file. The daily notes provide the detailed technical content; this module file provides the exam-focused synthesis.

---
*Module 14 of 20 | CEH v13 | Review with MASTER_NOTES.md for complete exam prep*

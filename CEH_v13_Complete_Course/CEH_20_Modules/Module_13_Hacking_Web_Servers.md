# CEH Module 13 — Hacking Web Servers

## Module Overview
**Module 13: Hacking Web Servers** is an official EC-Council CEH v13 module covering: web server architecture Apache Nginx IIS, misconfigurations directory listing default creds exposed admin panels, banner grabbing, HTTP methods PUT DELETE, web cache poisoning, DoS against web servers, tools Nikto Metasploit.

**Maps to course days:** Days 16, 21

---
## Key Concepts & Definitions

This module introduces the following core concepts that are directly tested on the CEH exam:

**Primary topics:** web server architecture Apache Nginx IIS, misconfigurations directory listing default creds exposed admin panels, banner grabbing, HTTP methods PUT DELETE, web cache poisoning, DoS against web servers, tools Nikto Metasploit

For each concept, understand:
- **Definition** — What it is in plain English
- **Mechanism** — How it works technically  
- **Attack use** — How attackers exploit it
- **Defense** — How defenders detect/prevent it

### Concept Deep Dive

The topics in this module (web server architecture Apache Nginx IIS, misconfigurations directory listing default creds exposed admin panels, banner grabbing, HTTP methods PUT DELETE, web cache poisoning, DoS against web servers, tools Nikto Metasploit) build on each other sequentially. Review the corresponding day notes for full explanations, ASCII diagrams, and comparison tables.

**Key relationships:**
- Each tool in this module has a specific use case — know when to use each
- Each attack technique has a corresponding defensive control
- Each protocol weakness has a specific CVE category (check NVD for examples)

---
## Tools Covered in This Module

**Primary tools:** nikto -h http://target, curl -v http://target, nmap --script http-enum target

### Syntax Reference

```bash
# Tools for Module 13: Hacking Web Servers
nikto -h http://target, curl -v http://target, nmap --script http-enum target

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

**High-frequency exam topics for Module 13:**
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

**Q1:** Directory listing vulnerability exposes: A) Server CPU B) All files in a directory to unauthenticated users C) Database credentials D) SSL keys

**Answer:** B) All files in a directory to unauthenticated users

**Explanation:** This is a core concept tested in Module 13. Know the exact definition and be able to distinguish it from similar options.

---

**Q2:** HTTP PUT method is dangerous when enabled because: A) It reads files B) It allows uploading arbitrary files to server C) It deletes cookies D) It redirects traffic

**Answer:** B) It allows uploading arbitrary files to server

**Explanation:** CEH exam frequently tests tool knowledge and scan/attack type identification. Memorize which tool does what and which flag triggers which behavior.

---

**Q3:** Which tool specifically audits web server vulnerabilities? A) Nmap B) Nikto C) Metasploit D) Hydra

**Answer:** B) Nikto

**Explanation:** Scenario-based questions require applying conceptual knowledge. Always eliminate obviously wrong answers first, then distinguish between the two most plausible options.

---
## Quick Reference Cheatsheet

```bash
# ── MODULE 13: HACKING WEB SERVERS ──────────────────────────────
# Topics: web server architecture Apache Nginx IIS, misconfigurations directory listing default creds exposed admin panels, banner grabbing, HTTP methods PUT DELETE, web cache poisoning, DoS against web servers, tools Nikto Metasploit
# Tools:  nikto -h http://target, curl -v http://target, nmap --script http-enum target

# Core commands:
# (See practical.md for days: Days 16, 21)

# Nmap for this module:
nmap -sV -sC --script default 192.168.56.102

# Save all output:
command 2>&1 | tee module13_output.txt

# Reference CVEs: Search NVD for terms in this module
# Reference TTP: Search MITRE ATT&CK for technique names
```

### Key Terms Glossary

Review all terms in: **web server architecture Apache Nginx IIS, misconfigurations directory listing default creds exposed admin panels, banner grabbing, HTTP methods PUT DELETE, web cache poisoning, DoS against web servers, tools Nikto Metasploit**

For the CEH exam, be able to:
- Define each term in one sentence
- Give a real-world example
- Identify the correct tool or defense

---
## Mapping to Daily Course Content

| Day | Topic | Module 13 Connection |
|-----|-------|------------------------|
| Days 16 | See course calendar | Primary coverage |
| 21 | See course calendar | Extended coverage |

**Study sequence:** Read notes.md for the mapped days before reviewing this module file. The daily notes provide the detailed technical content; this module file provides the exam-focused synthesis.

---
*Module 13 of 20 | CEH v13 | Review with MASTER_NOTES.md for complete exam prep*

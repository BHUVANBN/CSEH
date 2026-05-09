# CEH Module 17 — Hacking Mobile Platforms

## Module Overview
**Module 17: Hacking Mobile Platforms** is an official EC-Council CEH v13 module covering: Android architecture APK reverse engineering, iOS jailbreaking, mobile malware, OWASP Mobile Top 10, insecure data storage, certificate pinning bypass, ADB exploitation, Frida dynamic instrumentation, MDM solutions.

**Maps to course days:** Day 31 (career context)

---
## Key Concepts & Definitions

This module introduces the following core concepts that are directly tested on the CEH exam:

**Primary topics:** Android architecture APK reverse engineering, iOS jailbreaking, mobile malware, OWASP Mobile Top 10, insecure data storage, certificate pinning bypass, ADB exploitation, Frida dynamic instrumentation, MDM solutions

For each concept, understand:
- **Definition** — What it is in plain English
- **Mechanism** — How it works technically  
- **Attack use** — How attackers exploit it
- **Defense** — How defenders detect/prevent it

### Concept Deep Dive

The topics in this module (Android architecture APK reverse engineering, iOS jailbreaking, mobile malware, OWASP Mobile Top 10, insecure data storage, certificate pinning bypass, ADB exploitation, Frida dynamic instrumentation, MDM solutions) build on each other sequentially. Review the corresponding day notes for full explanations, ASCII diagrams, and comparison tables.

**Key relationships:**
- Each tool in this module has a specific use case — know when to use each
- Each attack technique has a corresponding defensive control
- Each protocol weakness has a specific CVE category (check NVD for examples)

---
## Tools Covered in This Module

**Primary tools:** adb shell, apktool d app.apk, frida, drozer

### Syntax Reference

```bash
# Tools for Module 17: Hacking Mobile Platforms
adb shell, apktool d app.apk, frida, drozer

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

**High-frequency exam topics for Module 17:**
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

**Q1:** Android application reverse engineering uses: A) Wireshark B) apktool to decompile APK C) Nmap D) Metasploit

**Answer:** B) apktool to decompile APK

**Explanation:** This is a core concept tested in Module 17. Know the exact definition and be able to distinguish it from similar options.

---

**Q2:** OWASP Mobile Top 10 M1 is: A) Insecure authentication B) Improper Platform Usage C) Insecure Data Storage D) Client Code Quality

**Answer:** B) Improper Platform Usage

**Explanation:** CEH exam frequently tests tool knowledge and scan/attack type identification. Memorize which tool does what and which flag triggers which behavior.

---

**Q3:** Certificate pinning prevents: A) SQL injection B) MitM attacks against mobile apps by validating server certificate C) Brute force D) Buffer overflow

**Answer:** B) MitM attacks against mobile apps by validating server certificate

**Explanation:** Scenario-based questions require applying conceptual knowledge. Always eliminate obviously wrong answers first, then distinguish between the two most plausible options.

---
## Quick Reference Cheatsheet

```bash
# ── MODULE 17: HACKING MOBILE PLATFORMS ──────────────────────────────
# Topics: Android architecture APK reverse engineering, iOS jailbreaking, mobile malware, OWASP Mobile Top 10, insecure data storage, certificate pinning bypass, ADB exploitation, Frida dynamic instrumentation, MDM solutions
# Tools:  adb shell, apktool d app.apk, frida, drozer

# Core commands:
# (See practical.md for days: Day 31 (career context))

# Nmap for this module:
nmap -sV -sC --script default 192.168.56.102

# Save all output:
command 2>&1 | tee module17_output.txt

# Reference CVEs: Search NVD for terms in this module
# Reference TTP: Search MITRE ATT&CK for technique names
```

### Key Terms Glossary

Review all terms in: **Android architecture APK reverse engineering, iOS jailbreaking, mobile malware, OWASP Mobile Top 10, insecure data storage, certificate pinning bypass, ADB exploitation, Frida dynamic instrumentation, MDM solutions**

For the CEH exam, be able to:
- Define each term in one sentence
- Give a real-world example
- Identify the correct tool or defense

---
## Mapping to Daily Course Content

| Day | Topic | Module 17 Connection |
|-----|-------|------------------------|
| Day 31 (career context) | See course calendar | Primary coverage |
| Day 31 (career context) | See course calendar | Extended coverage |

**Study sequence:** Read notes.md for the mapped days before reviewing this module file. The daily notes provide the detailed technical content; this module file provides the exam-focused synthesis.

---
*Module 17 of 20 | CEH v13 | Review with MASTER_NOTES.md for complete exam prep*

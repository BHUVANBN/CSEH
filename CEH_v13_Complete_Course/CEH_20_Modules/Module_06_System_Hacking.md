# CEH Module 06 — System Hacking

## Module Overview
**Module 06: System Hacking** is an official EC-Council CEH v13 module covering: password attacks online offline, NTLM LM hash, SAM database, privilege escalation, keyloggers, steganography, covering tracks, Hydra John Hashcat Mimikatz.

**Maps to course days:** Day 17, Day 20

---
## Key Concepts & Definitions

This module introduces the following core concepts that are directly tested on the CEH exam:

**Primary topics:** password attacks online offline, NTLM LM hash, SAM database, privilege escalation, keyloggers, steganography, covering tracks, Hydra John Hashcat Mimikatz

For each concept, understand:
- **Definition** — What it is in plain English
- **Mechanism** — How it works technically  
- **Attack use** — How attackers exploit it
- **Defense** — How defenders detect/prevent it

### Concept Deep Dive

The topics in this module (password attacks online offline, NTLM LM hash, SAM database, privilege escalation, keyloggers, steganography, covering tracks, Hydra John Hashcat Mimikatz) build on each other sequentially. Review the corresponding day notes for full explanations, ASCII diagrams, and comparison tables.

**Key relationships:**
- Each tool in this module has a specific use case — know when to use each
- Each attack technique has a corresponding defensive control
- Each protocol weakness has a specific CVE category (check NVD for examples)

---
## Tools Covered in This Module

**Primary tools:** hydra -l admin -P rockyou.txt target ssh, john hash.txt --wordlist=rockyou.txt, hashcat -m 1000 ntlm.txt rockyou.txt

### Syntax Reference

```bash
# Tools for Module 06: System Hacking
hydra -l admin -P rockyou.txt target ssh, john hash.txt --wordlist=rockyou.txt, hashcat -m 1000 ntlm.txt rockyou.txt

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

**High-frequency exam topics for Module 06:**
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

**Q1:** Which file stores Windows password hashes? A) /etc/shadow B) C:\Windows\SAM C) /etc/passwd D) registry.dat

**Answer:** B) C:\Windows\SAM

**Explanation:** This is a core concept tested in Module 06. Know the exact definition and be able to distinguish it from similar options.

---

**Q2:** LM hashes are weaker than NTLM because: A) They are longer B) They split password into 7-char chunks and use DES C) They use MD5 D) They require salting

**Answer:** B) They split password into 7-char chunks and use DES

**Explanation:** CEH exam frequently tests tool knowledge and scan/attack type identification. Memorize which tool does what and which flag triggers which behavior.

---

**Q3:** Pass-the-hash attacks work because: A) Passwords are stored in plaintext B) NTLM authentication accepts hash instead of password C) Kerberos tickets are reusable D) SAM files are unencrypted

**Answer:** B) NTLM authentication accepts hash instead of password

**Explanation:** Scenario-based questions require applying conceptual knowledge. Always eliminate obviously wrong answers first, then distinguish between the two most plausible options.

---
## Quick Reference Cheatsheet

```bash
# ── MODULE 06: SYSTEM HACKING ──────────────────────────────
# Topics: password attacks online offline, NTLM LM hash, SAM database, privilege escalation, keyloggers, steganography, covering tracks, Hydra John Hashcat Mimikatz
# Tools:  hydra -l admin -P rockyou.txt target ssh, john hash.txt --wordlist=rockyou.txt, hashcat -m 1000 ntlm.txt rockyou.txt

# Core commands:
# (See practical.md for days: Day 17, Day 20)

# Nmap for this module:
nmap -sV -sC --script default 192.168.56.102

# Save all output:
command 2>&1 | tee module06_output.txt

# Reference CVEs: Search NVD for terms in this module
# Reference TTP: Search MITRE ATT&CK for technique names
```

### Key Terms Glossary

Review all terms in: **password attacks online offline, NTLM LM hash, SAM database, privilege escalation, keyloggers, steganography, covering tracks, Hydra John Hashcat Mimikatz**

For the CEH exam, be able to:
- Define each term in one sentence
- Give a real-world example
- Identify the correct tool or defense

---
## Mapping to Daily Course Content

| Day | Topic | Module 06 Connection |
|-----|-------|------------------------|
| Day 17 | See course calendar | Primary coverage |
| Day 20 | See course calendar | Extended coverage |

**Study sequence:** Read notes.md for the mapped days before reviewing this module file. The daily notes provide the detailed technical content; this module file provides the exam-focused synthesis.

---
*Module 06 of 20 | CEH v13 | Review with MASTER_NOTES.md for complete exam prep*

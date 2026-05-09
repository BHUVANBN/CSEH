# CEH Module 20 — Cryptography

## Module Overview
**Module 20: Cryptography** is an official EC-Council CEH v13 module covering: symmetric AES DES 3DES modes ECB CBC GCM, asymmetric RSA ECC key exchange DH, hashing MD5 SHA-256 SHA-3 bcrypt HMAC, PKI CA X.509 CRL OCSP, TLS versions cipher suites, GPG PGP, cryptanalysis rainbow table birthday meet-in-middle.

**Maps to course days:** Day 29

---
## Key Concepts & Definitions

This module introduces the following core concepts that are directly tested on the CEH exam:

**Primary topics:** symmetric AES DES 3DES modes ECB CBC GCM, asymmetric RSA ECC key exchange DH, hashing MD5 SHA-256 SHA-3 bcrypt HMAC, PKI CA X.509 CRL OCSP, TLS versions cipher suites, GPG PGP, cryptanalysis rainbow table birthday meet-in-middle

For each concept, understand:
- **Definition** — What it is in plain English
- **Mechanism** — How it works technically  
- **Attack use** — How attackers exploit it
- **Defense** — How defenders detect/prevent it

### Concept Deep Dive

The topics in this module (symmetric AES DES 3DES modes ECB CBC GCM, asymmetric RSA ECC key exchange DH, hashing MD5 SHA-256 SHA-3 bcrypt HMAC, PKI CA X.509 CRL OCSP, TLS versions cipher suites, GPG PGP, cryptanalysis rainbow table birthday meet-in-middle) build on each other sequentially. Review the corresponding day notes for full explanations, ASCII diagrams, and comparison tables.

**Key relationships:**
- Each tool in this module has a specific use case — know when to use each
- Each attack technique has a corresponding defensive control
- Each protocol weakness has a specific CVE category (check NVD for examples)

---
## Tools Covered in This Module

**Primary tools:** openssl genrsa -out key.pem 2048, openssl enc -aes-256-cbc -in file -out enc, gpg --encrypt, hashcat -m 0 hash wordlist

### Syntax Reference

```bash
# Tools for Module 20: Cryptography
openssl genrsa -out key.pem 2048, openssl enc -aes-256-cbc -in file -out enc, gpg --encrypt, hashcat -m 0 hash wordlist

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

**High-frequency exam topics for Module 20:**
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

**Q1:** AES is a: A) Asymmetric cipher B) Hashing algorithm C) Symmetric block cipher D) Stream cipher

**Answer:** C) Symmetric block cipher

**Explanation:** This is a core concept tested in Module 20. Know the exact definition and be able to distinguish it from similar options.

---

**Q2:** Digital signatures provide: A) Confidentiality only B) Integrity and non-repudiation C) Availability D) Speed

**Answer:** B) Integrity and non-repudiation

**Explanation:** CEH exam frequently tests tool knowledge and scan/attack type identification. Memorize which tool does what and which flag triggers which behavior.

---

**Q3:** Rainbow tables are defeated by: A) Longer passwords B) Salting hashes before storage C) Using MD5 D) Increasing key length

**Answer:** B) Salting hashes before storage

**Explanation:** Scenario-based questions require applying conceptual knowledge. Always eliminate obviously wrong answers first, then distinguish between the two most plausible options.

---
## Quick Reference Cheatsheet

```bash
# ── MODULE 20: CRYPTOGRAPHY ──────────────────────────────
# Topics: symmetric AES DES 3DES modes ECB CBC GCM, asymmetric RSA ECC key exchange DH, hashing MD5 SHA-256 SHA-3 bcrypt HMAC, PKI CA X.509 CRL OCSP, TLS versions cipher suites, GPG PGP, cryptanalysis rainbow table birthday meet-in-middle
# Tools:  openssl genrsa -out key.pem 2048, openssl enc -aes-256-cbc -in file -out enc, gpg --encrypt, hashcat -m 0 hash wordlist

# Core commands:
# (See practical.md for days: Day 29)

# Nmap for this module:
nmap -sV -sC --script default 192.168.56.102

# Save all output:
command 2>&1 | tee module20_output.txt

# Reference CVEs: Search NVD for terms in this module
# Reference TTP: Search MITRE ATT&CK for technique names
```

### Key Terms Glossary

Review all terms in: **symmetric AES DES 3DES modes ECB CBC GCM, asymmetric RSA ECC key exchange DH, hashing MD5 SHA-256 SHA-3 bcrypt HMAC, PKI CA X.509 CRL OCSP, TLS versions cipher suites, GPG PGP, cryptanalysis rainbow table birthday meet-in-middle**

For the CEH exam, be able to:
- Define each term in one sentence
- Give a real-world example
- Identify the correct tool or defense

---
## Mapping to Daily Course Content

| Day | Topic | Module 20 Connection |
|-----|-------|------------------------|
| Day 29 | See course calendar | Primary coverage |
| Day 29 | See course calendar | Extended coverage |

**Study sequence:** Read notes.md for the mapped days before reviewing this module file. The daily notes provide the detailed technical content; this module file provides the exam-focused synthesis.

---
*Module 20 of 20 | CEH v13 | Review with MASTER_NOTES.md for complete exam prep*

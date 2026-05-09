# CEH Module 19 — Cloud Computing Security

## Module Overview
**Module 19: Cloud Computing Security** is an official EC-Council CEH v13 module covering: IaaS PaaS SaaS shared responsibility, S3 bucket misconfiguration, IAM privilege escalation, metadata service SSRF IMDSv1, container escape Docker Kubernetes, serverless security, CloudTrail GuardDuty, ScoutSuite Prowler Pacu.

**Maps to course days:** Day 27

---
## Key Concepts & Definitions

This module introduces the following core concepts that are directly tested on the CEH exam:

**Primary topics:** IaaS PaaS SaaS shared responsibility, S3 bucket misconfiguration, IAM privilege escalation, metadata service SSRF IMDSv1, container escape Docker Kubernetes, serverless security, CloudTrail GuardDuty, ScoutSuite Prowler Pacu

For each concept, understand:
- **Definition** — What it is in plain English
- **Mechanism** — How it works technically  
- **Attack use** — How attackers exploit it
- **Defense** — How defenders detect/prevent it

### Concept Deep Dive

The topics in this module (IaaS PaaS SaaS shared responsibility, S3 bucket misconfiguration, IAM privilege escalation, metadata service SSRF IMDSv1, container escape Docker Kubernetes, serverless security, CloudTrail GuardDuty, ScoutSuite Prowler Pacu) build on each other sequentially. Review the corresponding day notes for full explanations, ASCII diagrams, and comparison tables.

**Key relationships:**
- Each tool in this module has a specific use case — know when to use each
- Each attack technique has a corresponding defensive control
- Each protocol weakness has a specific CVE category (check NVD for examples)

---
## Tools Covered in This Module

**Primary tools:** aws s3 ls, aws iam list-users, scout aws, prowler -g group1

### Syntax Reference

```bash
# Tools for Module 19: Cloud Computing Security
aws s3 ls, aws iam list-users, scout aws, prowler -g group1

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

**High-frequency exam topics for Module 19:**
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

**Q1:** In the shared responsibility model for IaaS, the customer is responsible for: A) Physical hardware B) Hypervisor C) OS and applications D) Network cabling

**Answer:** C) OS and applications

**Explanation:** This is a core concept tested in Module 19. Know the exact definition and be able to distinguish it from similar options.

---

**Q2:** IMDSv1 SSRF vulnerability allows: A) S3 bucket access B) Attacker to steal AWS credentials via metadata endpoint C) Database access D) Container escape

**Answer:** B) Attacker to steal AWS credentials via metadata endpoint

**Explanation:** CEH exam frequently tests tool knowledge and scan/attack type identification. Memorize which tool does what and which flag triggers which behavior.

---

**Q3:** Which tool audits AWS security configuration? A) Nmap B) ScoutSuite C) Hydra D) Wireshark

**Answer:** B) ScoutSuite

**Explanation:** Scenario-based questions require applying conceptual knowledge. Always eliminate obviously wrong answers first, then distinguish between the two most plausible options.

---
## Quick Reference Cheatsheet

```bash
# ── MODULE 19: CLOUD COMPUTING SECURITY ──────────────────────────────
# Topics: IaaS PaaS SaaS shared responsibility, S3 bucket misconfiguration, IAM privilege escalation, metadata service SSRF IMDSv1, container escape Docker Kubernetes, serverless security, CloudTrail GuardDuty, ScoutSuite Prowler Pacu
# Tools:  aws s3 ls, aws iam list-users, scout aws, prowler -g group1

# Core commands:
# (See practical.md for days: Day 27)

# Nmap for this module:
nmap -sV -sC --script default 192.168.56.102

# Save all output:
command 2>&1 | tee module19_output.txt

# Reference CVEs: Search NVD for terms in this module
# Reference TTP: Search MITRE ATT&CK for technique names
```

### Key Terms Glossary

Review all terms in: **IaaS PaaS SaaS shared responsibility, S3 bucket misconfiguration, IAM privilege escalation, metadata service SSRF IMDSv1, container escape Docker Kubernetes, serverless security, CloudTrail GuardDuty, ScoutSuite Prowler Pacu**

For the CEH exam, be able to:
- Define each term in one sentence
- Give a real-world example
- Identify the correct tool or defense

---
## Mapping to Daily Course Content

| Day | Topic | Module 19 Connection |
|-----|-------|------------------------|
| Day 27 | See course calendar | Primary coverage |
| Day 27 | See course calendar | Extended coverage |

**Study sequence:** Read notes.md for the mapped days before reviewing this module file. The daily notes provide the detailed technical content; this module file provides the exam-focused synthesis.

---
*Module 19 of 20 | CEH v13 | Review with MASTER_NOTES.md for complete exam prep*

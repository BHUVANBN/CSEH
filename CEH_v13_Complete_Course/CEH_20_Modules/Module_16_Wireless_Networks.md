# CEH Module 16 — Hacking Wireless Networks

## Module Overview
**Module 16: Hacking Wireless Networks** is an official EC-Council CEH v13 module covering: WEP RC4 weakness, WPA TKIP, WPA2 CCMP AES, WPA3 SAE, 4-way handshake capture, WPS PIN Pixie Dust, evil twin rogue AP, aircrack-ng suite airmon-ng airodump-ng aireplay-ng, Bluetooth attacks.

**Maps to course days:** Day 25

---
## Key Concepts & Definitions

This module introduces the following core concepts that are directly tested on the CEH exam:

**Primary topics:** WEP RC4 weakness, WPA TKIP, WPA2 CCMP AES, WPA3 SAE, 4-way handshake capture, WPS PIN Pixie Dust, evil twin rogue AP, aircrack-ng suite airmon-ng airodump-ng aireplay-ng, Bluetooth attacks

For each concept, understand:
- **Definition** — What it is in plain English
- **Mechanism** — How it works technically  
- **Attack use** — How attackers exploit it
- **Defense** — How defenders detect/prevent it

### Concept Deep Dive

The topics in this module (WEP RC4 weakness, WPA TKIP, WPA2 CCMP AES, WPA3 SAE, 4-way handshake capture, WPS PIN Pixie Dust, evil twin rogue AP, aircrack-ng suite airmon-ng airodump-ng aireplay-ng, Bluetooth attacks) build on each other sequentially. Review the corresponding day notes for full explanations, ASCII diagrams, and comparison tables.

**Key relationships:**
- Each tool in this module has a specific use case — know when to use each
- Each attack technique has a corresponding defensive control
- Each protocol weakness has a specific CVE category (check NVD for examples)

---
## Tools Covered in This Module

**Primary tools:** airmon-ng start wlan0, airodump-ng wlan0mon, aireplay-ng --deauth 10 -a BSSID, aircrack-ng -w rockyou.txt cap.cap

### Syntax Reference

```bash
# Tools for Module 16: Hacking Wireless Networks
airmon-ng start wlan0, airodump-ng wlan0mon, aireplay-ng --deauth 10 -a BSSID, aircrack-ng -w rockyou.txt cap.cap

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

**High-frequency exam topics for Module 16:**
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

**Q1:** WEP is considered broken because: A) It uses WPA B) RC4 key scheduling flaw allows key recovery from IVs C) It uses AES D) It requires WPS

**Answer:** B) RC4 key scheduling flaw allows key recovery from IVs

**Explanation:** This is a core concept tested in Module 16. Know the exact definition and be able to distinguish it from similar options.

---

**Q2:** The 4-way handshake in WPA2 establishes: A) The SSID B) Session keys from the PMK C) The channel D) MAC filtering

**Answer:** B) Session keys from the PMK

**Explanation:** CEH exam frequently tests tool knowledge and scan/attack type identification. Memorize which tool does what and which flag triggers which behavior.

---

**Q3:** WPS PIN attack is effective because: A) WPS uses DES B) PIN is checked in two halves reducing brute force space C) WPS has no timeout D) PIN is 6 digits

**Answer:** B) PIN is checked in two halves reducing brute force space

**Explanation:** Scenario-based questions require applying conceptual knowledge. Always eliminate obviously wrong answers first, then distinguish between the two most plausible options.

---
## Quick Reference Cheatsheet

```bash
# ── MODULE 16: HACKING WIRELESS NETWORKS ──────────────────────────────
# Topics: WEP RC4 weakness, WPA TKIP, WPA2 CCMP AES, WPA3 SAE, 4-way handshake capture, WPS PIN Pixie Dust, evil twin rogue AP, aircrack-ng suite airmon-ng airodump-ng aireplay-ng, Bluetooth attacks
# Tools:  airmon-ng start wlan0, airodump-ng wlan0mon, aireplay-ng --deauth 10 -a BSSID, aircrack-ng -w rockyou.txt cap.cap

# Core commands:
# (See practical.md for days: Day 25)

# Nmap for this module:
nmap -sV -sC --script default 192.168.56.102

# Save all output:
command 2>&1 | tee module16_output.txt

# Reference CVEs: Search NVD for terms in this module
# Reference TTP: Search MITRE ATT&CK for technique names
```

### Key Terms Glossary

Review all terms in: **WEP RC4 weakness, WPA TKIP, WPA2 CCMP AES, WPA3 SAE, 4-way handshake capture, WPS PIN Pixie Dust, evil twin rogue AP, aircrack-ng suite airmon-ng airodump-ng aireplay-ng, Bluetooth attacks**

For the CEH exam, be able to:
- Define each term in one sentence
- Give a real-world example
- Identify the correct tool or defense

---
## Mapping to Daily Course Content

| Day | Topic | Module 16 Connection |
|-----|-------|------------------------|
| Day 25 | See course calendar | Primary coverage |
| Day 25 | See course calendar | Extended coverage |

**Study sequence:** Read notes.md for the mapped days before reviewing this module file. The daily notes provide the detailed technical content; this module file provides the exam-focused synthesis.

---
*Module 16 of 20 | CEH v13 | Review with MASTER_NOTES.md for complete exam prep*

# CEH v13 Complete Course — Study Folder System

> **Legal Disclaimer:** All techniques, tools, and methodologies documented in this course are strictly for **authorized, educational, and ethical purposes only**. Never perform any hacking activity on systems you do not own or have explicit written permission to test. Unauthorized access to computer systems is illegal and punishable by law under statutes such as the Computer Fraud and Abuse Act (CFAA), IT Act 2000, GDPR, and equivalent legislation worldwide. The authors and contributors of this material accept no liability for misuse.

---

## Table of Contents

1. [About This Course](#about-this-course)
2. [Folder Structure](#folder-structure)
3. [How to Use This Study System](#how-to-use-this-study-system)
4. [Tools Required & Installation](#tools-required--installation)
5. [32-Day Study Schedule](#32-day-study-schedule)
6. [Progress Tracker](#progress-tracker)
7. [External Resources](#external-resources)

---

## About This Course

This is a **self-contained, CEH v13-aligned** ethical hacking study system designed to take you from zero to exam-ready in 32 days. It mirrors the official EC-Council Certified Ethical Hacker v13 syllabus and covers all 20 CEH modules in a practical, lab-first approach.

**Who this is for:**
- Students pursuing the CEH v13 certification
- IT professionals transitioning into cybersecurity
- Security enthusiasts wanting structured, practical learning
- Red team trainees needing a systematic knowledge base

**What you get:**
- 32 days of structured content (notes, practicals, assignments)
- 20 CEH module reference files
- A master revision guide (`MASTER_NOTES.md`)
- Lab-based practical exercises with real commands
- Assignment challenges + self-assessment tools

---

## Folder Structure

```
CEH_v13_Complete_Course/
├── README.md                          ← You are here
├── MASTER_NOTES.md                    ← Complete revision guide
│
├── Month_1_Foundations/               ← Days 1–16
│   ├── Week_1_Fundamentals/           ← Days 1–4
│   │   ├── Day_01_Introduction/
│   │   │   ├── notes.md              ← Theory (600+ words)
│   │   │   ├── practical.md          ← Hands-on steps (400+ words)
│   │   │   └── assignment.md         ← Tasks & self-check (300+ words)
│   │   ├── Day_02_Cyber_Laws/
│   │   ├── Day_03_CIA_Triad/
│   │   └── Day_04_Kali_Linux/
│   ├── Week_2_Networking/             ← Days 5–8
│   │   ├── Day_05_OSI_TCPIP/
│   │   ├── Day_06_IP_Protocols/
│   │   ├── Day_07_Linux_Fundamentals/
│   │   └── Day_08_Windows_Fundamentals/
│   ├── Week_3_Reconnaissance/         ← Days 9–12
│   │   ├── Day_09_Footprinting/
│   │   ├── Day_10_OSINT_GoogleDorks/
│   │   ├── Day_11_DNS_WHOIS/
│   │   └── Day_12_Nmap_Reconng/
│   └── Week_4_Scanning/               ← Days 13–16
│       ├── Day_13_Network_Scanning/
│       ├── Day_14_Nmap_Deep_Dive/
│       ├── Day_15_Enumeration/
│       └── Day_16_Vulnerability_Scanning/
│
├── Month_2_Exploitation/              ← Days 17–32
│   ├── Week_5_System_Hacking/         ← Days 17–20
│   │   ├── Day_17_Password_Attacks/
│   │   ├── Day_18_Malware/
│   │   ├── Day_19_Sniffing_MITM/
│   │   └── Day_20_Covering_Tracks/
│   ├── Week_6_Web_Hacking/            ← Days 21–24
│   │   ├── Day_21_Web_Architecture/
│   │   ├── Day_22_OWASP_Top10/
│   │   ├── Day_23_Burp_Suite/
│   │   └── Day_24_Web_Project/
│   ├── Week_7_Network_Cloud_Wireless/ ← Days 25–28
│   │   ├── Day_25_Wireless_Security/
│   │   ├── Day_26_Firewall_IDS_IPS/
│   │   ├── Day_27_Cloud_Security/
│   │   └── Day_28_Social_Engineering/
│   └── Week_8_Advanced_Capstone/      ← Days 29–32
│       ├── Day_29_Cryptography/
│       ├── Day_30_Forensics_Incident_Response/
│       ├── Day_31_Career_Roadmap/
│       └── Day_32_Capstone_Project/
│
└── CEH_20_Modules/                    ← Official CEH module reference
    ├── Module_01_Intro_Ethical_Hacking.md
    ├── Module_02_Footprinting.md
    ... (20 modules total)
    └── Module_20_Cryptography.md
```

---

## How to Use This Study System

### Daily Workflow (Recommended)

Follow this order **every single day**:

```
Step 1 → Open notes.md       Read fully. Take handwritten notes alongside.
Step 2 → Open practical.md   Execute every command in your Kali Linux lab.
Step 3 → Open assignment.md  Complete all sections before moving to Day N+1.
Step 4 → Update your tracker Mark your progress checkbox below.
```

### Weekly Review

At the end of each week:
- Re-read all 4 `notes.md` files for the week
- Revisit any practical you couldn't complete
- Cross-reference with the corresponding `CEH_20_Modules/` file

### Final Exam Prep

In the final week before your exam:
- Read `MASTER_NOTES.md` cover to cover
- Use the glossary section (100+ terms)
- Use the command reference cheatsheet
- Complete the CEH exam prep checklist at the end of MASTER_NOTES.md

---

## Tools Required & Installation

### Core Platform

| Tool | Purpose | Install |
|------|---------|---------|
| Kali Linux | Primary attack platform | Download ISO from kali.org |
| VirtualBox | Virtualization | `sudo apt install virtualbox` |
| Metasploitable2 | Vulnerable target VM | Download from SourceForge |
| DVWA | Web vulnerability lab | `docker run -d -p 80:80 vulnerables/web-dvwa` |

### Network & Recon Tools

```bash
sudo apt update && sudo apt install -y \
  nmap masscan netcat-openbsd wireshark tcpdump \
  whois dnsutils dnsrecon dnsenum fierce \
  recon-ng theharvester maltego \
  nbtscan enum4linux smbclient ldap-utils \
  snmp snmp-mibs-downloader
```

### Web Testing Tools

```bash
sudo apt install -y \
  burpsuite nikto dirb gobuster \
  sqlmap whatweb wapiti \
  curl wget
```

### Exploitation & Post-Exploitation

```bash
sudo apt install -y \
  metasploit-framework \
  hydra medusa john hashcat \
  aircrack-ng bettercap ettercap-text-only \
  steghide exiftool
```

### Forensics & Defense

```bash
sudo apt install -y \
  autopsy sleuthkit \
  volatility3 \
  auditd ufw iptables-persistent \
  cowrie
```

### Wordlists

```bash
sudo apt install -y seclists wordlists
# RockYou wordlist (already on Kali):
sudo gunzip /usr/share/wordlists/rockyou.txt.gz
```

### Python/Pip Tools

```bash
pip install scoutsuite truffleHog
```

---

## 32-Day Study Schedule

| Week | Days | Focus Area | Topics |
|------|------|-----------|--------|
| Week 1 | 1–4 | Fundamentals | Hacker types, laws, CIA triad, Kali setup |
| Week 2 | 5–8 | Networking | OSI/TCP-IP, IP addressing, Linux, Windows |
| Week 3 | 9–12 | Reconnaissance | Footprinting, OSINT, DNS, Nmap basics |
| Week 4 | 13–16 | Scanning | Network scanning, Nmap NSE, Enumeration, Vuln scanning |
| Week 5 | 17–20 | System Hacking | Passwords, Malware, Sniffing, Covering tracks |
| Week 6 | 21–24 | Web Hacking | Web architecture, OWASP Top 10, Burp Suite, Project |
| Week 7 | 25–28 | Advanced Topics | Wireless, Firewalls/IDS, Cloud security, Social engineering |
| Week 8 | 29–32 | Capstone | Cryptography, Forensics, Career, Full pentest project |

### Calendar View

```
MONTH 1 — FOUNDATIONS
┌───────────────────────────────────────────────┐
│  Mon    Tue    Wed    Thu    Fri   Sat   Sun   │
│  Day1   Day2   Day3   Day4   --    --    --    │ Week 1
│  Day5   Day6   Day7   Day8   --    --    --    │ Week 2
│  Day9   Day10  Day11  Day12  --    --    --    │ Week 3
│  Day13  Day14  Day15  Day16  --    --    --    │ Week 4
└───────────────────────────────────────────────┘

MONTH 2 — EXPLOITATION & ADVANCED
┌───────────────────────────────────────────────┐
│  Mon    Tue    Wed    Thu    Fri   Sat   Sun   │
│  Day17  Day18  Day19  Day20  --    --    --    │ Week 5
│  Day21  Day22  Day23  Day24  --    --    --    │ Week 6
│  Day25  Day26  Day27  Day28  --    --    --    │ Week 7
│  Day29  Day30  Day31  Day32  --    --    --    │ Week 8
└───────────────────────────────────────────────┘
```

> **Note:** Weekends are buffer days. Use them for review, catching up on incomplete practicals, or extra CTF challenges.

---

## Progress Tracker

Mark each checkbox as you complete the day's full content (notes + practical + assignment).

### Month 1: Foundations

#### Week 1 — Fundamentals
- [ ] Day 01 — Introduction to Ethical Hacking
- [ ] Day 02 — Cyber Laws & Ethics
- [ ] Day 03 — CIA Triad & Core Security Concepts
- [ ] Day 04 — Kali Linux Setup & Navigation

#### Week 2 — Networking
- [ ] Day 05 — OSI Model & TCP/IP Stack
- [ ] Day 06 — IP Addressing, Ports & Protocols
- [ ] Day 07 — Linux Fundamentals
- [ ] Day 08 — Windows Fundamentals

#### Week 3 — Reconnaissance
- [ ] Day 09 — Footprinting Methodology
- [ ] Day 10 — OSINT & Google Dorks
- [ ] Day 11 — DNS, WHOIS & Email Footprinting
- [ ] Day 12 — Nmap & Recon-ng

#### Week 4 — Scanning
- [ ] Day 13 — Network Scanning Concepts
- [ ] Day 14 — Nmap Deep Dive (NSE)
- [ ] Day 15 — Enumeration Techniques
- [ ] Day 16 — Vulnerability Scanning

### Month 2: Exploitation & Advanced

#### Week 5 — System Hacking
- [ ] Day 17 — Password Attacks
- [ ] Day 18 — Malware Analysis
- [ ] Day 19 — Sniffing & MITM Attacks
- [ ] Day 20 — Covering Tracks

#### Week 6 — Web Hacking
- [ ] Day 21 — Web Application Architecture
- [ ] Day 22 — OWASP Top 10
- [ ] Day 23 — Burp Suite Mastery
- [ ] Day 24 — Web Application Security Project

#### Week 7 — Network, Cloud & Wireless
- [ ] Day 25 — Wireless Security
- [ ] Day 26 — Firewall, IDS & IPS
- [ ] Day 27 — Cloud Security
- [ ] Day 28 — Social Engineering

#### Week 8 — Advanced & Capstone
- [ ] Day 29 — Cryptography
- [ ] Day 30 — Incident Response & Digital Forensics
- [ ] Day 31 — Career Roadmap & Portfolio
- [ ] Day 32 — Capstone Project (Full Pentest Report)

### CEH 20 Modules Review
- [ ] Module 01 — Introduction to Ethical Hacking
- [ ] Module 02 — Footprinting & Reconnaissance
- [ ] Module 03 — Scanning Networks
- [ ] Module 04 — Enumeration
- [ ] Module 05 — Vulnerability Analysis
- [ ] Module 06 — System Hacking
- [ ] Module 07 — Malware Threats
- [ ] Module 08 — Sniffing
- [ ] Module 09 — Social Engineering
- [ ] Module 10 — Denial-of-Service
- [ ] Module 11 — Session Hijacking
- [ ] Module 12 — Evading IDS, Firewalls & Honeypots
- [ ] Module 13 — Hacking Web Servers
- [ ] Module 14 — Hacking Web Applications
- [ ] Module 15 — SQL Injection
- [ ] Module 16 — Hacking Wireless Networks
- [ ] Module 17 — Hacking Mobile Platforms
- [ ] Module 18 — IoT & OT Hacking
- [ ] Module 19 — Cloud Computing
- [ ] Module 20 — Cryptography

---

## External Resources

### Practice Platforms

| Platform | URL | Best For |
|----------|-----|---------|
| TryHackMe | https://tryhackme.com | Beginners, guided paths |
| HackTheBox | https://hackthebox.eu | Intermediate/advanced machines |
| PortSwigger Web Academy | https://portswigger.net/web-security | Web hacking mastery |
| VulnHub | https://vulnhub.com | Downloadable vulnerable VMs |
| PicoCTF | https://picoctf.org | CTF fundamentals |
| CTFtime | https://ctftime.org | Ongoing CTF competitions |
| CyberDefenders | https://cyberdefenders.org | Blue team & forensics |

### Tools & References

| Resource | URL | Purpose |
|----------|-----|---------|
| Exploit-DB | https://exploit-db.com | Exploits & PoCs |
| CVE Details | https://cvedetails.com | CVE lookup |
| NVD | https://nvd.nist.gov | CVSS scores |
| MITRE ATT&CK | https://attack.mitre.org | TTP framework |
| OWASP | https://owasp.org | Web security standards |
| Shodan | https://shodan.io | Internet-wide scanning |
| HackerOne | https://hackerone.com | Bug bounty programs |
| Bugcrowd | https://bugcrowd.com | Bug bounty programs |

### Official CEH Resources

| Resource | URL |
|----------|-----|
| EC-Council CEH | https://www.eccouncil.org/train-certify/certified-ethical-hacker-ceh/ |
| CEH Exam Blueprint | https://www.eccouncil.org/wp-content/uploads/2022/09/CEH-Exam-Blueprint-v13.pdf |
| iLabs (EC-Council) | https://ilabs.eccouncil.org |

---

*Last updated: 2026 | CEH v13 aligned | Use responsibly.*

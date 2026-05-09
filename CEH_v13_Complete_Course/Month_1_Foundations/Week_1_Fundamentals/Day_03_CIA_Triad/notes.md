# Day 03 — The CIA Triad & Core Security Concepts

## [TOPIC OVERVIEW]

The **CIA Triad** — Confidentiality, Integrity, and Availability — is the foundational model of information security. Every security control, every policy, every incident response action ultimately traces back to protecting one or more of these three properties. The CIA Triad is not just an academic model; it is the lens through which every security professional evaluates risk and designs defenses.

Understanding the CIA Triad is mandatory for the CEH exam, but more importantly, it gives you the language to articulate *why* a vulnerability matters. A SQL injection vulnerability is dangerous not because it uses apostrophes — it is dangerous because it can destroy **Confidentiality** (data theft), **Integrity** (data modification), and **Availability** (database crash). When you frame threats through the CIA lens, you can communicate risk to executives, engineers, and lawyers alike.

**Real-world relevance:** Every major breach in history can be analyzed as a CIA triad failure. The 2013 Target breach violated Confidentiality (40M credit card numbers stolen). The 2016 Bangladesh Bank heist violated Integrity (fraudulent SWIFT transactions). The 2016 Dyn DNS DDoS attack violated Availability (took down Twitter, Netflix, GitHub).

**CEH v13 connection:** CIA Triad concepts appear in Module 01 and are referenced throughout every subsequent module. Exam questions about threats, vulnerabilities, and attack classification all require CIA Triad understanding.

---

## [KEY CONCEPTS]

### Confidentiality

**Plain English:** Only the right people can see the information.
**Technical:** Ensuring information is accessible only to authorized entities through access controls, encryption, and authentication mechanisms.

**Mechanisms that protect Confidentiality:**
- **Encryption:** AES-256 for data at rest; TLS 1.3 for data in transit
- **Access Control Lists (ACLs):** Who can read, write, execute a resource
- **Multi-Factor Authentication (MFA):** Prevents unauthorized access even if passwords are stolen
- **Data Classification:** Labeling data by sensitivity (Public, Internal, Confidential, Top Secret)
- **Need-to-Know Principle:** Employees only access data required for their job function

**Attacks against Confidentiality:**
- Eavesdropping / sniffing network traffic
- Phishing to steal credentials
- SQL injection to dump databases
- Insider threats leaking data
- Broken access controls (OWASP A01)

---

### Integrity

**Plain English:** The information hasn't been tampered with — it's accurate and trustworthy.
**Technical:** Ensuring data is complete, accurate, and unaltered by unauthorized parties throughout its lifecycle.

**Mechanisms that protect Integrity:**
- **Hashing:** MD5, SHA-256, SHA-3 — create a fingerprint of data; any change produces a different hash
- **Digital Signatures:** Cryptographic proof that data came from a specific source and wasn't altered
- **Message Authentication Codes (HMAC):** Verifies both integrity and authenticity
- **Version Control:** Tracks changes and allows rollback (Git, SVN)
- **File Integrity Monitoring (FIM):** Tools like Tripwire alert when critical files change

**Hash comparison demonstration:**
```
Original file hash:  sha256sum config.txt → a3f4b2c1d...
Modified file hash:  sha256sum config.txt → 9e1c3a7f2...  ← DIFFERENT = tampered
```

**Attacks against Integrity:**
- Man-in-the-Middle (MITM) attacks modifying data in transit
- SQL injection modifying database records
- Malware altering system files
- DNS cache poisoning (redirecting to wrong IP)
- Ransomware encrypting and destroying data

---

### Availability

**Plain English:** The system or data is accessible when authorized users need it.
**Technical:** Ensuring authorized users have reliable, timely access to resources.

**Mechanisms that protect Availability:**
- **Redundancy:** Multiple servers, power supplies, network links
- **Load Balancing:** Distributes traffic to prevent single-point overload
- **Backups:** Regular, tested backups to restore after failure
- **DDoS Protection:** Rate limiting, scrubbing centers, CDN-based mitigation (Cloudflare)
- **Disaster Recovery Planning (DRP) / Business Continuity Planning (BCP)**
- **Uptime SLAs:** Defined service level agreements (99.9% = ~8.7 hours downtime/year)

**Attacks against Availability:**
- Distributed Denial of Service (DDoS) — flood the target with traffic
- Ransomware encrypting files and denying access
- Physical destruction of hardware
- Resource exhaustion attacks (SYN flood, Slowloris)
- Software bugs causing crashes

---

### The CIA Triad Table

| Property | Threat Example | Tool/Attack | Defense |
|----------|---------------|------------|---------|
| Confidentiality | Data breach | SQL injection, sniffing | Encryption, ACL |
| Integrity | Data modification | MITM, malware | Hashing, digital signatures |
| Availability | System outage | DDoS, ransomware | Redundancy, backups |

---

### Extended Triad: Adding Authentication & Non-Repudiation

Some frameworks extend CIA to **CIAAN** or use the **Parkerian Hexad**:
- **Authentication:** Verifying identity (who are you?)
- **Non-Repudiation:** Cannot deny having performed an action (digital signatures provide this)
- **Possession/Control:** Ensuring only authorized parties control the data
- **Utility:** Data must be in a usable form

---

### Threat vs. Vulnerability vs. Risk vs. Exploit

These four terms are constantly confused and frequently tested on the CEH exam:

| Term | Definition | Example |
|------|-----------|---------|
| **Vulnerability** | A weakness in a system, process, or control | Unpatched Apache server (CVE-2021-41773) |
| **Threat** | A potential cause of harm — anything that can exploit a vulnerability | Attacker who knows about that CVE |
| **Risk** | Probability × Impact = likelihood and consequence of exploitation | High probability of attack × High impact = CRITICAL risk |
| **Exploit** | The actual code or technique used to take advantage of a vulnerability | Metasploit module `exploit/multi/handler` |
| **Attack Vector** | The path through which an exploit reaches the vulnerability | Network, email attachment, USB drive |
| **Attack Surface** | Total exposure of a system — all points where attackers can interact | Open ports + web endpoints + employee email |

**Mnemonic:** "VTR+E = Vulnerability creates the hole, Threat is who falls through, Risk is how likely and how bad, Exploit is what they use."

---

### CVE, CWE, and CVSS Explained

**CVE — Common Vulnerabilities and Exposures:**
- A unique identifier for a publicly known vulnerability
- Format: `CVE-YEAR-NUMBER` (e.g., CVE-2021-44228 = Log4Shell)
- Maintained by MITRE, published in NVD (National Vulnerability Database)
- Every CVE has: description, affected products, references, severity score

**CWE — Common Weakness Enumeration:**
- Categories of software weaknesses that *lead to* CVEs
- Format: `CWE-NUMBER` (e.g., CWE-89 = SQL Injection weakness class)
- A single CWE can have thousands of CVEs associated with it
- CVE describes a specific flaw; CWE describes the class of flaw

**CVSS — Common Vulnerability Scoring System:**
- Standardized 0–10 scoring system for vulnerability severity
- **Base Score** factors: Attack Vector, Attack Complexity, Privileges Required, User Interaction, Scope, CIA Impact
- Score ranges: 0=None, 0.1-3.9=Low, 4.0-6.9=Medium, 7.0-8.9=High, 9.0-10.0=Critical
- **Temporal Score:** Adjusts for exploit maturity and patch availability
- **Environmental Score:** Adjusts for your specific organization's context

**Example:** Log4Shell (CVE-2021-44228)
- CVSS Base Score: **10.0 CRITICAL**
- Attack Vector: Network | Complexity: Low | No Auth Required | Full CIA Impact

---

### Zero-Day Definition

A **zero-day vulnerability** is a flaw that:
1. Is unknown to the software vendor
2. Has no patch available
3. May or may not be publicly known

"Zero-day" refers to the fact that developers have had zero days to fix it. Zero-days are extremely valuable — governments and cybercriminal groups pay millions for reliable ones. The Stuxnet worm used **four** zero-days simultaneously, which was unprecedented.

**Zero-day → N-day:** Once the vendor releases a patch, the vulnerability becomes an "N-day" (where N = number of days since the patch). Organizations that don't patch immediately remain vulnerable to N-day exploits.

---

### Threat Modeling Basics

**Threat modeling** is a structured approach to identifying security threats during system design — before building, not after being breached.

Popular frameworks:
- **STRIDE** (Microsoft): Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, Elevation of Privilege
- **PASTA:** Process for Attack Simulation and Threat Analysis
- **DREAD:** Damage, Reproducibility, Exploitability, Affected Users, Discoverability

---

## [CEH EXAM FOCUS]

1. **"Which pillar of CIA..."** questions — given a breach, identify which CIA property was violated
2. **CVE vs CWE vs CVSS** — know the distinction clearly; common distractor question
3. **Zero-day vs N-day** — zero-day = no patch; N-day = patch exists but not applied
4. **Risk formula** — Risk = Threat × Vulnerability × Asset Value
5. **STRIDE categories** — know what each letter represents

### Tricky Areas
- Ransomware attacks **all three** CIA properties: Confidentiality (if data is exfiltrated before encryption), Integrity (files are encrypted/modified), Availability (system locked)
- **Non-repudiation** is NOT part of the classic CIA Triad — it's an extension
- A vulnerability with CVSS 10.0 is not automatically the highest priority to fix — environmental score matters more for prioritization

---

## [REAL-WORLD CONTEXT]

### Case Study: The Colonial Pipeline Ransomware Attack (2021)

**What happened:** DarkSide ransomware group compromised Colonial Pipeline's IT systems using a compromised VPN password (found in a leaked credential database). They encrypted 100GB of data and demanded $4.4 million in Bitcoin. Colonial Pipeline shut down operations affecting fuel supply to the US East Coast.

**CIA Analysis:**
- **Confidentiality violated:** 100GB of data was exfiltrated before encryption
- **Integrity violated:** Files were encrypted — original data integrity was destroyed
- **Availability violated:** Pipeline operations shut down for 6 days

**How CIA knowledge helps:** A proper security posture addressing all three pillars would have included: MFA on VPN (Confidentiality), file integrity monitoring (Integrity), and operational backup systems (Availability). The single compromised password — with no MFA — was the entire chain of failure.

---

**Key Takeaway:** The CIA Triad is not a box to check — it is a thinking framework. Every time you assess a vulnerability, ask: "Which pillar does this threaten? How severely? What controls would protect it?" This three-question habit will serve you throughout your entire security career.

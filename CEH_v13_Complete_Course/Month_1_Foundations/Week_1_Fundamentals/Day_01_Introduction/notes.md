# Day 01 — Introduction to Ethical Hacking

## [TOPIC OVERVIEW]

### What Is Ethical Hacking?

**Ethical hacking** — also known as penetration testing or white-hat hacking — is the practice of intentionally probing a system, network, or application for security vulnerabilities using the same tools, techniques, and mindset as malicious hackers, but with explicit legal authorization from the system owner.

The fundamental distinction from criminal hacking is **permission**. Without a signed authorization document, even the most well-intentioned security test is illegal in most jurisdictions. This course begins with this principle because it defines everything that follows.

**Why it matters in cybersecurity:** Organizations face thousands of attacks daily. A single successful breach can cost millions in damages, legal penalties, and reputational harm. Ethical hackers are the defenders who think like attackers — finding holes before the criminals do. The global cybersecurity talent gap exceeds 3.4 million professionals (ISC² 2023), making this one of the highest-demand skill sets in the tech industry.

**Real-world relevance:** Every major tech company — Google, Microsoft, Facebook, Apple — runs bug bounty programs and employs red teams precisely because internal developers cannot be expected to find their own security flaws objectively. Ethical hackers have disclosed vulnerabilities in critical infrastructure, healthcare systems, and financial institutions that could have caused catastrophic harm if found by adversaries first.

**CEH v13 connection:** The CEH exam begins with Module 01 — Introduction to Ethical Hacking. Approximately 6% of exam questions come from this domain, covering terminology, phases, and legal/ethical frameworks.

---

## [KEY CONCEPTS]

### Hacker Types (EC-Council Classification)

Understanding who hackers are is the foundation of the CEH curriculum. EC-Council classifies them by intent and authorization:

| Hacker Type | Description | Legal Status |
|-------------|-------------|-------------|
| **White Hat** | Ethical hacker with written authorization. Finds vulnerabilities to help organizations improve security. | Legal |
| **Black Hat** | Malicious hacker acting without authorization. Motivated by financial gain, destruction, or espionage. | Illegal |
| **Grey Hat** | Operates without authorization but typically does not have destructive intent. May disclose vulnerabilities without permission. | Legally ambiguous |
| **Script Kiddie** | Unskilled attacker who uses pre-built tools and scripts without understanding how they work. | Illegal when unauthorized |
| **Hacktivist** | Uses hacking as a form of political or social protest. Anonymous is the most famous example. | Usually illegal |
| **State-Sponsored Hacker** | Government-backed attacker targeting foreign governments, critical infrastructure, or corporations for intelligence or disruption. | Illegal internationally; legally grey domestically |
| **Insider Threat** | A current or former employee, contractor, or business partner who intentionally or accidentally causes harm. | Varies; often criminal |
| **Cyber Terrorist** | Uses hacking to cause widespread fear, disruption, or physical harm aligned with ideological goals. | Illegal and treated as terrorism |

> **Exam Tip:** CEH exam commonly asks you to distinguish between white/grey/black hat and identify the correct category for a scenario. Know each definition precisely.

---

### The 5 Phases of Ethical Hacking

Every professional pentest — and every criminal attack — follows a logical sequence. The CEH defines these as five phases:

```
Phase 1: RECONNAISSANCE (Footprinting)
    ↓  Gather information about the target passively and actively
Phase 2: SCANNING
    ↓  Probe the target to discover open ports, services, and vulnerabilities
Phase 3: GAINING ACCESS (Exploitation)
    ↓  Exploit found vulnerabilities to compromise the system
Phase 4: MAINTAINING ACCESS (Post-Exploitation)
    ↓  Install backdoors, escalate privileges, pivot to other systems
Phase 5: CLEARING TRACKS (Anti-Forensics)
       Remove evidence of the compromise (logs, artifacts)
```

**Phase 1 — Reconnaissance:** The attacker gathers as much information as possible about the target before touching it. This includes public records, DNS data, WHOIS, social media, job postings, and more. Divided into passive (no direct contact) and active (direct contact) recon.

**Phase 2 — Scanning:** The attacker uses tools like Nmap to discover live hosts, open ports, running services, and operating systems. This phase begins direct interaction with the target.

**Phase 3 — Gaining Access:** Exploitation occurs here. The attacker leverages known vulnerabilities, misconfigured services, or weak credentials to gain a foothold. Tools like Metasploit automate this process.

**Phase 4 — Maintaining Access:** Once inside, the attacker installs persistent backdoors (rootkits, reverse shells, scheduled tasks) to ensure continued access even if the initial entry point is closed.

**Phase 5 — Clearing Tracks:** The attacker erases evidence — deleting log files, altering timestamps, removing temporary files. This is why digital forensics is so critical to incident response.

---

### Legal vs. Illegal Hacking

The line between legal and illegal hacking is **written authorization**. The key documents in an ethical hacking engagement are:

- **Non-Disclosure Agreement (NDA):** Protects the client's sensitive information discovered during testing.
- **Rules of Engagement (RoE):** Defines what systems are in scope, what attack types are permitted, testing hours, escalation procedures, and emergency contacts.
- **Authorization Letter / Statement of Work (SoW):** The actual legal document granting permission to test. Without this, even internal "authorized" tests have grey areas.
- **Master Service Agreement (MSA):** Overarching contract between the pentest firm and the client.

**Penetration Testing vs. Ethical Hacking vs. Red Teaming:**

| Term | Definition |
|------|-----------|
| **Penetration Testing** | Structured, time-boxed engagement to find and exploit vulnerabilities in a defined scope. |
| **Ethical Hacking** | Broader term — encompasses pentesting but also includes ongoing security assessments, code review, and advisory roles. |
| **Red Teaming** | Adversary simulation — mimics a real threat actor over an extended period, tests people/process/technology holistically, often without the blue team knowing. |
| **Vulnerability Assessment** | Identifies and ranks vulnerabilities without attempting exploitation. Less invasive than pentesting. |

---

### CEH v13 Overview

The **Certified Ethical Hacker v13** is EC-Council's flagship penetration testing certification. It covers 20 modules spanning all major attack surfaces and is designed to validate hands-on knowledge of offensive security techniques.

- **Exam format:** 125 multiple-choice questions, 4 hours
- **Passing score:** Approximately 70% (varies by form)
- **Validity:** 3 years (renewable via ECE credits)
- **Prerequisites:** 2 years of work experience in IT security OR official EC-Council training

**CEH v13 New Additions (vs v12):**
- AI-powered attack techniques
- Enhanced cloud security module
- OT/SCADA systems coverage
- Updated IoT attack techniques
- AI-driven threat analysis tools

---

## [CEH EXAM FOCUS]

### Common Exam Question Areas for Day 1 Topics

1. **"What type of hacker..." scenario questions** — Given a description of attacker behavior, identify the correct classification (white/black/grey hat, script kiddie, hacktivist, state-sponsored)

2. **Phase identification questions** — "An attacker installs a rootkit to maintain access. Which phase is this?" (Answer: Maintaining Access)

3. **Legal distinction questions** — "What document must an ethical hacker obtain before testing?" (Answer: Authorization letter / written permission)

4. **Penetration testing vs. red teaming** — Know the distinctions clearly

5. **Difference between vulnerability assessment and penetration testing** — VA finds vulnerabilities; pentesting exploits them

### Tricky Areas & Misconceptions

- **Grey hat ≠ good.** Grey hats operate without permission, making their actions illegal even if their intent is not malicious. EC-Council still classifies unauthorized access as illegal regardless of intent.
- **Ethical hacking requires more than good intentions** — it requires documentation, authorization, and defined scope.
- **"Clearing tracks" is done by ethical hackers too** — but only to demonstrate attacker capability, not to hide from the client. The ethical hacker documents everything and provides a full report.

### Key Terms EC-Council Expects You to Know

- **Hacker, Cracker** — EC-Council uses "hacker" for all types and "cracker" for those who break software protections
- **Tiger Team** — A team of ethical hackers hired to test an organization
- **Vulnerability** — A weakness that can be exploited
- **Threat** — A potential cause of harm
- **Risk** — Probability × Impact of a threat exploiting a vulnerability
- **Exploit** — Code or technique that takes advantage of a vulnerability
- **Zero-day** — A vulnerability with no patch available yet

---

## [REAL-WORLD CONTEXT]

### Case Study: The SolarWinds Supply Chain Attack (2020)

**What happened:** State-sponsored hackers (attributed to Russia's SVR, known as Cozy Bear/APT29) compromised SolarWinds' software build pipeline and inserted malicious code into the Orion IT monitoring software. Approximately 18,000 organizations installed the trojanized update, including U.S. government agencies (Treasury, Commerce, Homeland Security) and major corporations.

**Attack phases visible in this breach:**
- **Reconnaissance:** Attackers spent months learning SolarWinds' development environment
- **Gaining Access:** Compromised the build server to inject the SUNBURST backdoor
- **Maintaining Access:** The backdoor lay dormant for 2 weeks after installation before activating, evading behavioral analysis
- **Clearing Tracks:** The malware was meticulously designed to blend with legitimate SolarWinds traffic

**What knowledge would have helped:**
- Regular code integrity checks (CI/CD pipeline security)
- Supply chain security audits
- Behavioral anomaly detection (the backdoor eventually triggered Mandiant's security monitoring)
- Understanding of insider-level access threats

**Key lesson:** Even with excellent perimeter security, attackers find novel entry vectors. An ethical hacker's job is to think exactly this creatively — before the adversary does.

---

**Key Takeaway:** Ethical hacking is not about the tools — it's about the mindset of thinking like an attacker while operating with the integrity of a professional. Everything in this course builds on the foundation established today: know who you are, what you're allowed to do, and why it matters.

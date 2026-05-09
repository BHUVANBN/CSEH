# Day 02 — Cyber Laws & Ethics

## [TOPIC OVERVIEW]

### What Are Cyber Laws and Why Do They Matter?

**Cyber law** encompasses the legal frameworks that govern the use of computers, networks, and the internet. For ethical hackers, understanding cyber law is not optional — it is the boundary between professional practice and criminal liability. The moment you access a system without explicit authorization, you cross a legal line that exists in virtually every jurisdiction on Earth.

This day's focus is critically important because the CEH exam explicitly tests knowledge of laws, legal frameworks, and ethical standards. More importantly, in real professional practice, ignorance of the law is never a defense. A penetration tester who exceeds their authorized scope has committed a crime, regardless of their intent.

**Why it matters:** In 2021, a security researcher was arrested for accessing a computer system without authorization — even though he claimed he was trying to help the organization. The law does not recognize good intentions without documented permission. This is why the legal and ethical framework is taught before any technical skills.

**Real-world relevance:** Ethical hacking engagements are governed by contracts, laws, and professional codes of conduct. Understanding these protects you, your client, and the integrity of your findings. Lawyers are not your enemy — they are your protection.

**CEH v13 connection:** Module 01 covers legal frameworks and ethics. Approximately 3–5% of CEH questions involve legal knowledge, authorization requirements, and ethical boundaries.

---

## [KEY CONCEPTS]

### Key Cyber Laws

#### Computer Fraud and Abuse Act (CFAA) — United States

The **Computer Fraud and Abuse Act (CFAA)**, 18 U.S.C. § 1030, is the primary U.S. federal law governing computer crime. Enacted in 1986 and amended multiple times, it criminalizes:

- Unauthorized access to any computer
- Accessing a computer to obtain information with intent to defraud
- Transmitting malicious code (malware)
- Threatening to damage computers (extortion)
- Trafficking in passwords

**Key penalty:** Up to 10 years imprisonment for first offense; up to 20 years for repeat offenses.

**Relevance for ethical hackers:** The CFAA's definition of "unauthorized access" is broad. Even if a client gives verbal permission, if there is no written authorization document, an ethical hacker could theoretically be prosecuted. Always get written consent.

**Famous CFAA case:** Aaron Swartz, a programming prodigy, was charged under CFAA for downloading academic articles in bulk from JSTOR using MIT's network — articles he had legal access to. He faced up to 35 years in prison. This case highlighted how broadly the CFAA can be applied.

---

#### IT Act 2000 — India

India's **Information Technology Act 2000** (amended 2008) is the primary legislation governing cyber activities:

- **Section 43:** Unauthorized access to computer systems — civil penalty up to ₹1 crore
- **Section 66:** Computer-related offenses (hacking) — up to 3 years imprisonment and/or ₹5 lakh fine
- **Section 66B:** Receiving stolen computer resources — up to 3 years imprisonment
- **Section 66C:** Identity theft — up to 3 years imprisonment
- **Section 66E:** Violation of privacy — up to 3 years imprisonment
- **Section 67:** Publishing obscene content — up to 5 years imprisonment
- **Section 69:** Government power to intercept/monitor/decrypt information

**Key point for CEH:** The IT Act 2000 aligns with the CFAA's principle — accessing any computer system without authorization is a criminal offense.

---

#### General Data Protection Regulation (GDPR) — European Union

**GDPR** (Regulation EU 2016/679) governs the collection, processing, and storage of personal data of EU residents. Relevant to ethical hackers because:

- During a pentest, you may encounter personal data — you must handle it lawfully
- Organizations in scope of GDPR must conduct regular security assessments
- Data breaches must be reported within 72 hours — this drives demand for proactive security testing

**GDPR Key Principles:**
- Lawfulness, fairness, and transparency
- Purpose limitation
- Data minimization
- Accuracy
- Storage limitation
- Integrity and confidentiality (Article 5(1)(f)) — direct cybersecurity mandate

**Penalties:** Up to €20 million or 4% of global annual turnover, whichever is higher.

---

### Rules of Engagement (RoE)

A **Rules of Engagement document** is the operational contract that defines exactly how a penetration test will be conducted. It protects both the ethical hacker and the client. Every professional engagement must have one.

**RoE must include:**

| Section | Contents |
|---------|---------|
| **Scope** | Specific IP ranges, domains, applications in scope. Explicitly lists what is OUT of scope. |
| **Testing Period** | Start date, end date, approved testing hours (e.g., only between 9 PM–6 AM to avoid business disruption) |
| **Permitted Attack Types** | Social engineering allowed? DoS testing? Physical access? |
| **Communication Channels** | Who to contact in case of emergency. How findings are reported. |
| **Escalation Procedure** | What happens if a critical vulnerability is found that is being actively exploited? |
| **Third-Party Systems** | Handling of cloud providers, CDN services, partner systems that are out of scope |
| **Data Handling** | How client data discovered during testing is stored, protected, and destroyed after the engagement |
| **Legal Authorization Statement** | Signed statement from an authorized executive confirming permission to test |

---

### Authorization Letter

The **Authorization Letter** (also called a "Get Out of Jail Free Letter") is a signed document — ideally on company letterhead — that:

- Identifies the organization granting permission
- Identifies the individual or firm authorized to perform testing
- Specifies the exact systems, IP ranges, and services in scope
- States the testing period
- Is signed by an executive with authority (CISO, CTO, or equivalent)
- Includes emergency contact information

> **Critical:** Carry a copy of the authorization letter during any on-site engagement. If law enforcement is called, this is your first line of defense.

---

### Non-Disclosure Agreement (NDA)

An **NDA** protects both parties:

- **For the client:** The tester cannot disclose findings, vulnerabilities, or proprietary information discovered during the engagement
- **For the tester:** The client cannot claim the tester maliciously damaged systems if the NDA documents the scope of authorized activities

NDAs are typically **mutual** in penetration testing — both parties agree to keep engagement details confidential.

---

### Bug Bounty Programs

A **bug bounty program** is a structured, publicly or privately announced program where organizations invite researchers to find and responsibly disclose vulnerabilities in exchange for monetary rewards.

**Key differences from a standard pentest:**
- Bug bounty is ongoing; pentest is time-boxed
- Bug bounty scope is defined by the program; pentest scope is negotiated
- Bug bounty payment is per-vulnerability; pentest is fixed-fee
- Bug bounty hunters have no prior relationship with the company; pentesters do

**Major platforms:** HackerOne, Bugcrowd, Intigriti, Synack

**Safe harbor clauses:** Most bug bounty programs include safe harbor language that explicitly protects researchers from legal action if they follow the program's rules. Always read the scope before testing.

---

### Code of Ethics — EC-Council

The EC-Council requires all CEH candidates to sign a Code of Ethics agreeing to:

1. Keep client information confidential
2. Never access systems without permission
3. Never misuse knowledge for unauthorized activities
4. Protect intellectual property
5. Report all findings honestly
6. Respect privacy of individuals

Violation of the Code of Ethics can result in revocation of the CEH certification.

---

## [CEH EXAM FOCUS]

### Common Exam Question Areas

1. **CFAA provisions** — "Which law criminalizes unauthorized access to computers in the US?" (CFAA)
2. **Scope questions** — "An ethical hacker discovers a vulnerability outside the agreed scope. What should they do?" (Report it to the client, do not exploit it)
3. **RoE document purpose** — Must know all elements of an RoE
4. **Bug bounty vs pentest** — Distinguishing characteristics
5. **GDPR article identification** — Article 5 (principles), Article 32 (security), Article 33 (breach notification)

### Tricky Areas

- **"Grey area" authorization:** An IT manager says "go ahead" verbally — this is NOT valid authorization. You need signed written permission from an executive with authority.
- **Out-of-scope discovery:** Finding a critical vuln outside scope does NOT give you permission to exploit it. Document and report to the client.
- **Cloud environments:** Testing AWS/Azure/GCP resources requires permission from both the client AND the cloud provider (AWS has its own penetration testing policy, for example).

### Key Terms

- **Authorization** — Written, signed permission to conduct security testing
- **Scope of engagement** — The defined boundaries of a pentest
- **Safe harbor** — Legal protection for researchers who follow disclosure rules
- **Responsible disclosure** — Reporting vulnerabilities to the vendor privately before public disclosure
- **Coordinated vulnerability disclosure (CVD)** — Structured process for reporting vulnerabilities

---

## [REAL-WORLD CONTEXT]

### Case Study: The AT&T Hacker (2012)

Andrew Auernheimer ("weev") discovered that AT&T's iPad customer management website exposed 114,000 customer email addresses through a simple enumeration attack — he just changed the ID number in the URL. He argued he was exposing a public security flaw. He was convicted under the CFAA and sentenced to 41 months in prison (later overturned on jurisdictional grounds, not on the merits of the CFAA charge).

**What went wrong:** He accessed data without authorization. Even though the vulnerability was trivially obvious and he didn't "hack" in the traditional sense, the CFAA doesn't require sophisticated intrusion — any unauthorized access is a crime.

**What would have made this legal:** A bug bounty program, a responsible disclosure agreement, or a prior authorization letter. The knowledge was the same; the legal protection was absent.

---

**Key Takeaway:** The law is the first tool in an ethical hacker's toolkit. Before you touch a single system, ensure you have documented, signed authorization. Every other skill in this course is meaningless — and potentially criminal — without it.

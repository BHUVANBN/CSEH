# Day 02 — Assignment: Cyber Laws & Ethics

> **Difficulty:** Beginner
> **Estimated Time:** 1.5–2 hours
> **Prerequisites:** Complete notes.md and practical.md for Day 02

---

## [THEORY QUESTIONS]

**Q1.** Describe three specific actions that would be illegal under the Computer Fraud and Abuse Act (CFAA). For each action, explain why it falls under the CFAA even if the person claimed they had "good intentions."

*Your answer:*

---

**Q2.** An IT admin at a company verbally tells a security consultant "you can test our systems." Is this sufficient authorization? What is missing, and what risks does the consultant face if they proceed?

*Your answer:*

---

**Q3.** What is a bug bounty program? How does it differ from a standard penetration testing engagement in terms of scope, payment, and legal authorization?

*Your answer:*

---

**Q4.** Explain GDPR Article 5's principle of "integrity and confidentiality" (Article 5(1)(f)). How does this create demand for ethical hackers?

*Your answer:*

---

**Q5.** A penetration tester discovers a vulnerability outside the agreed scope that appears to be actively exploited by an attacker (they can see live attack traffic in logs). What should they do, step by step?

*Your answer:*

---

## [PRACTICAL TASK]

### Task: Write a Mock RoE for "SecureBank Ltd."

**Objective:** Using the template from practical.md as a foundation, create a complete, professional Rules of Engagement document for the following scenario:

**Scenario:**
> SecureBank Ltd. has hired you to perform a **network penetration test** (not web — network-layer) of their data center. The scope includes three servers in their staging environment (IPs: 10.50.10.10–10.50.10.12). The engagement runs for one week. Social engineering and denial-of-service testing are NOT permitted. The CISO (Jane Doe, jdoe@securebank-lab.com, +1-555-0100) is the authorizing executive. You must report any critical findings within 2 hours of discovery.

**Deliverable:**
```bash
nano ~/CEH_Labs/Day02_SecureBank_RoE.md
```

Your completed RoE must include all 8 sections from the template. It must be specific to this scenario (not generic). Minimum 400 words.

**Expected outcome:** A professional-grade RoE document that a real CISO could review and sign.

---

## [CHALLENGE]

### Advanced: Comparative Legal Analysis

Research how **three different countries** handle unauthorized computer access. Compare:

| Country | Primary Law | Max Penalty | Notable Case |
|---------|------------|------------|-------------|
| USA | CFAA | | |
| UK | Computer Misuse Act 1990 | | |
| [Choose: Germany, Australia, India, Canada, etc.] | | | |

**Questions to answer:**
1. Which country has the strictest penalties?
2. Which country's law is most protective of security researchers?
3. If you discovered a vulnerability in a French company's website while located in India, which country's laws apply to you?

Write your findings in:
```bash
nano ~/CEH_Labs/Day02_challenge_legal_comparison.md
```

---

## [REFLECTION]

**R1.** Aaron Swartz was facing 35 years in prison for downloading academic articles from JSTOR. Many people felt this was disproportionate. As a cybersecurity professional, how do you balance the need for strong cyber laws with the risk of criminalizing legitimate security research? What reforms, if any, would you recommend to the CFAA?

*Your answer:*

---

**R2.** You are hired by Company X to pentest their system. During the engagement, you discover they are secretly collecting user data illegally (GDPR violation). You are under NDA. What do you do? Walk through the ethical and legal considerations.

*Your answer:*

---

## [SELF-CHECK]

- [ ] I can name the primary cyber law in the US, India, and EU
- [ ] I know what makes a verbal authorization legally insufficient
- [ ] I can list all 8 sections of a proper Rules of Engagement document
- [ ] I understand the difference between responsible disclosure and irresponsible disclosure
- [ ] I know what GDPR requires of organizations regarding security
- [ ] I can explain what a safe harbor clause is in a bug bounty context
- [ ] I completed the RoE document for SecureBank Ltd.
- [ ] I reviewed at least one real bug bounty program scope (from practical.md)
- [ ] I understand that cloud provider permission is needed separately from client permission
- [ ] I know what to do if I discover a critical vulnerability outside my assigned scope

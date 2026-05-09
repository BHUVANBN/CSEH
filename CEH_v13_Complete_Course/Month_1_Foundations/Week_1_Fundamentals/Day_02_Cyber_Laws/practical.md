# Day 02 — Practical: Legal Documents & Bug Bounty Analysis

> **Time Estimate:** 1.5–2 hours
> **⚠️ Safety Warning:** This practical is entirely non-technical and safe. You are drafting documents and reviewing public information — no system access required. This is the most important "soft skill" practical in the course.

---

## [ENVIRONMENT NEEDED]

- **OS:** Any (Kali Linux, Windows, or your host machine)
- **Tools required:** Text editor (nano, vim, VSCode, or any word processor)
- **Internet access:** Required for bug bounty review section
- **No special installations needed**

---

## [STEP-BY-STEP PRACTICAL]

### Part 1: Draft a Rules of Engagement (RoE) Document

**Scenario:** You have been hired by "SecureBank Ltd." to perform a web application penetration test on their customer portal located at `https://portal.securebank-lab.com`. The engagement is authorized by the CISO, starts next Monday, and runs for 2 weeks. Social engineering and DoS testing are explicitly out of scope.

**1.** Open a terminal and create your RoE file:
```bash
mkdir -p ~/CEH_Labs/legal_templates
nano ~/CEH_Labs/legal_templates/RoE_SecureBank.md
```

**2.** Copy and fill in this template:

```markdown
# RULES OF ENGAGEMENT DOCUMENT
**Engagement Type:** Web Application Penetration Test
**Client:** SecureBank Ltd.
**Testing Firm:** [Your Name / Company]
**Version:** 1.0
**Date:** [Today's Date]
**Classification:** CONFIDENTIAL

---

## 1. AUTHORIZATION
This document authorizes [Tester Name] to conduct penetration testing activities
as described herein. This is signed by:

- **Authorizing Executive:** [CISO Name], Chief Information Security Officer
- **Company:** SecureBank Ltd.
- **Signature:** ___________________________
- **Date:** [Date]

## 2. SCOPE
### In Scope:
- Web application: https://portal.securebank-lab.com
- IP range: 10.10.10.0/24 (staging environment only)
- Authentication mechanisms on the portal
- All web application endpoints listed in Appendix A

### Out of Scope:
- Production database servers
- Third-party payment processor (Stripe integration)
- Mobile application
- Employee email systems
- Any system not explicitly listed above

## 3. TESTING PERIOD
- **Start Date:** [Monday's date]
- **End Date:** [Monday + 14 days]
- **Approved Testing Hours:** 6:00 PM to 8:00 AM local time (off-peak)
- **Weekend Testing:** Permitted with 24-hour advance notice

## 4. PERMITTED ATTACK TYPES
- [x] Automated vulnerability scanning
- [x] Manual web application testing
- [x] Authentication bypass attempts
- [x] Injection testing (SQLi, XSS, CSRF, etc.)
- [x] Business logic testing
- [ ] Social engineering — NOT PERMITTED
- [ ] Denial of Service — NOT PERMITTED
- [ ] Physical access testing — NOT PERMITTED

## 5. COMMUNICATION
### Primary Contact (Client):
- Name: [Client Contact Name]
- Role: Security Manager
- Email: security@securebank-lab.com
- Phone: [Phone Number]

### Emergency Escalation:
- Name: [CISO Name]
- Phone: [Emergency Phone]
- Available: 24/7 during engagement

### Tester Contact:
- Name: [Your Name]
- Email: [Your Email]
- Phone: [Your Phone]

## 6. FINDINGS COMMUNICATION
- **Critical findings** (CVSS 9.0+): Notify client within 4 hours of discovery
- **High findings** (CVSS 7.0–8.9): Notify within 24 hours
- **Medium/Low findings:** Include in final report
- **Final report delivery:** Within 5 business days of engagement end

## 7. DATA HANDLING
- All client data discovered during testing will be stored encrypted on tester's system
- Data will be permanently deleted within 30 days of report delivery
- Tester will not retain copies of any credentials, PII, or financial data found

## 8. LEGAL STATEMENT
This document constitutes written authorization for the activities described above.
The client agrees that the tester is authorized to perform these activities and
accepts that some testing activities may temporarily affect system performance.

Agreed and signed:

Client: _________________________ Date: _______
Tester: _________________________ Date: _______
```

**3.** Save the document (Ctrl+X, Y, Enter in nano)

**Expected output:** A well-structured RoE document saved at `~/CEH_Labs/legal_templates/RoE_SecureBank.md`

[SCREENSHOT: Terminal showing the file saved successfully, followed by `cat` output displaying the formatted document]

---

### Part 2: Draft an Authorization Letter Template

**4.** Create the authorization letter:
```bash
nano ~/CEH_Labs/legal_templates/Authorization_Letter_Template.md
```

**5.** Fill in this template:

```markdown
[Company Letterhead]
[Company Logo]

Date: [Date]

To Whom It May Concern:

This letter serves as written authorization for [Tester/Firm Name] to conduct
penetration testing and security assessment activities on behalf of [Company Name].

## AUTHORIZED ACTIVITIES
The authorized party is permitted to:
- Perform network scanning and enumeration
- Test for vulnerabilities in specified systems
- Attempt to exploit identified vulnerabilities within the defined scope
- Access systems within scope using discovered credentials

## AUTHORIZED SYSTEMS
The following systems are authorized for testing:
- IP Range: [x.x.x.x/xx]
- Domain: [domain.com and subdomains]
- Web Application: [URL]

## AUTHORIZATION PERIOD
This authorization is valid from [Start Date] to [End Date].

## AUTHORIZING INDIVIDUAL
Name: [Full Name]
Title: [Job Title - must be executive with authority]
Company: [Company Name]
Signature: _______________________
Date: ___________________________

## EMERGENCY CONTACT
If law enforcement inquiries are received related to these authorized activities,
please contact: [Name] at [Phone] who can verify this authorization.

This authorization letter is issued in good faith and in compliance with all
applicable laws and regulations.
```

[SCREENSHOT: Completed authorization letter template in text editor]

---

### Part 3: Bug Bounty Scope Analysis

**6.** Open a browser and navigate to HackerOne's public programs:
```
https://hackerone.com/programs
```
Filter: **"Show public programs"** → sort by "Largest bounty"

**7.** Click on a well-known program (e.g., **Shopify**, **GitLab**, or **Twitter/X**)

**8.** Navigate to the **"Scope"** tab and identify:

Create a file to record your findings:
```bash
nano ~/CEH_Labs/bug_bounty_analysis.md
```

Document:
```markdown
# Bug Bounty Scope Analysis
**Program:** [Company Name]
**Date Reviewed:** [Today]

## IN-SCOPE ASSETS:
[List all in-scope domains, apps, and IPs]

## OUT-OF-SCOPE ASSETS:
[List all explicitly excluded items]

## PROHIBITED ACTIONS:
[List what testers are NOT allowed to do]

## BOUNTY REWARDS:
- Critical: $[amount]
- High: $[amount]
- Medium: $[amount]
- Low: $[amount]

## SAFE HARBOR CLAUSE:
[Copy the exact safe harbor language from the program]

## ANALYSIS:
- What makes this scope well-defined or poorly defined?
- What ambiguities exist that could cause confusion?
- Would you feel comfortable testing this program? Why or why not?
```

**Expected output:** A structured analysis showing you understand what is and is not permitted in a real-world bug bounty program.

---

## [TOOL REFERENCE]

### Useful Resources for Legal Document Research

```bash
# Download sample pentest contract templates
curl -L https://github.com/WebBreacher/pentest-templates -o pentest_templates.zip

# View your created documents
ls -la ~/CEH_Labs/legal_templates/
cat ~/CEH_Labs/legal_templates/RoE_SecureBank.md

# Count words in a document (verify minimum length)
wc -w ~/CEH_Labs/legal_templates/RoE_SecureBank.md
```

### Bug Bounty Platforms to Review

| Platform | URL | Notes |
|----------|-----|-------|
| HackerOne | https://hackerone.com/programs | Largest public programs |
| Bugcrowd | https://bugcrowd.com/programs | Wide industry coverage |
| Intigriti | https://intigriti.com/programs | Europe-focused |
| Synack | https://synack.com | Invite-only, vetted researchers |
| YesWeHack | https://yeswehack.com | Global, EU-compliant |

### Key Terms for Legal Documentation

| Term | Plain English Meaning |
|------|----------------------|
| Statement of Work (SoW) | Detailed description of what work will be performed |
| Master Service Agreement (MSA) | Overarching contract governing all work between two parties |
| Non-Disclosure Agreement (NDA) | Contract to keep information confidential |
| Rules of Engagement (RoE) | Operational rules for how testing will be conducted |
| Authorization Letter | Specific permission to perform defined testing activities |
| Safe Harbor | Legal protection clause in bug bounty programs |
| Responsible Disclosure | Private notification to vendor before public announcement |

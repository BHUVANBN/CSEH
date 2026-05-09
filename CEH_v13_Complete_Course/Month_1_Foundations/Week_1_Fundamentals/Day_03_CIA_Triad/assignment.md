# Day 03 — Assignment: CIA Triad & Core Security Concepts

> **Difficulty:** Beginner
> **Estimated Time:** 1.5 hours

---

## [THEORY QUESTIONS]

**Q1.** For each of the following attacks, identify which CIA property (or properties) it violates and explain why:
- A hacker exfiltrates a company's customer database
- A ransomware attack encrypts all files and demands payment
- An employee modifies financial records to embezzle money
- A DDoS attack takes down an e-commerce website during Black Friday

**Q2.** Explain the difference between a CVE and a CWE. Give one example of each.

**Q3.** What is a zero-day vulnerability? Why are zero-days so dangerous compared to known vulnerabilities?

**Q4.** What is the CVSS scoring system? What does a CVSS score of 9.8 mean in practical terms?

**Q5.** Define "attack surface." Give three examples of actions that *reduce* the attack surface of a web application.

---

## [PRACTICAL TASK]

### Map 3 Real Breaches to CIA Triad Failures

Research three of the following breaches and map each one to a CIA failure:
- 2013 Target breach
- 2014 Sony Pictures hack
- 2016 Bangladesh Bank SWIFT hack
- 2017 Equifax breach
- 2021 Colonial Pipeline ransomware
- 2021 Log4Shell (Log4j) exploitation

For each breach, create a table entry:

```markdown
## Breach: [Name]
**Year:** 
**Attacker:**
**Method:**

| CIA Property | Violated? | How? |
|---|---|---|
| Confidentiality | Yes/No | |
| Integrity | Yes/No | |
| Availability | Yes/No | |

**Primary control that failed:**
**What should have prevented it:**
```

Save your analysis:
```bash
nano ~/CEH_Labs/Week1/Day03/breach_analysis.md
```

---

## [CHALLENGE]

### Integrity Check Script

Write a bash script that:
1. Takes a directory as input
2. Generates SHA-256 hashes of all `.conf` files in that directory
3. Saves them to a baseline file `hashes_baseline.txt`
4. Can be run again in "check mode" to compare current hashes against baseline
5. Alerts on any changes, new files, or deleted files

```bash
nano ~/CEH_Labs/Week1/Day03/fim_script.sh
```

Test it on `/etc/` (view only — do not modify):
```bash
./fim_script.sh /etc baseline
./fim_script.sh /etc check
```

---

## [REFLECTION]

**R1.** The CIA Triad has been the dominant security model for decades. Some argue it's insufficient for modern threats (AI-generated deepfakes, supply chain attacks). Do you agree? What additional properties would you add and why?

**R2.** A company tells you "we use SHA-256 to hash all passwords." Is this sufficient? What additional protection is needed and why? (Hint: research "salted hashes" and "bcrypt")

---

## [SELF-CHECK]

- [ ] I can explain Confidentiality, Integrity, and Availability in plain English
- [ ] I know at least 2 attacks against each CIA property
- [ ] I can explain the difference between CVE, CWE, and CVSS
- [ ] I know what a zero-day is and why it's dangerous
- [ ] I understand the risk formula: Risk = Probability × Impact
- [ ] I ran the md5sum and sha256sum commands and observed hash changes after file modification
- [ ] I encrypted and decrypted a file with openssl successfully
- [ ] I completed the 3-breach CIA analysis
- [ ] I understand STRIDE threat modeling categories
- [ ] I know what "attack surface" means and how to reduce it

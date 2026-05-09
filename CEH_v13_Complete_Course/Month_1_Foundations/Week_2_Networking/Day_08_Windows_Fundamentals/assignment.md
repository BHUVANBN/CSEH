# Day 08 — Assignment: Windows Security Fundamentals

> **Difficulty:** Beginner-Intermediate
> **Estimated Time:** 1.5 hours

---
## [THEORY QUESTIONS]

**Q1.** What is the difference between SYSTEM and Administrator on Windows? In what scenario would an attacker prefer SYSTEM privileges?

**Q2.** Explain what pass-the-hash is. Why does it work? What Windows protocol does it exploit?

**Q3.** What Windows Event IDs would you monitor to detect: (a) brute force attacks, (b) new admin account creation, (c) new service installation?

**Q4.** What is UAC? What is a UAC bypass and why is it useful to attackers?

**Q5.** Explain SMB null sessions. What information can be enumerated through a null session on older Windows systems?

---
## [PRACTICAL TASK]

On your Windows VM, document all running services:
1. Run `sc query type= running` and save output
2. Identify 3 services that could be attack vectors (unnecessary services, old versions)
3. For each identified service, find its executable path with: `sc qc ServiceName`
4. Research if each service has known CVEs from 2022-2024

Document findings in:
```
notepad C:\Users\%USERNAME%\Desktop\service_audit.txt
```

---
## [CHALLENGE]

Research two CVEs related to Windows services from 2023-2024 on https://nvd.nist.gov:
- CVE number
- Affected service/component
- CVSS score and severity
- Attack vector (local vs network)
- Whether a patch is available
- Proof-of-concept available publicly?

Write a 1-page analysis explaining which is more dangerous in an enterprise context and why.

---
## [REFLECTION]

**R1.** PowerShell logging (ScriptBlock logging, Module logging, Transcription) can capture attacker activity. Why do attackers encode PowerShell commands in base64 (`-enc`)? Does this bypass logging?

**R2.** Windows Defender ATP / Microsoft Defender for Endpoint can detect many attack techniques. How does this change the attacker's approach? What is "living off the land" (LOLBins) and how does it evade detection?

---
## [SELF-CHECK]
- [ ] I know the Windows directory structure and purpose of System32, Users, ProgramData
- [ ] I know the 5 Windows Registry root keys and their purposes
- [ ] I can list Event IDs for logon (4624), failed logon (4625), new process (4688)
- [ ] I understand NTLM authentication and why pass-the-hash works
- [ ] I ran ipconfig, netstat, tasklist, sc query, net user on Windows
- [ ] I ran basic PowerShell commands (Get-Process, Get-Service, Get-LocalUser)
- [ ] I completed the service audit task
- [ ] I know what SYSTEM vs Administrator privileges mean

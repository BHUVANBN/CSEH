# Day 07 — Assignment: Linux Fundamentals

> **Difficulty:** Beginner-Intermediate
> **Estimated Time:** 1.5 hours

---
## [THEORY QUESTIONS]

**Q1.** What does `-rwsr-xr-x` mean? Which special permission bit is set? Why is this potentially dangerous from a security perspective?

**Q2.** What is the difference between `kill PID` and `kill -9 PID`? When would you use each?

**Q3.** Explain the fields in `/etc/passwd` format: `root:x:0:0:root:/root:/bin/bash`. What does each field mean?

**Q4.** What is a cron job? How can an attacker use cron for persistence after compromising a system?

**Q5.** Explain the difference between `>` and `>>` in bash. Give a practical example of when each is appropriate.

---
## [PRACTICAL TASK]

Write a bash script `pentest_setup.sh` that:
1. Creates directory `~/Pentests/<date>_engagement/` with subdirs: Recon, Scanning, Exploitation, PostExploit, Reporting
2. Creates a `README.md` in each subdir with the section name as heading
3. Creates a `scope.txt` in the root with placeholder IP ranges
4. Creates a cron job to back up the folder daily at midnight to `/tmp/backup/`
5. Prints completion summary with paths

Test the script and verify output with `tree`.

---
## [CHALLENGE]

Create a log analysis script that:
- Reads `/var/log/auth.log`
- Extracts all failed SSH login attempts
- Groups by source IP and counts attempts
- Flags any IP with >5 attempts as "SUSPICIOUS"
- Outputs a sorted report to `~/CEH_Labs/Week2/Day07/ssh_report.txt`

---
## [REFLECTION]

**R1.** You gain shell access to a compromised Linux server. You run `find / -perm -4000 2>/dev/null` and see `/usr/bin/find` with SUID. How could you exploit this? (Research GTFOBins)

**R2.** An attacker modifies `/etc/crontab` to run a reverse shell at boot. As a defender, how would you detect this? What monitoring would you put in place?

---
## [SELF-CHECK]
- [ ] I can read and interpret Linux file permission strings
- [ ] I can use chmod with both octal and symbolic notation
- [ ] I understand the purpose of SUID and why it matters for privilege escalation
- [ ] I can create, modify, and delete users on Linux
- [ ] I can extract data using grep, awk, cut, sort, and uniq in pipelines
- [ ] I understand cron job syntax and schedule format
- [ ] I completed the pentest_setup.sh script
- [ ] My script runs without errors and creates the correct structure

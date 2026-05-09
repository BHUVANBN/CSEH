# Day 07 — Linux Fundamentals

## [TOPIC OVERVIEW]
Linux is the operating system of cybersecurity. Web servers, IoT devices, cloud instances, routers, and every major hacking tool runs on Linux. For the ethical hacker, Linux proficiency is not optional — it is the baseline skill that everything else builds upon. Kali Linux is Debian-based, and understanding Linux file permissions, user management, process control, text processing, and shell scripting will directly impact your effectiveness in every lab from this point forward.

**CEH v13 connection:** Linux commands appear throughout the CEH exam, particularly in the context of post-exploitation, log analysis, and tool usage. Approximately 10–15% of practical CEH scenarios assume Linux fluency.

---
## [KEY CONCEPTS]

### File Permissions
Linux permissions use a 10-character string: `-rwxr-xr--`
- Position 1: file type (`-`=file, `d`=directory, `l`=symlink)
- Positions 2-4: owner permissions (rwx)
- Positions 5-7: group permissions (r-x)
- Positions 8-10: others permissions (r--)

**Octal notation:**
| Octal | Binary | Meaning |
|-------|--------|---------|
| 7 | 111 | rwx |
| 6 | 110 | rw- |
| 5 | 101 | r-x |
| 4 | 100 | r-- |
| 0 | 000 | --- |

```bash
chmod 755 script.sh     # rwxr-xr-x
chmod 644 file.txt      # rw-r--r--
chmod u+x script.sh     # add execute for owner
chmod o-r file.txt      # remove read from others
chown user:group file   # change owner and group
```

### Special Permissions
- **SUID (4):** File executes with owner's privileges → `chmod 4755 file` → `-rwsr-xr-x`
- **SGID (2):** File executes with group's privileges
- **Sticky bit (1):** Only owner can delete file (used on /tmp) → `chmod 1777 /tmp`

SUID binaries are critical in privilege escalation: `find / -perm -4000 2>/dev/null`

### User Management
```bash
/etc/passwd   # User accounts (username:x:UID:GID:comment:home:shell)
/etc/shadow   # Password hashes (root readable only)
/etc/group    # Group definitions

sudo adduser username        # Create user (interactive)
sudo useradd -m username     # Create user (non-interactive)
sudo passwd username         # Set password
sudo usermod -aG sudo user   # Add to sudo group
sudo deluser username        # Delete user
su - username                # Switch user
sudo -l                      # List sudo privileges
```

**Shadow file hash format:** `$6$salt$hash` — `$6` = SHA-512, `$1` = MD5, `$2y` = bcrypt

### Process Management
```bash
ps aux                  # All processes (a=all, u=user-oriented, x=no-tty)
ps -ef                  # Alternative full format
top                     # Live process monitor
htop                    # Better live monitor (install: apt install htop)
kill PID                # Send SIGTERM (graceful)
kill -9 PID             # Send SIGKILL (force)
killall processname     # Kill by name
jobs                    # List background jobs
bg %1                   # Resume job 1 in background
fg %1                   # Bring job 1 to foreground
command &               # Run in background
nohup command &         # Run immune to hangup signal
```

### Text Processing Pipeline
```bash
cat file.txt | grep "error" | sort | uniq -c | sort -rn | head -10
```
This pipeline: reads file → finds "error" lines → sorts → counts unique → re-sorts by count → shows top 10. This exact pattern is used in log analysis constantly.

| Tool | Purpose | Example |
|------|---------|---------|
| grep | Search patterns | `grep -r "password" /var/log/` |
| awk | Field processing | `awk -F: '{print $1}' /etc/passwd` |
| sed | Stream editor | `sed 's/old/new/g' file.txt` |
| cut | Column extractor | `cut -d: -f1 /etc/passwd` |
| sort | Sort lines | `sort -n` (numeric), `-r` (reverse) |
| uniq | Remove duplicates | `uniq -c` (count occurrences) |
| wc | Count | `wc -l file.txt` (count lines) |
| head/tail | First/last lines | `tail -f /var/log/syslog` |

### Redirection & Piping
```bash
command > file.txt      # Redirect stdout (overwrite)
command >> file.txt     # Redirect stdout (append)
command 2> errors.txt   # Redirect stderr
command 2>/dev/null     # Discard errors
command &> all.txt      # Redirect both stdout and stderr
command1 | command2     # Pipe stdout of cmd1 to stdin of cmd2
```

### Cron Jobs
```bash
crontab -l              # List current user's cron jobs
crontab -e              # Edit cron jobs
crontab -r              # Remove all cron jobs
sudo crontab -l -u user # List another user's crons
cat /etc/crontab        # System-wide cron
ls /etc/cron.d/         # Additional cron files
```

**Cron syntax:** `minute hour day month weekday command`
```
0 2 * * * /usr/bin/backup.sh     # Run at 2 AM daily
*/5 * * * * /usr/bin/check.sh    # Run every 5 minutes
@reboot /usr/bin/startup.sh      # Run at boot
```

### Shell Scripting Basics
```bash
#!/bin/bash
# Basic script structure
VAR="value"
echo "Hello $VAR"
if [ "$VAR" == "value" ]; then echo "match"; fi
for i in 1 2 3; do echo $i; done
while [ condition ]; do commands; done
function myfunc() { echo "function"; }
```

---
## [CEH EXAM FOCUS]
1. File permission interpretation — read -rwsr-xr-x and state permissions
2. /etc/passwd and /etc/shadow — know fields and what they contain
3. SUID bit — why it matters for privilege escalation
4. grep syntax — find patterns in logs
5. Cron job persistence — attackers use @reboot for persistence

### Tricky Areas
- `/etc/passwd` is world-readable; `/etc/shadow` is root-only — many confuse these
- `chmod 777` is a critical misconfiguration — world-writable directories/files
- SUID on shell binaries (`/bin/bash -p`) can give instant root shell

---
## [REAL-WORLD CONTEXT]
### Dirty COW — CVE-2016-5195
A race condition in the Linux kernel's Copy-On-Write mechanism allowed any local user to gain root privileges by writing to read-only memory-mapped files. SUID binaries like `/usr/bin/passwd` were common targets. Affected virtually every Linux kernel from 2.6.22 (2007) to 4.8.3 (2016). Patched within days but millions of unpatched systems remain vulnerable today.

---
**Key Takeaway:** Linux mastery is a force multiplier. Every minute you invest in learning Linux fundamentals saves hours in every future lab. The command pipeline pattern (grep | sort | uniq | head) is one of the most powerful tools in a security analyst's arsenal.

# Day 07 — Practical: Linux Administration & Scripting

> **Time Estimate:** 2 hours
> **Safety Warning:** Run all commands on Kali Linux VM only. Be careful with rm -rf and permission changes.

---
## [ENVIRONMENT NEEDED]
- OS: Kali Linux
- Tools: All pre-installed
- No additional installs needed

---
## [STEP-BY-STEP PRACTICAL]

### Part 1: Permissions

**1.** Create test files and view permissions:
```bash
mkdir -p ~/CEH_Labs/Week2/Day07 && cd ~/CEH_Labs/Week2/Day07
touch file1.txt file2.txt script.sh
ls -la
```

**2.** Set various permissions:
```bash
chmod 755 script.sh
chmod 644 file1.txt
chmod 600 file2.txt
ls -la
```

**3.** Add executable and verify:
```bash
echo '#!/bin/bash
echo "Script running as: $(whoami)"' > script.sh
chmod u+x script.sh
./script.sh
```

**4.** Find SUID binaries on system:
```bash
find / -perm -4000 2>/dev/null | head -20
```
Expected: List of SUID binaries including /usr/bin/sudo, /usr/bin/passwd etc.

### Part 2: User Management

**5.** Create a test user:
```bash
sudo adduser testuser
```

**6.** View user in passwd:
```bash
grep testuser /etc/passwd
```

**7.** View shadow entry (hash):
```bash
sudo grep testuser /etc/shadow
```

**8.** Add to sudo group:
```bash
sudo usermod -aG sudo testuser
groups testuser
```

**9.** Switch to user and verify:
```bash
su - testuser
whoami
sudo whoami
exit
```

**10.** Extract all usernames with real shells:
```bash
grep -v "nologin\|false" /etc/passwd | cut -d: -f1
```

### Part 3: Text Processing Pipeline

**11.** Extract usernames from passwd:
```bash
cat /etc/passwd | cut -d: -f1 | sort | uniq
```

**12.** Count failed SSH attempts:
```bash
grep "Failed password" /var/log/auth.log 2>/dev/null | wc -l
```

**13.** Find top attacking IPs:
```bash
grep "Failed password" /var/log/auth.log 2>/dev/null | awk '{print $(NF-3)}' | sort | uniq -c | sort -rn | head -10
```

**14.** Search recursively for "password" in logs:
```bash
grep -r "password" /var/log/ 2>/dev/null | grep -v "Binary file" | head -10
```

### Part 4: Shell Script — Pentest Folder Creator

**15.** Create automation script:
```bash
nano ~/CEH_Labs/create_project.sh
```
```bash
#!/bin/bash
# Pentest project folder creator
PROJECT_NAME="$1"
if [ -z "$PROJECT_NAME" ]; then
    echo "Usage: $0 <project-name>"
    exit 1
fi
BASE="$HOME/Pentests/$PROJECT_NAME"
for dir in Recon Scanning Exploitation Post-Exploitation Reporting; do
    mkdir -p "$BASE/$dir"
    echo "# $dir Notes" > "$BASE/$dir/README.md"
    echo "Created $BASE/$dir"
done
echo "Project structure created at $BASE"
```
```bash
chmod +x ~/CEH_Labs/create_project.sh
~/CEH_Labs/create_project.sh MyFirstPentest
tree ~/Pentests/
```

### Part 5: Cron Job Demo

**16.** Add a test cron job:
```bash
(crontab -l 2>/dev/null; echo "*/1 * * * * echo test >> /tmp/cron_test.txt") | crontab -
crontab -l
```

**17.** Wait 1 minute, then check:
```bash
cat /tmp/cron_test.txt
```

**18.** Remove the test cron:
```bash
crontab -r
```

---
## [TOOL REFERENCE]

```bash
# Permissions
chmod 755 file              # rwxr-xr-x
chmod u+x,g-w file          # symbolic mode
chown user:group file       # change owner
find / -perm -4000 2>/dev/null  # find SUID files

# Users
cat /etc/passwd | cut -d: -f1,3,7   # username:UID:shell
sudo cat /etc/shadow | cut -d: -f1,2 # username:hash

# Text processing
grep -r "term" /path/        # recursive search
awk -F: '{print $1}' file    # field separator, print field 1
sed 's/old/new/g' file       # replace all occurrences
cut -d: -f1,3 file           # cut fields 1 and 3
sort -n | uniq -c | sort -rn # sort numerically, count, re-sort
```

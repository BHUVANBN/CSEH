# Day 04 — Practical: Kali Linux Navigation & Configuration

> **Time Estimate:** 1.5–2 hours
> **⚠️ Safety Warning:** Run all commands on your Kali VM only. The `rm -rf` command is dangerous — always double-check paths before executing.

---

## [ENVIRONMENT NEEDED]

- **OS:** Kali Linux VM (from Day 01 setup)
- **Tools:** All pre-installed (bash, nano, apt)
- **No additional installs needed for this lab**

---

## [STEP-BY-STEP PRACTICAL]

### Part 1: Filesystem Exploration

**1.** Explore the root filesystem:
```bash
ls -la /
```
Expected: List of top-level directories with permissions, owner, size.

**2.** Examine each key directory:
```bash
ls /etc/ | head -30        # Configuration files
ls /var/log/               # Log files
ls /usr/share/wordlists/   # Wordlists
ls /opt/                   # Optional tools
ls /proc/ | head -20       # Process info (numbers = PIDs)
```

**3.** View your current user and system info:
```bash
whoami
id
uname -a
cat /etc/os-release
```

**4.** View the user list:
```bash
cat /etc/passwd | grep -v "nologin\|false" | cut -d: -f1
```
Expected: Real user accounts (kali, root, etc.) without system accounts.

### Part 2: Terminal Customization

**5.** View your bash configuration:
```bash
cat ~/.bashrc
```

**6.** Add a custom prompt and aliases:
```bash
nano ~/.bashrc
```
Add at the bottom:
```bash
# Custom prompt: username@hostname:path in cyan
export PS1='\[\033[01;36m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '

# Useful aliases
alias ll='ls -la'
alias cls='clear'
alias myip='ip addr show | grep "inet " | awk "{print \$2}"'
alias update='sudo apt update && sudo apt upgrade -y'
```
Save and apply:
```bash
source ~/.bashrc
```

**7.** Test your aliases:
```bash
ll
myip
```

### Part 3: Create CEH Lab Folder Structure

**8.** Create your study lab directory tree:
```bash
mkdir -p ~/CEH_Labs/{Week1/{Day01,Day02,Day03,Day04},Week2/{Day05,Day06,Day07,Day08},Week3/{Day09,Day10,Day11,Day12},Week4/{Day13,Day14,Day15,Day16}}
```

**9.** Verify the structure:
```bash
find ~/CEH_Labs -type d | sort
```

**10.** Add README files to each week:
```bash
for week in Week1 Week2 Week3 Week4; do
  echo "# $week Lab Notes" > ~/CEH_Labs/$week/README.md
done
```

### Part 4: Package Management

**11.** Update package index:
```bash
sudo apt update
```

**12.** Install useful tools:
```bash
sudo apt install -y net-tools curl vim htop tree
```

**13.** Use tree to visualize your lab structure:
```bash
tree ~/CEH_Labs
```

**14.** Search for a tool:
```bash
apt search burpsuite
apt show burpsuite
```

**15.** View command history:
```bash
history
history | grep nmap
history | tail -20
```

### Part 5: Network Interface Verification

**16.** Check interfaces (two methods):
```bash
ifconfig                   # Old method (net-tools package)
ip addr show               # Modern method (iproute2)
ip link show               # Show link layer info
```

**17.** Check routing:
```bash
ip route show
```

---

## [TOOL REFERENCE]

### Essential Kali Commands

```bash
# System info
uname -a                   # Kernel version
lsb_release -a             # OS version
df -h                      # Disk usage
free -h                    # Memory usage
uptime                     # System uptime and load

# Process management
ps aux                     # All running processes
top                        # Live process monitor
htop                       # Better live monitor
kill <PID>                 # Kill process by PID
killall <name>             # Kill by name

# Network
ip addr show               # Interfaces and IPs
ip route show              # Routing table
ss -tuln                   # Listening ports (modern)
netstat -tuln              # Listening ports (classic)
```

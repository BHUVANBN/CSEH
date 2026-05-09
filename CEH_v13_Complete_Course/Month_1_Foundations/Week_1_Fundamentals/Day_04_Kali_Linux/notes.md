# Day 04 — Kali Linux Deep Dive

## [TOPIC OVERVIEW]

**Kali Linux** is a Debian-based Linux distribution maintained by Offensive Security, purpose-built for penetration testing, digital forensics, and security research. Released in 2013 as the successor to BackTrack Linux, Kali ships with over 600 pre-installed security tools organized by category. It is the industry-standard platform for ethical hackers and is used in CEH labs, OSCP training, CTF competitions, and real-world engagements.

Understanding Kali Linux is not just about knowing its tools — it is about understanding the operating system deeply enough to troubleshoot, customize, and build efficient workflows. A skilled ethical hacker controls their environment completely.

**Real-world relevance:** Red team operators and penetration testers live in Kali Linux. Every tool you will use throughout this course runs on Kali. Familiarity with its filesystem, package manager, terminal, and configuration is essential before you begin any offensive operations.

**CEH v13 connection:** The CEH exam expects you to know common Linux commands, the filesystem hierarchy, and the categories of tools available. Several lab scenarios in the CEH iLabs environment use Kali Linux.

---

## [KEY CONCEPTS]

### Kali Linux Architecture

- **Base:** Debian Testing (rolling release)
- **Desktop:** GNOME (default), also available with KDE, XFCE, LXDE
- **Kernel:** Hardened Linux kernel with additional patches
- **Maintained by:** Offensive Security (creators of OSCP)
- **License:** Open source, free

**Kali Variants:**
- **Kali Linux** — Full desktop installation for VM/bare metal
- **Kali NetHunter** — Mobile platform for Android rooted devices
- **Kali ARM** — Raspberry Pi and ARM devices
- **Kali Docker** — Lightweight containerized version
- **Kali WSL** — Windows Subsystem for Linux version

---

### Linux Filesystem Hierarchy Standard (FHS)

Understanding the filesystem layout is fundamental to every Linux operation:

```
/                   Root directory — top of the hierarchy
├── /bin            Essential user binaries (ls, cp, mv, bash)
├── /sbin           System binaries (ifconfig, iptables) — usually root-only
├── /etc            System-wide configuration files (/etc/passwd, /etc/ssh/)
├── /home           User home directories (/home/kali, /home/batman)
├── /root           Root user's home directory
├── /var            Variable data: logs (/var/log/), databases, mail
├── /tmp            Temporary files — cleared on reboot
├── /usr            User programs and libraries
│   ├── /usr/bin    Non-essential user binaries
│   ├── /usr/share  Architecture-independent data (wordlists here!)
│   └── /usr/local  Locally compiled/installed software
├── /opt            Optional/third-party software (Burp Suite, custom tools)
├── /proc           Virtual filesystem — kernel and process info (/proc/cpuinfo)
├── /dev            Device files (/dev/sda = first hard drive, /dev/eth0)
├── /mnt            Temporary mount points for filesystems
├── /media          Auto-mounted removable media (USB drives)
└── /lib            Essential shared libraries
```

**Key for pentesters:**
- `/usr/share/wordlists/` — RockYou, SecLists wordlists
- `/usr/share/metasploit-framework/` — Metasploit modules
- `/usr/share/nmap/scripts/` — NSE scripts
- `/opt/` — Tools installed manually (e.g., custom exploits)
- `/var/log/` — All system logs (auth.log, syslog, etc.)
- `/etc/passwd` — User list (readable by all)
- `/etc/shadow` — Password hashes (root only)

---

### Kali Tool Categories

| Category | Purpose | Key Tools |
|----------|---------|-----------|
| **Information Gathering** | Reconnaissance | Nmap, theHarvester, Maltego, Recon-ng |
| **Vulnerability Analysis** | Finding weaknesses | Nikto, OpenVAS, Lynis |
| **Web Application Analysis** | Web testing | Burp Suite, sqlmap, Dirb, Gobuster |
| **Password Attacks** | Cracking creds | Hydra, John the Ripper, Hashcat, Medusa |
| **Wireless Attacks** | Wi-Fi testing | Aircrack-ng, Bettercap, Reaver |
| **Exploitation Tools** | Gaining access | Metasploit, BeEF, searchsploit |
| **Sniffing & Spoofing** | Traffic analysis | Wireshark, Tcpdump, Ettercap |
| **Post Exploitation** | After compromise | Mimikatz, Powersploit, Weevely |
| **Forensics** | Evidence analysis | Autopsy, Volatility, Foremost |
| **Reverse Engineering** | Binary analysis | Ghidra, Radare2, GDB |
| **Reporting Tools** | Documentation | Dradis, Faraday, CherryTree |

---

### Package Management with APT

```bash
sudo apt update                    # Refresh package index
sudo apt upgrade -y                # Upgrade all packages
sudo apt install <package> -y      # Install a package
sudo apt remove <package>          # Remove package (keep config)
sudo apt purge <package>           # Remove package + config files
sudo apt autoremove                # Remove unused dependencies
apt search <keyword>               # Search for packages
apt show <package>                 # Show package details
dpkg -l | grep <name>             # Check if installed
```

---

### Running Kali: Root vs Non-Root

**Historical context:** Kali Linux used to run entirely as root (since pentesting tools often require root). Since Kali 2020.1, Kali defaults to a non-root user (`kali`) and uses `sudo` for privilege escalation — aligning with modern security practices.

**Best practice for CEH labs:**
- Run as non-root user `kali`
- Use `sudo` for commands requiring elevated privileges
- Only switch to root shell (`sudo -i`) when absolutely necessary

---

### Essential Terminal Skills

**Navigation:**
```bash
pwd           # Print Working Directory — where are you?
ls -la        # List files with permissions, hidden files, sizes
cd /path      # Change directory
cd ..         # Go up one level
cd ~          # Go to home directory
cd -          # Go to previous directory
```

**File operations:**
```bash
cp source dest           # Copy file
mv source dest           # Move or rename
rm file                  # Delete file
rm -rf directory/        # Delete directory recursively (DANGEROUS)
mkdir -p path/to/dir     # Create directory and parents
touch filename           # Create empty file or update timestamp
find / -name "*.txt"     # Find files by name
locate filename          # Fast search using database
which tool               # Find tool's location in PATH
```

**Text processing:**
```bash
cat file.txt              # Display entire file
less file.txt             # Paginated view
head -n 20 file.txt       # First 20 lines
tail -n 20 file.txt       # Last 20 lines
tail -f /var/log/syslog   # Follow log in real time
grep "pattern" file.txt   # Search for pattern
grep -r "pattern" /dir/   # Recursive search
```

---

## [CEH EXAM FOCUS]

1. **Linux directory purposes** — Know what lives in /etc, /var, /opt, /usr, /tmp
2. **APT commands** — install, update, upgrade, search
3. **Common Linux commands** — ls, cat, grep, find, chmod, chown, ps, netstat
4. **Kali tool categories** — Which category does Burp Suite / Nmap / Hydra belong to?
5. **Root vs non-root** — When is root required? (network sniffing, packet crafting)

### Tricky Areas
- `/etc/passwd` contains users, NOT passwords (passwords moved to `/etc/shadow`)
- `rm -rf /` is irreversible — never run without sanity-checking your path variable
- `sudo` vs `su` — sudo runs one command as root; su switches to root shell

---

## [REAL-WORLD CONTEXT]

### Case Study: Kali in Professional Red Team Operations

During the 2019 red team engagement against a Fortune 500 financial firm (published as a de-identified case study by Rapid7), the red team used Kali Linux running from a Raspberry Pi device hidden behind a server rack in the company's data center — planted during a physical access simulation. The Pi ran a reverse shell that phoned home over HTTPS. The entire 3-week engagement was controlled from this tiny Kali device.

**What this demonstrates:** Kali's flexibility — it runs on anything from a desktop to a credit-card-sized computer. The filesystem knowledge (where to store payloads, how to hide in /tmp, how logs work in /var) directly contributed to operational success.

---

**Key Takeaway:** Kali Linux is your primary weapon and workshop. Invest time learning the filesystem hierarchy, terminal commands, and package management now — every single lab exercise in this course depends on this foundation.

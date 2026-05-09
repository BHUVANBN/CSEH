# Day 08 — Windows Fundamentals for Ethical Hackers

## [TOPIC OVERVIEW]
Windows is the dominant operating system in enterprise environments — over 75% of corporate desktops and servers run Windows. For ethical hackers, Windows knowledge is critical because it is the most targeted platform by attackers. Understanding Windows architecture, Registry, services, event logs, and PowerShell is essential for both offensive operations (exploiting Windows targets) and defensive work (hardening and incident response).

**CEH v13 connection:** Module 06 (System Hacking) focuses heavily on Windows. Windows-specific attacks (pass-the-hash, RDP brute force, Registry persistence) are directly tested on the CEH exam.

---
## [KEY CONCEPTS]

### Windows Directory Structure
```
C:\
├── Windows\
│   ├── System32\          ← 64-bit system binaries (cmd.exe, notepad.exe)
│   ├── SysWOW64\          ← 32-bit binaries on 64-bit Windows
│   ├── Temp\             ← Temporary files
│   └── System32\config\ ← Registry hive files (SAM, SYSTEM, SECURITY)
├── Users\
│   ├── Administrator\    ← Admin home
│   ├── <username>\       ← User home
│   │   ├── AppData\      ← Application data (often hidden)
│   │   ├── Desktop\
│   │   └── Documents\
│   └── Public\           ← Shared folder
├── Program Files\         ← 64-bit applications
├── Program Files (x86)\ ← 32-bit applications
└── ProgramData\          ← Application data (hidden)
```

### Windows Registry
The Registry is a hierarchical database storing configuration settings for the OS and applications.

**Root keys (hives):**
| Hive | Abbreviation | Purpose |
|------|-------------|---------|
| HKEY_LOCAL_MACHINE | HKLM | Hardware, OS, services config |
| HKEY_CURRENT_USER | HKCU | Current user settings |
| HKEY_USERS | HKU | All user profiles |
| HKEY_CLASSES_ROOT | HKCR | File associations, COM objects |
| HKEY_CURRENT_CONFIG | HKCC | Hardware profile |

**Persistence Registry Keys (attackers use these):**
```
HKLM\Software\Microsoft\Windows\CurrentVersion\Run
HKCU\Software\Microsoft\Windows\CurrentVersion\Run
HKLM\Software\Microsoft\Windows\CurrentVersion\RunOnce
```
Any value in these keys runs automatically at login.

### Windows Services & Processes
```cmd
tasklist                      # List running processes
tasklist /svc                 # Show services per process
sc query                      # List all services
sc query type= running        # Only running services
sc start ServiceName          # Start service
sc stop ServiceName           # Stop service
net start                     # List running services (simpler)
services.msc                  # GUI service manager
```

**Key system processes:**
- `lsass.exe` — Local Security Authority (stores credentials in memory!)
- `svchost.exe` — Hosts Windows services
- `csrss.exe` — Client/Server Runtime Subsystem
- `winlogon.exe` — Handles logon/logoff

### Windows Users & Groups
```cmd
net user                           # List all users
net user username                  # User details
net user username password /add    # Create user
net localgroup                     # List groups
net localgroup Administrators      # List admin group members
net localgroup Administrators user /add  # Add to admins
whoami                             # Current user
whoami /priv                       # Current privileges
whoami /groups                     # Current group membership
```

**Built-in accounts:**
- `Administrator` — Full control
- `SYSTEM` / `NT AUTHORITY\SYSTEM` — Highest privilege (above Administrator!)
- `Guest` — Limited access
- `DefaultAccount` — System-managed

### Windows Event Logs
Accessible via `eventvwr.msc` or `Get-EventLog` in PowerShell.

**Critical Security Event IDs:**
| Event ID | Description |
|----------|------------|
| 4624 | Successful logon |
| 4625 | Failed logon |
| 4634 | Logoff |
| 4648 | Logon with explicit credentials |
| 4672 | Special privileges assigned at logon |
| 4688 | New process created |
| 4698 | Scheduled task created |
| 4720 | User account created |
| 4740 | Account locked out |
| 7045 | New service installed |

### UAC — User Account Control
UAC prompts for elevation when admin actions are required. Attackers attempt UAC bypass to escalate privileges silently. Common bypass techniques: eventvwr.exe COM hijacking, fodhelper.exe abuse.

### SMB Protocol
SMB (Server Message Block) on port 445 is used for Windows file sharing. Historically the most attacked Windows protocol:
- **MS17-010 (EternalBlue)** — Exploited by WannaCry and NotPetya
- **Null sessions** — Anonymous SMB connections to enumerate shares/users
- **Pass-the-hash** — Authenticate with NTLM hash instead of password

### PowerShell Basics
```powershell
Get-Process                        # List processes
Get-Service                        # List services
Get-LocalUser                      # List local users
Get-LocalGroup                     # List local groups
Get-EventLog -LogName Security -Newest 20   # Recent security events
Get-ChildItem C:\ -Recurse -Hidden        # Find hidden files
Invoke-WebRequest -Uri "http://url" -OutFile "file"  # Download file
Set-ExecutionPolicy Bypass -Scope Process  # Bypass execution policy
```

**PowerShell execution policy bypass (attacker technique):**
```powershell
powershell -ExecutionPolicy Bypass -File script.ps1
powershell -enc <base64-encoded-command>
```

---
## [CEH EXAM FOCUS]
1. Event ID numbers — 4624 (logon), 4625 (failed), 4688 (new process), 4698 (scheduled task)
2. Registry persistence keys — HKLM/HKCU Run keys
3. NTLM vs LM hash — NTLM is MD4-based; LM is weak, disabled by default since Vista
4. Windows privilege levels — SYSTEM > Administrator > Standard User
5. Pass-the-hash — authenticate using hash without knowing plaintext password

### Tricky Areas
- `C:\Windows\System32` contains 64-bit binaries on 64-bit Windows (confusing naming)
- `NT AUTHORITY\SYSTEM` has MORE privileges than `Administrator`
- PowerShell history stored at: `%APPDATA%\Microsoft\Windows\PowerShell\PSReadLine\ConsoleHost_history.txt`

---
## [REAL-WORLD CONTEXT]
### WannaCry Ransomware (2017)
WannaCry exploited MS17-010 (EternalBlue) — an SMB vulnerability in Windows allowing unauthenticated remote code execution. It infected 230,000+ machines in 150 countries in 24 hours. It ran as SYSTEM, encrypted files, and demanded Bitcoin ransom. The UK NHS was crippled — surgeries cancelled, patients turned away. Microsoft had released patch MS17-010 two months prior, but organizations had not applied it.

---
**Key Takeaway:** Windows knowledge is attack surface knowledge. Every service, Registry key, scheduled task, and event log entry is either a potential entry point or a defensive artifact. Learn both sides simultaneously.

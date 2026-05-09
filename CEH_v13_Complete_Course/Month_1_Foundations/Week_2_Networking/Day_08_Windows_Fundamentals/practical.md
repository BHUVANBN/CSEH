# Day 08 — Practical: Windows Fundamentals Exploration

> **Time Estimate:** 1.5 hours
> **Note:** These commands require a Windows VM (Windows 10/Server). You can use Windows Subsystem for Linux (WSL) host or a Windows VM. Some commands can be adapted to Kali using Impacket tools for remote Windows interaction.

---
## [ENVIRONMENT NEEDED]
- OS: Windows 10/Server 2019 VM (or WSL2 host Windows machine)
- Access: CMD (as Administrator) and PowerShell
- Optional: Kali Linux for remote Windows enumeration with Impacket

---
## [STEP-BY-STEP PRACTICAL]

### Part 1: CMD Reconnaissance

**1.** System and network info:
```cmd
ipconfig /all
systeminfo
hostname
whoami
whoami /priv
```

**2.** Network connections:
```cmd
netstat -ano
netstat -ano | findstr LISTENING
netstat -ano | findstr :445
```

**3.** Process list:
```cmd
tasklist
tasklist /svc
tasklist | findstr lsass
```

**4.** Service enumeration:
```cmd
sc query
sc query type= running
net start
```

**5.** User and group enumeration:
```cmd
net user
net localgroup
net localgroup Administrators
net localgroup "Remote Desktop Users"
```

**6.** Registry run keys (persistence check):
```cmd
reg query HKLM\Software\Microsoft\Windows\CurrentVersion\Run
reg query HKCU\Software\Microsoft\Windows\CurrentVersion\Run
```

**7.** Scheduled tasks:
```cmd
schtasks /query /fo LIST /v | findstr "Task Name\|Status\|Next Run"
```

### Part 2: PowerShell Investigation

**8.** Open PowerShell as Administrator and run:
```powershell
Get-Process | Sort-Object CPU -Descending | Select-Object -First 10
Get-Service | Where-Object Status -eq "Running"
Get-LocalUser | Select-Object Name, Enabled, LastLogon
Get-LocalGroup
```

**9.** Recent security events:
```powershell
Get-EventLog -LogName Security -Newest 20 | Select-Object TimeGenerated, EventID, Message | Format-List
```

**10.** Look for failed logon events:
```powershell
Get-EventLog -LogName Security -InstanceId 4625 -Newest 10
```

**11.** Check for suspicious scheduled tasks:
```powershell
Get-ScheduledTask | Where-Object State -eq "Ready" | Select-Object TaskName, TaskPath
```

### Part 3: Remote Windows Enumeration from Kali (using Impacket)

If you have a Windows VM on your Host-Only network:
```bash
# Install impacket on Kali
sudo pip install impacket

# Enumerate users via SMB
python3 /usr/share/doc/python3-impacket/examples/samrdump.py Administrator:password@192.168.56.x

# List shares
smbclient -L //192.168.56.x -U Administrator
```

---
## [TOOL REFERENCE]

```cmd
ipconfig /all              :: Network configuration
netstat -ano               :: Connections with PID
tasklist /svc              :: Processes with services
sc query                   :: Service list
net user                   :: User list
net localgroup             :: Group list
reg query <key>            :: Query registry
schtasks /query            :: Scheduled tasks
```

```powershell
Get-Process                # Process list
Get-Service                # Service list
Get-LocalUser              # Local users
Get-EventLog -LogName Security -Newest N   # Event log
Get-ScheduledTask          # Scheduled tasks
Get-NetFirewallRule        # Firewall rules
```

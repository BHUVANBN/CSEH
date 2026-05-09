# Day 01 — Practical: Setting Up Your Ethical Hacking Lab

> **Time Estimate:** 2–3 hours
> **⚠️ Safety Warning:** All activities must be performed in an **isolated lab network**. Never test tools or techniques on public networks, production systems, or systems you do not own. Use NAT + Host-Only networking in VirtualBox to ensure your lab VMs cannot reach the internet or your LAN during active testing.

---

## [ENVIRONMENT NEEDED]

### Hardware Requirements (Minimum)
- **RAM:** 8 GB (16 GB recommended for running multiple VMs simultaneously)
- **Storage:** 50 GB free disk space
- **CPU:** 64-bit processor with virtualization support (Intel VT-x or AMD-V enabled in BIOS)

### Software Required

| Software | Version | Download |
|----------|---------|---------|
| VirtualBox | 7.x | https://www.virtualbox.org/wiki/Downloads |
| Kali Linux ISO | Latest (2024.x) | https://www.kali.org/get-kali/ |
| Metasploitable2 | Latest | https://sourceforge.net/projects/metasploitable/ |
| DVWA (optional) | Latest | Docker: `docker run -d -p 80:80 vulnerables/web-dvwa` |

### Network Architecture

```
Your Host Machine
     │
     ├── VirtualBox Host-Only Adapter (vboxnet0: 192.168.56.0/24)
     │        │
     │        ├── Kali Linux VM     → 192.168.56.101 (attacker)
     │        └── Metasploitable2   → 192.168.56.102 (target)
     │
     └── VirtualBox NAT Adapter (for internet on Kali, disabled during attacks)
```

---

## [STEP-BY-STEP PRACTICAL]

### Part 1: Install VirtualBox

**1.** Download VirtualBox from https://www.virtualbox.org/wiki/Downloads

**2.** On Ubuntu/Debian host:
```bash
sudo apt update
sudo apt install virtualbox virtualbox-ext-pack -y
```

**3.** Verify installation:
```bash
vboxmanage --version
```
**Expected output:** `7.x.x` or similar version string

**4.** Enable virtualization in BIOS if not already done. Restart, enter BIOS (typically F2/Del/F12), find "Intel VT-x" or "AMD-V" and enable it.

---

### Part 2: Set Up Kali Linux VM

**5.** Open VirtualBox → Click **"New"**

**6.** Configure the new VM:
- **Name:** `Kali-Linux-CEH`
- **Type:** Linux
- **Version:** Debian (64-bit)
- **RAM:** 4096 MB (4 GB minimum)
- **Storage:** Create a new virtual hard disk → VDI → Dynamically allocated → **40 GB**

**7.** Attach the Kali ISO:
- Select your new VM → **Settings** → **Storage**
- Click the empty CD icon → **Choose a Disk File** → select your downloaded Kali ISO

**8.** Configure network (critical for lab isolation):
- Go to **Settings** → **Network**
- **Adapter 1:** Attached to **NAT** (for internet access during setup)
- **Adapter 2:** Attached to **Host-Only Adapter** → select `vboxnet0`

[SCREENSHOT: VirtualBox network settings showing NAT on Adapter 1 and Host-Only on Adapter 2]

**9.** Start the VM → Select **"Graphical Install"** from the Kali boot menu

**10.** Follow installation wizard:
- Language: English
- Location: your country
- Hostname: `kali-ceh`
- Username: `kali` (or your preferred name)
- Password: Use a strong password (min 12 chars for lab)
- Partition: **Guided — use entire disk** for simplicity

**Expected output after installation:** Kali Linux desktop loads with the default GNOME environment.

> **Troubleshooting:** If the VM won't boot after installation, ensure the ISO is detached: Settings → Storage → remove the CD.

---

### Part 3: Initial Kali Configuration

**11.** Open a terminal in Kali. Update the system:
```bash
sudo apt update && sudo apt upgrade -y
```
**Expected output:** Package lists downloaded, upgrades applied. This may take 10–20 minutes on first run.

**12.** Install commonly needed tools:
```bash
sudo apt install -y net-tools curl git vim htop
```

**13.** Verify your network interfaces:
```bash
ip addr show
```
**Expected output:** You should see at least two interfaces — `eth0` (NAT) and `eth1` (Host-Only). Note the IP addresses. Your Host-Only IP should be in the `192.168.56.x` range.

**14.** Take a snapshot (critical for recovery):
- In VirtualBox menu: **Machine → Take Snapshot**
- Name it: `Fresh-Install-Clean-State`

[SCREENSHOT: VirtualBox Snapshots panel showing the clean state snapshot]

> **Why snapshots matter:** If you break your Kali installation during labs (and you will), you can instantly restore to this clean state without reinstalling. Always take a snapshot before risky operations.

---

### Part 4: Set Up Metasploitable2 (Target VM)

**15.** Download Metasploitable2 from SourceForge (it comes as a `.vmdk` file)

**16.** In VirtualBox → **New**:
- **Name:** `Metasploitable2-Target`
- **Type:** Linux
- **Version:** Ubuntu (64-bit)
- **RAM:** 1024 MB (1 GB is sufficient)
- **Hard Disk:** **Use an existing virtual hard disk file** → select the downloaded `.vmdk`

**17.** Configure network — **Host-Only only** (no NAT — this VM should NEVER reach the internet):
- Settings → Network → Adapter 1 → Host-Only Adapter → `vboxnet0`

**18.** Start Metasploitable2. Default credentials:
```
Username: msfadmin
Password: msfadmin
```

**19.** Find its IP address:
```bash
ifconfig
```
**Expected output:** IP in range `192.168.56.x` — note this address, it will be your target in all future labs.

[SCREENSHOT: Metasploitable2 login screen with IP visible in the banner]

---

### Part 5: Verify Lab Connectivity

**20.** From your Kali VM, ping the Metasploitable2 target:
```bash
ping -c 4 192.168.56.102
```
**Expected output:**
```
PING 192.168.56.102: 56 data bytes
64 bytes from 192.168.56.102: icmp_seq=0 ttl=64 time=0.5 ms
...
4 packets transmitted, 4 received, 0% packet loss
```

> **Troubleshooting:** If ping fails:
> - Check that both VMs use the same Host-Only adapter (`vboxnet0`)
> - Run `vboxmanage list hostonlyifs` to verify the adapter is enabled
> - Check that the Host-Only network DHCP server is enabled in VirtualBox: **File → Host Network Manager**

**21.** From Kali, do a quick Nmap scan to confirm Metasploitable2 is reachable:
```bash
nmap -sn 192.168.56.0/24
```
**Expected output:** Should show at least 2 hosts up — your Kali and Metasploitable2.

**22.** Take another snapshot of both VMs in their current "lab-ready" state.

---

## [TOOL REFERENCE]

### VirtualBox CLI Cheatsheet

```bash
# List all VMs
vboxmanage list vms

# Start a VM
vboxmanage startvm "VM-Name" --type headless

# Take a snapshot
vboxmanage snapshot "VM-Name" take "Snapshot-Name"

# Restore a snapshot
vboxmanage snapshot "VM-Name" restore "Snapshot-Name"

# List snapshots
vboxmanage snapshot "VM-Name" list
```

### Basic Kali Verification Commands

```bash
# Check OS version
cat /etc/os-release

# Check kernel version
uname -r

# List installed security tools (sample)
ls /usr/bin/ | grep -E "nmap|wireshark|metasploit|hydra"

# Check available disk space
df -h

# Check memory usage
free -h
```

### Network Configuration Flags

```bash
# Show all interfaces
ip addr show

# Show routing table
ip route show

# Ping with count limit
ping -c 4 <target-ip>

# Trace network path
traceroute <target-ip>
```

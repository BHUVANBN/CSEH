# Day 14 — Practical: Nmap NSE Deep Dive

> **Time Estimate:** 1.5–2 hours
> **⚠️ Safety Warning:** Perform all activities in your isolated VirtualBox lab environment. Never use these techniques on systems you do not own or have explicit written authorization to test.

---
## [ENVIRONMENT NEEDED]

- **OS:** Kali Linux (primary attacker machine)
- **Target:** Metasploitable2 VM at 192.168.56.102 (or DVWA for web topics)
- **Network:** Host-Only VirtualBox network (192.168.56.0/24)
- **Tools:** Identified in topics: NSE categories auth brute default discovery exploit vuln, Lua scripting basics, smb-vuln* ftp-anon ssh-brute http-enum, db_nmap in Metasploit

### Install required tools:
```bash
sudo apt update
sudo apt install -y nmap wireshark tcpdump netcat-openbsd curl wget git python3-pip
```

---
## [STEP-BY-STEP PRACTICAL]

### Phase 1: Environment Verification

**1.** Confirm lab network is up:
```bash
ping -c 2 192.168.56.102
```
Expected: 0% packet loss. If ping fails, start Metasploitable2 VM.

**2.** Create working directory for this day:
```bash
mkdir -p ~/CEH_Labs/Week*/Day14
cd ~/CEH_Labs/Week*/Day14
```

### Phase 2: Core Practical Exercises

**3.** The main exercises for **Nmap NSE Deep Dive** follow the methodology below.

Topics covered hands-on: **NSE categories auth brute default discovery exploit vuln, Lua scripting basics, smb-vuln* ftp-anon ssh-brute http-enum, db_nmap in Metasploit**

Each tool and technique should be:
- Executed against the lab target (Metasploitable2 at 192.168.56.102)
- Or against DVWA (http://192.168.56.102/dvwa/) for web topics
- Or against your own Kali machine (127.0.0.1) for local tools

**4.** Run the primary reconnaissance/scanning/exploitation for this topic:
```bash
# Core commands for this day — refer to the topic list and notes.md
# Execute each tool against the lab target
# Document all output in ~/CEH_Labs/Week*/Day14/output.txt
```

**5.** Document findings:
```bash
# Redirect important output to a file for your report
command_output 2>&1 | tee ~/CEH_Labs/Week*/Day14/findings.txt
```

### Phase 3: Tool-Specific Exercises

**6.** For each tool identified in the topics (NSE categories auth brute default discovery exploit vuln, Lua scripting basics, smb-vuln* ftp-anon ssh-brute http-enum, db_nmap in Metasploit):
- Run with default options first
- Then apply targeted flags for the specific use case
- Save output: `tool --flags target | tee tool_output.txt`

**7.** Capture network traffic during active tool use:
```bash
sudo tcpdump -i eth1 -w day14_capture.pcap &
# Run your tools
kill %1
```

**8.** Analyze the capture:
```bash
sudo wireshark day14_capture.pcap &
```

### Phase 4: Troubleshooting

Common issues and fixes:
- **Tool not found:** `sudo apt install <toolname>`
- **Permission denied:** Prefix with `sudo`
- **Target not responding:** Verify Metasploitable2 is running, check ping
- **No output:** Add `-v` or `--verbose` flag for more detail
- **Firewall blocking:** Check `sudo ufw status` on Kali

---
## [TOOL REFERENCE]

### Primary Tools for Nmap NSE Deep Dive

```bash
# Tool syntax cheatsheet for: NSE categories auth brute default discovery exploit vuln, Lua scripting basics, smb-vuln* ftp-anon ssh-brute http-enum, db_nmap in Metasploit

# Generic usage patterns:
tool -target 192.168.56.102           # Basic usage
tool -target 192.168.56.102 -v        # Verbose
tool -target 192.168.56.102 -o output.txt  # Save output

# Nmap (used in most days):
nmap -sV -sC 192.168.56.102           # Default scripts + version
nmap -A 192.168.56.102                # Aggressive (OS+version+script)
nmap --script vuln 192.168.56.102     # Vulnerability scripts

# Save results:
command | tee output.txt              # Show and save
command > output.txt 2>&1            # Save all (including errors)
```

### Common Flags Reference

| Flag | Meaning |
|------|---------|
| `-v` / `--verbose` | Increase output detail |
| `-o <file>` | Output to file |
| `-h` / `--help` | Show help |
| `--timeout N` | Set connection timeout |
| `-t N` / `--threads N` | Parallel threads |

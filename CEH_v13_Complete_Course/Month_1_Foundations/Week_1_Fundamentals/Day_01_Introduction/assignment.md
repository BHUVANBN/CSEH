# Day 01 — Assignment: Introduction to Ethical Hacking

> **Difficulty:** Beginner
> **Estimated Time:** 1–2 hours
> **Prerequisites:** Complete notes.md and practical.md for Day 01

---

## [THEORY QUESTIONS]

Answer each question in 3–5 sentences. Write your answers below each question.

**Q1.** What is the difference between a white hat and a grey hat hacker? Is grey hat hacking legal? Justify your answer.

*Your answer:*

---

**Q2.** List and briefly explain the 5 phases of ethical hacking in the correct order. For each phase, give one example of a tool used.

*Your answer:*

---

**Q3.** Why is written authorization the single most important legal protection for an ethical hacker? What documents should be in place before any test begins?

*Your answer:*

---

**Q4.** Explain the difference between a vulnerability, a threat, a risk, and an exploit. Use a real-world analogy (e.g., a house with an unlocked window).

*Your answer:*

---

**Q5.** What distinguishes penetration testing from red teaming? In what scenarios would an organization choose red teaming over a standard pentest?

*Your answer:*

---

## [PRACTICAL TASK]

### Task: Document Your Lab Setup

**Objective:** Create a formal lab documentation file that any future team member could use to replicate your environment.

**Steps:**

1. Open a text editor in Kali Linux and create a file called `lab_setup.md`:
```bash
nano ~/lab_setup.md
```

2. Document the following information in your file:

```markdown
# Lab Environment Documentation
**Date:** [today's date]
**Kali Linux Version:** [output of: cat /etc/os-release]
**VirtualBox Version:** [output of: vboxmanage --version]

## Network Configuration
**Host-Only Network:** 192.168.56.0/24
**Kali Linux IP:** [your IP]
**Metasploitable2 IP:** [target IP]

## VM Specifications
### Kali Linux
- RAM: [amount]
- Disk: [amount]
- Network Adapters: [list]

### Metasploitable2
- RAM: [amount]
- Network Adapter: [Host-Only only]

## Connectivity Test Results
**Ping test (Kali → Metasploitable2):**
[paste output of: ping -c 4 <metasploitable2-ip>]

**Nmap ping sweep result:**
[paste output of: nmap -sn 192.168.56.0/24]

## Snapshots Taken
1. Kali-Fresh-Install — [date]
2. Lab-Ready-State — [date]
```

3. Save the file and confirm it exists:
```bash
ls -la ~/lab_setup.md
cat ~/lab_setup.md
```

**Expected Outcome:** A complete lab documentation file that proves your environment is set up and functioning correctly.

---

## [CHALLENGE]

### Research Task: Real-World CEH Professionals

**Objective:** Understand what certified ethical hackers actually do in their careers.

**Task:**
1. Go to LinkedIn.com (or any professional networking site)
2. Search for: `"Certified Ethical Hacker" OR "CEH"` in the search bar
3. Find **3 different professionals** who hold the CEH certification
4. For each person, note:
   - Their current job title
   - The industry they work in
   - How long they've been in cybersecurity
   - What other certifications they hold alongside CEH
   - What skills they list on their profile

5. Write a 1-paragraph summary comparing their roles:
   - What do their jobs have in common?
   - How do their roles differ?
   - What career path appears most common after CEH?

6. Create a file to record your findings:
```bash
nano ~/day01_challenge.md
```

**Bonus:** Find one CEH professional who has transitioned from a non-IT background (e.g., law enforcement, military, teaching). Note their transition path.

---

## [REFLECTION]

**R1.** You just learned about state-sponsored hackers. Think about the SolarWinds breach (referenced in notes.md). As an ethical hacker hired by a mid-size software company, what **3 specific recommendations** would you give them to reduce supply chain attack risk? Why did you choose those 3?

*Your answer:*

---

**R2.** The 5 phases of ethical hacking mirror what criminal hackers do. Does this mean ethical hackers are "training criminals"? How do you reconcile the dual-use nature of hacking knowledge with your responsibility as a security professional?

*Your answer:*

---

## [SELF-CHECK]

Tick each box only when you can confidently explain the concept without referring to notes:

- [ ] I can name and describe all hacker types (white, black, grey, script kiddie, hacktivist, state-sponsored, insider threat)
- [ ] I can list the 5 phases of ethical hacking in order and give an example of each
- [ ] I can explain why written authorization is legally critical
- [ ] I can distinguish between penetration testing, ethical hacking, red teaming, and vulnerability assessment
- [ ] I can explain the difference between vulnerability, threat, risk, and exploit
- [ ] My Kali Linux VM is installed and updated
- [ ] My Metasploitable2 target VM is running on Host-Only network
- [ ] I have confirmed connectivity between both VMs (ping test passed)
- [ ] I have taken snapshots of both VMs
- [ ] I have created and saved my lab documentation file

---

> **Before proceeding to Day 02:** All checkboxes should be ticked. If any practical tasks were incomplete, revisit the practical.md guide. Do not skip forward — each day builds on the previous.

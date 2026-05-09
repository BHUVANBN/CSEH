# Day 04 — Assignment: Kali Linux Mastery

> **Difficulty:** Beginner
> **Estimated Time:** 1 hour

---

## [THEORY QUESTIONS]

**Q1.** What is the purpose of the `/etc/shadow` file? Why is it separate from `/etc/passwd`?

**Q2.** What is the difference between `apt remove` and `apt purge`? When would you use each?

**Q3.** Why does Kali Linux no longer default to the root user? What security principle does this follow?

**Q4.** What is Kali NetHunter and what makes it useful for penetration testers?

**Q5.** Explain the purpose of the `/proc` filesystem. Give two examples of useful information you can find there.

---

## [PRACTICAL TASK]

Navigate the Kali filesystem and document what you find in each major directory. Create a file:
```bash
nano ~/CEH_Labs/Week1/Day04/filesystem_map.md
```

For each directory, write: what it contains and one interesting file you found there:
- `/etc`
- `/var/log`
- `/usr/share/wordlists`
- `/usr/share/nmap/scripts`
- `/opt`
- `/tmp`
- `/home`
- `/root` (requires sudo)
- `/proc`

Then customize your terminal prompt to show `[CEH-Lab] username@kali:path$` in green text.

---

## [CHALLENGE]

Write a bash script `lab_setup.sh` that:
1. Creates the full Week 1–4 folder structure under `~/CEH_Labs/`
2. Creates a `README.md` in each week folder with the week's topics
3. Creates a `tools_needed.md` in each day folder
4. Prints a success message with the total number of directories created
5. Is idempotent (running it twice does not break anything — use `-p` flag)

---

## [REFLECTION]

**R1.** You are on a pentest and gain shell access to a Linux server. Which directories would you check first, and why? (Think: credentials, logs, configurations, user data)

**R2.** Why do attackers often write their tools and payloads to `/tmp`? What defensive measure can a sysadmin implement to make `/tmp` less useful to attackers?

---

## [SELF-CHECK]

- [ ] I know what lives in /etc, /var, /opt, /usr, /tmp, /proc
- [ ] I can install, remove, and search for packages with apt
- [ ] I have created my CEH_Labs folder structure
- [ ] I customized my terminal prompt in ~/.bashrc
- [ ] I can list processes with ps aux and kill them with kill/killall
- [ ] I know the difference between ifconfig and ip addr
- [ ] I understand why Kali runs as non-root by default
- [ ] I completed the filesystem_map.md documentation

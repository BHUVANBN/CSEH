# Day 03 — Practical: Demonstrating Integrity & Confidentiality

> **Time Estimate:** 1–1.5 hours
> **⚠️ Safety Warning:** All commands run on your local Kali Linux VM. No network activity required. Safe to run in any environment.

---

## [ENVIRONMENT NEEDED]

- **OS:** Kali Linux
- **Tools:** `md5sum`, `sha256sum`, `openssl` (all pre-installed on Kali)
- **No additional installs needed**

---

## [STEP-BY-STEP PRACTICAL]

### Part 1: Demonstrating Integrity with Hashing

**1.** Open terminal and create a working directory:
```bash
mkdir -p ~/CEH_Labs/Week1/Day03
cd ~/CEH_Labs/Week1/Day03
```

**2.** Create a test file:
```bash
echo "This is my original secret configuration file." > config.txt
cat config.txt
```
Expected output: `This is my original secret configuration file.`

**3.** Generate MD5 hash of the original file:
```bash
md5sum config.txt
```
Expected output: `e3b0c44...  config.txt` (a 32-character hex string)
Record this hash — it's the "baseline" fingerprint.

**4.** Generate SHA-256 hash (stronger):
```bash
sha256sum config.txt
```
Expected output: A 64-character hex string. SHA-256 is the industry standard; MD5 is deprecated for security use.

**5.** Now MODIFY the file (simulate tampering):
```bash
echo "TAMPERED LINE ADDED BY ATTACKER" >> config.txt
cat config.txt
```

**6.** Re-hash the file and COMPARE:
```bash
md5sum config.txt
sha256sum config.txt
```
Expected output: COMPLETELY DIFFERENT hashes — even adding one character changes the entire hash.

This is the fundamental property of cryptographic hash functions: **avalanche effect** — small input change = completely different output.

**7.** Automate integrity checking with a script:
```bash
nano integrity_check.sh
```
```bash
#!/bin/bash
EXPECTED_HASH="PASTE_YOUR_ORIGINAL_SHA256_HERE"
CURRENT_HASH=$(sha256sum config.txt | awk '{print $1}')

if [ "$EXPECTED_HASH" == "$CURRENT_HASH" ]; then
    echo "[OK] File integrity verified — no tampering detected."
else
    echo "[ALERT] File has been MODIFIED! Possible tampering!"
fi
```
```bash
chmod +x integrity_check.sh
./integrity_check.sh
```

[SCREENSHOT: Terminal showing different hashes before and after file modification]

---

### Part 2: Demonstrating Confidentiality with OpenSSL Encryption

**8.** Create a plaintext "sensitive" file:
```bash
echo "CONFIDENTIAL: Server admin password is P@ssw0rd123!" > plaintext.txt
cat plaintext.txt
```

**9.** Encrypt it using AES-256-CBC:
```bash
openssl enc -aes-256-cbc -pbkdf2 -in plaintext.txt -out encrypted.bin
```
You will be prompted for a password — remember this password.

**10.** Verify the encrypted file is unreadable:
```bash
cat encrypted.bin
```
Expected output: Binary garbage — completely unreadable without the key.

**11.** Decrypt it:
```bash
openssl enc -d -aes-256-cbc -pbkdf2 -in encrypted.bin -out decrypted.txt
cat decrypted.txt
```
Expected output: `CONFIDENTIAL: Server admin password is P@ssw0rd123!`

[SCREENSHOT: Terminal showing original, encrypted (unreadable), and decrypted content]

**12.** Try decrypting with the WRONG password:
```bash
openssl enc -d -aes-256-cbc -pbkdf2 -in encrypted.bin -out wrong_decrypt.txt
```
Enter a wrong password when prompted.
Expected output: `bad decrypt` error — the wrong key cannot decrypt the data.

---

### Part 3: Hash a Download to Verify Integrity (Real-World Use)

**13.** Download a small file and verify its integrity:
```bash
# Download a tool with known hash (example: busybox)
wget https://busybox.net/downloads/busybox-1.36.0.tar.bz2 -O busybox.tar.bz2
```

**14.** Compute its SHA-256:
```bash
sha256sum busybox.tar.bz2
```

**15.** Compare with the official SHA-256 listed on the website. If they match, the download was not tampered with in transit. This is how Kali Linux verifies ISO downloads.

---

## [TOOL REFERENCE]

### Hash Commands Cheatsheet

```bash
md5sum <file>                    # Generate MD5 hash (deprecated for security)
sha256sum <file>                 # Generate SHA-256 hash (recommended)
sha512sum <file>                 # Generate SHA-512 hash (strongest standard)
sha256sum -c <checksum_file>     # Verify multiple files against stored hashes
echo -n "text" | sha256sum       # Hash a string (not a file)
```

### OpenSSL Encryption Cheatsheet

```bash
# Encrypt (AES-256-CBC, modern PBKDF2 key derivation)
openssl enc -aes-256-cbc -pbkdf2 -in plaintext.txt -out encrypted.bin

# Decrypt
openssl enc -d -aes-256-cbc -pbkdf2 -in encrypted.bin -out decrypted.txt

# Other cipher options:
openssl enc -aes-128-cbc ...     # 128-bit AES
openssl enc -des3 ...            # Triple DES (legacy, weak)
openssl enc -chacha20 ...        # ChaCha20 (modern stream cipher)

# List all available ciphers:
openssl enc -list
```

### Common OpenSSL Flags

| Flag | Meaning |
|------|---------|
| `-in <file>` | Input file |
| `-out <file>` | Output file |
| `-pbkdf2` | Modern key derivation (required for security) |
| `-iter 100000` | Increase key derivation iterations |
| `-d` | Decrypt mode |
| `-k <password>` | Specify password in command (insecure on shared systems) |

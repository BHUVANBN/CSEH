# Day 05 — Assignment: OSI Model & Protocol Analysis

> **Difficulty:** Beginner
> **Estimated Time:** 1.5 hours

---

## [THEORY QUESTIONS]

**Q1.** Draw the OSI model from memory (all 7 layers, top to bottom) and list at least 2 protocols for each layer.

**Q2.** Explain the TCP 3-way handshake step by step. What flag does each packet carry? What is a SYN flood attack and how does it exploit this process?

**Q3.** DNS uses both TCP and UDP on port 53. When does it use each, and why?

**Q4.** What is the difference between a hub and a switch at the OSI layer level? Why are hubs a security risk on modern networks?

**Q5.** Port 443 is HTTPS. At which OSI layer does the TLS encryption operate? What does "HTTPS" encrypt and what does it NOT encrypt?

---

## [PRACTICAL TASK]

**Capture a DNS query in Wireshark and document it:**

```bash
sudo wireshark &
```

1. Start capture on eth0
2. Open terminal, run: `nslookup google.com 8.8.8.8`
3. Stop capture
4. Filter: `dns`
5. Click on the DNS query packet
6. In the packet details, identify and screenshot:
   - Frame (Layer 2 header)
   - IP header (Layer 3: source/dest IP)
   - UDP header (Layer 4: source/dest port)
   - DNS payload (Layer 7: query name, type, response)

Document your findings in:
```bash
nano ~/CEH_Labs/Week2/Day05/dns_analysis.md
```

---

## [CHALLENGE]

Use Wireshark to capture a complete HTTP session (not HTTPS) to an HTTP-only test site. Use `http://neverssl.com` which intentionally serves over HTTP.

1. Capture the traffic
2. Follow the TCP stream (right-click packet → Follow → TCP Stream)
3. Document the raw HTTP request headers and response headers
4. Identify: Request method, URL, HTTP version, Server header, Content-Type
5. Explain: Why could an attacker on the same network intercept this data? What OSI layer does this attack occur at?

---

## [REFLECTION]

**R1.** ARP operates at Layer 2 and maps IP addresses to MAC addresses. Why does this matter for security? What attack uses ARP to intercept traffic, and what layer does that attack occur at?

**R2.** Modern firewalls operate at Layer 3 and Layer 4. Next-generation firewalls (NGFW) operate up to Layer 7. What additional attacks can an NGFW detect that a traditional firewall cannot?

---

## [SELF-CHECK]

- [ ] I can name all 7 OSI layers in order (both top-down and bottom-up)
- [ ] I know the PDU name for each layer (bit, frame, packet, segment, data)
- [ ] I know the common port numbers table (at least 15 ports)
- [ ] I understand TCP vs UDP differences and when each is used
- [ ] I can explain the TCP 3-way handshake from memory
- [ ] I captured and analyzed traffic with tcpdump
- [ ] I opened a capture file in Wireshark and applied display filters
- [ ] I completed the DNS packet analysis task

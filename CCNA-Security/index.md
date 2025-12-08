---
title: CCNA Security / Network Defense Capstone
---

# CCNA Security / Network Defense Fundamentals – Capstone

This page pulls together my work from **CYBR-2102 – Network Defense Fundamentals**.  
The course focused on three main areas:

- Designing a **defense-in-depth network** in Packet Tracer  
- Performing **packet capture and threat analysis** in Wireshark  
- Building a full **incident response plan** mapped to NIST SP 800-61  

---

## Course Outcomes

By the end of the class I could:

- Design a segmented network with **external, DMZ, and internal zones**
- Write and verify **Cisco IOS ACLs** that enforce least privilege between zones
- Capture and analyze traffic with **Wireshark**, including ping sweeps, port scans, and DoS-style floods
- Document findings in **traffic analysis reports** and map them to CIS / NIST controls
- Write a full **incident response plan** for a brute-force RDP attack with exfiltration attempts

---

## Milestone 1 – Defense-in-Depth Network Design

**Goal:** Build a small enterprise-style network in Packet Tracer and show how layered controls protect the environment.

**Key elements**

- Three security zones: **External → Firewall → DMZ → Internal LAN**
- Subnets:
  - DMZ: `192.168.10.0/24`
  - Internal: `192.168.20.0/24`
- ACLs on the firewall interface to:
  - Allow **HTTP** into the DMZ web server
  - Deny direct DMZ ↔ Internal access
  - Restrict admin access to specific management hosts
- Local firewalls enabled on **PC-Admin** and **FileServer**
- Access-control matrix defining what each role (Admin, IT Support, User) can and cannot do

**What this shows**

This milestone demonstrates that I can design and justify a **layered security architecture** instead of relying on a single firewall rule. Each layer (perimeter, network, host, application, data) has a specific control and a test to prove it works.

**Artifact (PDF):**  
[Milestone 1 — Defense-in-Depth Diagram & Access Policy](/CCNA-Security/Milestone1-DefenseInDepth.pdf)

> Update the link path/filename above if your PDF is named differently.

---

## Milestone 2 – Traffic Analysis Report (Wireshark)

**Goal:** Capture live traffic and identify attacker behaviors from packet data.

**Capture details**

- Tool: **Wireshark**
- Duration: ~3–5 minutes of traffic
- Protocols observed: **ICMP, TCP, DNS, ARP, TLS**
- Top events:
  - ICMP ping sweep across a large IP range
  - TCP SYN scan against ports `1–20` on the gateway
  - High-rate ICMP with large payloads (DoS-style behavior)

**Analysis highlights**

- Used Wireshark display filters such as:
  - `icmp`
  - `tcp.flags.syn == 1 and tcp.flags.ack == 0`
- Classified all three behaviors as **true positives** (intentionally generated in the lab)
- Mapped defensive actions to industry controls:
  - Rate-limit ICMP and restrict scanning attempts
  - Tune IDS/IPS for ping sweeps, SYN scans, and ICMP anomalies
  - Keep systems and firewall firmware patched and up to date

**What this shows**

This milestone proves I can move from **raw packets → detection → actionable recommendations**, which is exactly what a junior SOC analyst or network defender is expected to do.

**Artifact (PDF):**  
[Milestone 2 – Traffic Analysis Report](/CCNA-Security/Holden_CYBR2102_M2.pdf)

---

## Milestone 3 – Incident Response Plan

**Scenario**

“Unauthorized RDP brute-force and data exfiltration attempt” detected via Windows Security Logs (Event ID **4625** failures) on an internal system.

The report walks through the full **NIST SP 800-61** incident lifecycle:

1. **Preparation**
   - Logging enabled, IR roles defined, host firewall active  
   - Baseline documentation in place

2. **Detection & Analysis**
   - SOC tool flags repeated 4625 failures from a single source IP  
   - Analyst confirms failed RDP attempts and unusual outbound activity

3. **Containment**
   - Disabled the compromised account  
   - Blocked the attacker IP at the firewall  
   - Stopped outbound transfer attempts

4. **Eradication**
   - Ran anti-malware scans  
   - Removed suspicious artifacts and verified the system was clean

5. **Recovery**
   - Restored affected files from backup  
   - Monitored closely for new login attempts before returning to normal operations

6. **Post-Incident Activity**
   - Root cause: exposed RDP and weak authentication / lockout settings  
   - Recommendations:
     - Require **MFA** and RDP via VPN only
     - Enforce account lockout after 3–5 failed attempts
     - Restrict RDP to internal/trusted IPs
     - Keep RDP and OS patches current
     - Improve user awareness around suspicious login alerts

**What this shows**

This milestone ties together **network defense + Windows security + backup** into a coherent **incident response playbook**, showing how I would handle a real brute-force attack from detection through lessons learned.

**Artifact (PDF):**  
[Milestone 3 – Incident Response Plan](/CCNA-Security/Holden_CYBR2102_M3.pdf)

---

## Labs and Supporting Work

In addition to the milestones, I completed six Cisco / Packet Tracer labs covering:

- Basic router and switch setup with secure management access  
- VLANs and inter-VLAN routing  
- Standard and extended ACLs  
- VPN and secure remote-access configurations  
- Device hardening and login/banner protections  
- Final review lab tying routing, switching, and security together

(Individual lab PDFs are stored in this folder and can be linked or downloaded as needed.)

---

## How This Maps to Real Work

Together, these milestones and labs show my progression from:

1. **Designing** a secure network (defense-in-depth)  
2. **Detecting & analyzing** hostile traffic in Wireshark  
3. **Responding** to an incident using NIST 800-61 and CIS-style controls  

This is the same pipeline used in real SOC / network-defense roles:  
**design → monitor → respond → improve**.

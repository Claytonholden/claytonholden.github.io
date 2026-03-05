# Topic 01 Notes — Wireshark Foundations & Host Identification

## Core Skill: How to Start Any PCAP

When opening a PCAP, I do NOT scroll through packets first.

My workflow:

1. Protocol Hierarchy  
   - `Statistics → Protocol Hierarchy`
   - What dominates? TCP? UDP? TLS? DNS?

2. Endpoints  
   - `Statistics → Endpoints`
   - Identify top talker (likely primary host)

3. Conversations  
   - `Statistics → Conversations`
   - Who is communicating most?

Only after this do I look at individual packets.

---

## Identifying Hosts & Devices

### Windows Indicators
- NBNS / LLMNR traffic
- Hostnames like `DESKTOP-XXXX`
- SMB traffic
- Kerberos / LDAP in domain environments

### macOS / iOS Indicators
- mDNS (.local names)
- Bonjour service discovery
- Apple vendor MAC addresses

### Linux Indicators
- SSH presence
- Linux user-agent strings
- Absence of Windows name resolution protocols

---

## Useful tshark Commands

Protocol hierarchy:
`tshark -r file.pcap -q -z io,phs`

Top IP endpoints:
`tshark -r file.pcap -q -z endpoints,ip`

DHCP hostname extraction:
`tshark -r file.pcap -Y dhcp -T fields -e bootp.option.hostname`

NBNS names:
`tshark -r file.pcap -Y nbns -T fields -e nbns.name`

---

## Key Lesson

Traffic analysis is not guessing the OS.  
It’s correlating multiple small indicators until the conclusion is supported.

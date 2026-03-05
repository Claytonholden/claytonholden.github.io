# Topic 02 Notes — Filtering & Baseline Analysis

## Core Skill: Establishing “Normal”

Before calling anything suspicious, I ask:

- What protocols are always present?
- What hosts consistently communicate?
- What does regular DNS activity look like?

---

## My Baseline Workflow

1. Observe traffic with NO filters.
2. Apply 3 filters per PCAP:
   - Host focus: `ip.addr == x.x.x.x`
   - Core protocol: `dns`, `tls`, `http`
   - Environment-specific: `nbns || llmnr`, `imap`, `ftp`

3. Compare patterns across captures.

---

## Recognizing Normal Patterns

- DNS appears in almost every capture.
- TLS dominates modern traffic.
- Windows networks are chatty (NBNS, LLMNR).
- Domain environments show LDAP + Kerberos + SMB.

---

## Why Baselines Matter

Without a baseline:
- All traffic looks suspicious.
- Analysts over-escalate.

With a baseline:
- Only deviations stand out.

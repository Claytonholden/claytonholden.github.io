# Topic 1 — Recon, Scanning & Vulnerability Analysis

## Core workflow
- Scope / ROE
- Passive recon (DNS/WHOIS/subdomains)
- Active recon (Nmap strategy)
- Service enumeration + validation
- Vulnerability research (CVE → CWE → NVD → CVSS)
- Reporting: risk + evidence + mitigations + verification steps

## Nmap templates
- `nmap -sV --top-ports 1000 <target>`
- `nmap -p- -sV <target>`
- `nmap -sC -sV <target>`
- `nmap -sV --script vulners --script-args mincvss=4 <target>`

## CVE/CWE/NVD/CVSS relationship
- CVE = specific vuln ID
- CWE = weakness category
- NVD = database w/ enrichment + scoring
- CVSS = severity score + vector

## Portfolio bullets
- Built a repeatable recon → scan → research workflow and documented results clearly.
- Can explain severity and prioritization using CVSS and mitigations.

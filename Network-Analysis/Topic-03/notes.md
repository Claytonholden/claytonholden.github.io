# Topic 03 Notes — Anomalies & Attack Traffic

## Core Skill: Compare Against Baseline

An anomaly is:
Something that deviates from normal traffic patterns.

It is NOT automatically malware.

---

## Indicators I Look For

### Suspicious HTTP
- Cleartext `.exe` downloads
- Repeated POST requests to scripts
- Unfamiliar domains with high query counts

### Beaconing Behavior
- Repeated connections to same external IP
- Consistent byte sizes
- Regular timing intervals
- Non-standard ports (2222, 8080)

### Suspicious DNS
- High frequency of obscure domains
- Randomized domain patterns

### Legacy Protocol Misuse
- FTP uploads
- IRC in modern networks
- Telnet traffic

---

## Monitoring with Statistics

Instead of packet-by-packet:

- Protocol hierarchy → What dominates?
- Endpoints → Who dominates?
- Conversations → Who repeats?
- Port frequency → What services are hit?

Automation leaves patterns.  
Patterns are detectable statistically.

---

## Key Lesson

Unusual ≠ malicious.  
Suspicious + repeated + context = escalation.

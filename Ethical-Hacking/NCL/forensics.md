# NCL — Forensics Playbook

## Common tasks I saw
- Magic bytes / file signatures
- Corrupted headers (jpg vs png)
- Browser artifacts (Firefox sqlite history)
- PCAP evidence extraction

## Magic bytes: JPEG vs PNG
- JPEG starts with: FF D8 FF ...
- PNG starts with: 89 50 4E 47 0D 0A 1A 0A

### Recovery workflow
1) Identify mismatch: extension vs file header
2) Run `xxd` or `file` to confirm type
3) Fix header bytes with a hex editor
4) Ensure correct chunk structure (PNG often needs correct bytes following signature)
5) Rename extension and open

## Browser sqlite (Firefox)
- Look at tables like `moz_places`, `moz_historyvisits`
- Join visits to URLs to build timeline

## Tools
- `file`, `xxd`, hex editors
- sqlitebrowser / sqlite3
- Wireshark / tshark (when PCAP-based)

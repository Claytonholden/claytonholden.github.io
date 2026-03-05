# NCL — Port Scanning Playbook

## Goal
Answer:
- lowest open TCP ports (1st/2nd/3rd)
- lowest open UDP port
- identify software on a specific port (e.g., 16080)

## Workflow
1) TCP scan
   - `nmap -sS -p- --min-rate 1000 <target>`
2) Service detection on discovered ports
   - `nmap -sV -p <ports> <target>`
3) UDP scan (targeted)
   - `nmap -sU --top-ports 200 <target>`
4) Verify app services (if HTTP-like)
   - `curl -I http://<target>:<port>`
   - `whatweb http://<target>:<port>` (optional)

## Notes
- UDP often appears open|filtered — be careful and verify.
- For “software on port X” always back it up with -sV and a manual check (curl/banner).

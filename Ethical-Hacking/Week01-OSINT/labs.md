# Week 01 Labs

## Ports.cityinthe.cloud

### Objective
Identify open TCP and UDP ports.

### Tools Used
- nmap
- service detection

### Key Commands
nmap -sS -p- ports.cityinthe.cloud
nmap -sV -p16080 ports.cityinthe.cloud
nmap -sU --top-ports 200 ports.cityinthe.cloud

### Lessons Learned
- Always scan all ports
- UDP scanning is slower
- Service detection reveals version info

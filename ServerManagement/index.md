---
layout: default
title: Server Management (NET-2220)
---

# Server Management (NET-2220)
**Fall 2025 — Clayton Holden**  
**Capstone Summary • Windows Server Lifecycle Management**

This course focused on the complete lifecycle of deploying, securing, maintaining, backing up, and monitoring a Windows Server 2022 environment.  
My final environment consisted of a fully configured domain controller (**SERVER3**) running in a virtualized lab, hardened to CIS Level 1 standards, backed up daily, and monitored through an automated PowerShell health-check system.

This page summarizes the **three major phases** of the project (Milestones 1–3), with links to their detailed reports and lab documentation.

---

# 🧩 **Milestone 1 — Deployment & Directory Configuration**
[View Milestone 1 PDF](Deployment-Directory/Milestone1_DeploymentDirectory.pdf)

Milestone 1 established the core Active Directory environment.  
Key completed tasks included:

- Deployment of **Windows Server 2022** on VirtualBox  
- Configuration of hostname (**SERVER3**) and networking (DHCP-based lab config)  
- Installation of **Active Directory Domain Services (AD DS)**  
- Creation of **corp.local** forest and domain controller promotion  
- Organizational Unit structure: *Users* and *Groups*  
- Identity objects created:  
  - User: **jsmith**  
  - Group: **ITAdmins**  
- Verification of domain login and group membership (ADUC screenshots confirmed this)  

> According to Milestone 1, SERVER3 was fully deployed and validated with AD DS, user/group creation, and baseline structure functional (pages 1–3). 

You can view the work for this phase inside:

- [`Deployment-Directory/`](Deployment-Directory/index.md)

---

# 🔐 **Milestone 2 — Security Hardening & Patch Management**
[View Milestone 2 PDF](Hardening-Patching/Milestone2_HardeningPatching.pdf)

This milestone focused on applying CIS-style controls and validating patch compliance.  
Security tasks included:

### **Password & Lockout Policies (CIS Level 1)**
- Minimum length: **12 characters**  
- Password history: **24**  
- Maximum age: **60 days**  
- Account lockout threshold: **5 attempts**  
- Lockout duration/reset window: **15 minutes**

### **Firewall Hardening**
- All profiles (Domain, Private, Public) **enabled**  
- Inbound RDP restricted to local subnet only  
- Custom **Block All Inbound** rule applied  

### **Service Hardening**
The following insecure/unnecessary services were disabled:
- **RemoteRegistry**  
- **Telnet (TlntSvr)**  
- **Print Spooler**  

### **Patch Validation**
PowerShell was used to verify cumulative updates and hotfixes:
Get-HotFix | Sort-Object InstalledOn -Descending | Select-Object -First 10
systeminfo | Select-String "KB"

Event Viewer logs and KB output confirmed the server was fully patched as of December 2025.

> Screenshots in Milestone 2 show password policy, firewall rules, disabled services, update history, HotFix output, and audit policy configuration (pages 1–7). 

View all hardening work inside:

- [`Hardening-Patching/`](Hardening-Patching/index.md)

---

# 💾 **Milestone 3 — Backup & Automation Implementation**
[View Milestone 3 PDF](Backup-Automation/Milestone3_BackupAutomation.pdf)

This phase added backup reliability and operational monitoring.

### **Backup Configuration**
- Windows Server Backup installed  
- Daily **full server backup** scheduled at **02:00 AM**  
- Backups written to dedicated disk: **E:\Backups**  
- Validation performed through:  
  - *Microsoft-Windows-Backup/Operational* Event Viewer logs  
  - `wbadmin get versions`  
  - Backup catalog inspection  

### **Automation & Monitoring**
A PowerShell script (`ServerMonitor.ps1`) was created to generate a daily report including:

- Services not running  
- Last 20 system log events  
- Top 10 CPU-consuming processes  

Task Scheduler runs it daily at **08:00 AM**, writing logs to:
C:\Scripts\Monitoring\Logs\Status_<timestamp>.txt

> Milestone 3 validation confirmed successful backups, version catalog entries, clean log output, and functional automation (pages 1–7). 

View all backup + automation work inside:

- [`Backup-Automation/`](Backup-Automation/index.md)

---

# 🏁 **Capstone Outcome**

Across the three milestones, SERVER3 now demonstrates:

### ✔ Full deployment of an enterprise-style domain controller  
### ✔ Hardened configuration aligned to CIS 2022 Level 1  
### ✔ Verified patch compliance  
### ✔ Daily backup + recoverable backup catalog  
### ✔ Automated server monitoring + report generation  
### ✔ Professional documentation using ITIL-style change records  

This represents a complete lifecycle for Windows Server management:
**Build → Secure → Patch → Backup → Monitor → Document.**

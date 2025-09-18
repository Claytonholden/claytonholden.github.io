# Rules of Engagement (Week 5)

## My First-Hour Priorities
- Define a clear **scope** that limits testing to approved systems and accounts only.  
- Require **explicit written authorization** from the CIO and instructor before any activity begins.  
- Avoid any collection of personal data or systems outside the approved sandbox, because that would cross both policy and ethical boundaries.  

## ROE Outline (Final)
### Purpose & Approvals
- Purpose: To safely conduct penetration testing on the class sandbox network without disrupting production systems.  
- Approvals: CIO and course instructor must sign before testing begins.  

### Scope & Authorization
- In-scope: Sandbox network, designated test hosts, and instructor-provided accounts.  
- Out-of-scope: Mock student or college data in the sandbox and all production systems.  
- Authorization: No testing occurs without written approval.  

### Timing & Deconfliction
- Testing is allowed only during scheduled class hours unless otherwise approved.  
- No tests during maintenance freezes or backups.  
- Teams must coordinate to avoid overlapping disruptive tests.  

### Communications & Escalation
- Real-time contacts: Instructor (Incident Manager) and IT Help Desk (sandbox custodian).  
- Notify at least 24 hours before testing and confirm again 1 hour before start.  
- Stop-test conditions: halt immediately if out-of-scope data, service outages, or signs of real user data are detected.  

### Data Handling
- Collect only minimum necessary evidence (short log snippets, service banners).  
- No capture of credentials, tokens, or mock student/college data.  
- Evidence stored in restricted `/evidence/` location with SHA-256 hashes recorded.  
- Retain for 14 days unless extended; then securely deleted.  
- Apply redaction for any accidental capture of sensitive data.  

### Reporting & Handoff
- Draft report within 48 hours, final report within 7 days.  
- Report includes purpose, scope, actions, evidence IDs/hashes, and recommended fixes.  
- Remediation handoff goes to sandbox custodian and instructor.  

## Integrity & Privacy Controls
Evidence is hashed with SHA-256 at collection time and logged in the chain of custody. All artifacts are stored in a restricted evidence directory with IR-team-only access. Logs are reviewed for redaction to remove any mock student or personal data before sharing. Retention is limited to 14 days unless extended by written approval, after which secure deletion is confirmed.  

## Evidence Links
- [Week 5 ROE Outline (PDF)](/CYBR2100_ROE_Outline_W05_HoldenClayton.pdf)  
- [Week 5 Reflection (PDF)](/CYBR2100_Reflection_W05_HoldenClayton.pdf)  

## Reflection
Next time I would make the escalation and stop-test conditions even clearer, with more concrete examples to remove judgment calls. I would also add more detail on who enforces the ROE if someone violates the terms. The main stakeholders are the testers, the instructor, and IT Security. Clear rules help keep trust while making sure testing is useful but safe.  

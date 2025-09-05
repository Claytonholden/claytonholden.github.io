# OSS & Disclosure Readiness (Week 3)

## License Choice
For a small internal tool, I would choose the MIT license. It is the simplest of the common licenses and only requires attribution by including the copyright and license text. Unlike GPL, it does not impose copyleft obligations if the tool is shared, and unlike Apache 2.0 it does not add NOTICE or patent terms. This makes it lightweight, highly compatible, and easy to adopt in both internal and external settings.

## Initial Vulnerability Report Template
**Reporter Contact:** [Name / role / email placeholder]  
**Affected Product/Version/Environment:** [Identify system, version, OS or environment]  
**Reproducible Summary:** Short description of the issue and how it was observed (no exploit steps, no credentials).  
**Impact/Suggested Severity:** Outline of what could happen if the issue is left unpatched.  
**Mitigation/Workaround (if known):** Any temporary fixes or containment strategies.  
**Coordination Timeline:** Suggested disclosure timeline (e.g., 90 days, adjustable if exploitation is active).  

## Justification
The MIT license was chosen because it balances flexibility with clear attribution requirements. According to *Choose a License* (https://choosealicense.com/), MIT is one of the most permissive licenses, making it easy to adopt and integrate. For the disclosure side, the CISA guidance on Vulnerability Disclosure Programs emphasizes safe initial reports that exclude exploit details and focus on scope, impact, and coordination timelines, which is reflected in the template above.

## Evidence Links
- [Week 3 Case Brief (PDF)](/files/CYBR2100_CaseBrief_W03_HoldenClayton.pdf)  
- [Week 3 Reflection (PDF)](/files/CYBR2100_Reflection_W03_HoldenClayton.pdf)  

## Reflection
If I improved this page, I would refine the vulnerability report template by adding clearer instructions for severity rating and impact categories. I would also expand on how communication between the researcher and vendor should be handled. The main stakeholders are developers, security researchers, and end users. A good process protects users from risk while giving vendors a fair chance to fix issues responsibly.

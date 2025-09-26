# AI Ethics Controls Plan (Week 7)

## Policy Snippet (Final)
We use AI tools in security operations to catch suspicious logins, phishing emails, and other alerts faster than a person could on their own. These tools don’t replace people—they highlight unusual activity and give reasons in plain language so users and analysts know why something was flagged. A human analyst always reviews serious alerts and can override the AI if it gets it wrong.  

If someone feels an alert was a mistake, they can appeal through the IT help desk. Appeals are reviewed within 24 hours and resolved within five business days. The AI only looks at the data it needs, like login times or email headers, not the full content of personal emails. Evidence is kept for 90 days, and sensitive details are masked.  

We measure how accurate the alerts are, track false positives, and review appeals. The models are retrained every six months and checked quarterly to keep them fair and reliable.  

## Controls & Metrics
- **Human-in-the-loop review** — all high-risk alerts require analyst review before action.  
  - *Metric:* ≥ 95% of escalated alerts are reviewed by a human within 4 hours.  
- **Appeals system** — users can contest AI flags with IT Security.  
  - *Metric:* 100% of appeals acknowledged within 24 hours; resolved in ≤ 5 business days.  
- **Minimum necessary data** — AI only processes metadata (headers, login times), not full content.  
  - *Metric:* Quarterly data audits show 0 instances of content-level collection.  
- **Model accuracy checks** — subgroup testing to detect bias or drift.  
  - *Metric:* False positive rate ≤ 5%; subgroup variance ≤ 2% between user groups.  
- **Retraining and review cadence** — models retrained every 6 months; performance reviewed quarterly.  
  - *Metric:* Quarterly report published by IT Security with accuracy, FP/FN rates, and appeals stats.  

## Justification
These controls fit the main risks of bias and false positives that we discussed in class and in Chapter 11 of *Ethics in Technology*. Bias is managed with subgroup testing, while false positives are controlled by human review and user appeals. Minimum necessary data protects privacy, and clear metrics with regular review keep the system accountable and transparent. Together, these controls make AI tools useful without letting them run unchecked.  

## Evidence Links
- Microsoft. (2023). [Security Copilot – What’s new](https://learn.microsoft.com/en-us/copilot/security/whats-new-copilot-security?utm_source=chatgpt.com)  
- CISA. (2025). [AI Data Security Best Practices](https://www.cisa.gov/resources-tools/resources/ai-data-security-best-practices-securing-data-used-train-operate-ai-systems?utm_source=chatgpt.com)  
- Schmitt, C., & Flechais, I. (2023). *Digital Deception: Generative AI in Social Engineering and Phishing.* [arXiv](https://arxiv.org/abs/2310.13715?utm_source=chatgpt.com)  

## Reflection
If I did this again, I would refine the appeals system so it is easier for users to track the status of their requests. Right now, the window is clear, but the process could feel like a black box. Another trade-off is scope—limiting data to metadata protects privacy, but it also might cause us to miss some real threats. Finding the right balance between privacy and thorough detection is the part I would want to revisit next time.  

## AI Use Note
I used ChatGPT as a structured writing partner. I provided my lecture notes and the assignment requirements, then asked the tool to guide me step by step with targeted questions. This let me organize my thoughts more effectively while keeping the final writing in my own words. I see AI as a professional support tool — I controlled the content and direction, but used ChatGPT to make the process faster, clearer, and more organized.

# Investigation Timeline

**Incident ID:** IR-001  
**Incident Type:** Phishing Email with Malware Delivery  
**Date Investigated:** 10 July 2026  
**Analyst:** Thanvik S

| Time | Event |
|------|-------|
| 09:58 UTC | Suspicious email received by the organization. |
| 10:00 UTC | Email flagged for investigation due to suspicious financial content. |
| 10:05 UTC | Email headers analyzed to verify sender authenticity. |
| 10:10 UTC | SPF result identified as **SoftFail**. |
| 10:12 UTC | DKIM verification failed. |
| 10:15 UTC | Malicious URL extracted from the email body. |
| 10:20 UTC | URL identified as a direct download for `install.exe`. |
| 10:25 UTC | Indicators of Compromise (IOCs) documented. |
| 10:30 UTC | MITRE ATT&CK techniques mapped. |
| 10:35 UTC | Incident report completed and recommendations documented. |

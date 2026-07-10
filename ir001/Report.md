# Incident Investigation Report

## Incident Information

| Field | Value |
|------|------|
| Incident ID | IR-001 |
| Incident Name | PhishStrike |
| Category | Phishing |
| Severity | High |
| Status | Closed |
| Analyst | Thanvik S |
| Framework | NIST SP 800-61 |

---

# Executive Summary

A phishing email impersonating a legitimate university employee was investigated after being reported as suspicious. The email attempted to convince recipients that a purchase worth **625,000 pesos** had been processed and instructed them to download an invoice.

Technical analysis revealed that the email failed authentication checks, contained a direct download link to a malicious executable (`install.exe`), and displayed multiple indicators commonly associated with phishing and malware delivery campaigns.

No evidence was found indicating that the malicious executable had been executed during the investigation.

---

# Incident Details

## Subject

COMMERCIAL PURCHASE RECEIPT ONLINE 27 NOV

## Sender

erikajohana.lopez@uptc.edu.co

## Recipient

Undisclosed Recipients

## Email Theme

Fake commercial purchase receipt requesting the recipient to download an invoice.

---

# Detection

The incident was detected after a suspicious email containing an unexpected purchase notification was received.

The message attempted to create urgency by claiming that a payment of **625,000 pesos** had been processed and instructed the recipient to open an invoice using an access code.

---

# Scope

Affected Asset

- Email System

Affected Users

- Multiple recipients

Affected Platform

- Microsoft Outlook

---

# Technical Investigation

## Email Header Analysis

Authentication Results

| Test | Result |
|------|--------|
| SPF | SoftFail |
| DKIM | Fail |
| DMARC | None |

These results indicate that the sender could not be successfully authenticated and may have been impersonated.

---

## Malicious Link Analysis

The email contained the following download URL:

http://107.175.247.199/loader/install.exe

Observations

- Direct IP address used instead of a domain name.
- Download points to an executable file.
- Executable likely intended to deliver malware after user interaction.

---

# Indicators of Compromise

| IOC Type | Value |
|----------|-------|
| Sender Email | erikajohana.lopez@uptc.edu.co |
| Subject | COMMERCIAL PURCHASE RECEIPT ONLINE 27 NOV |
| Malicious IP | 107.175.247.199 |
| SMTP IP | 18.208.22.104 |
| URL | http://107.175.247.199/loader/install.exe |
| File | install.exe |

---

# MITRE ATT&CK Mapping

| Technique | ID |
|-----------|------|
| Phishing | T1566 |
| User Execution | T1204 |
| Malicious File | T1204.002 |
| Ingress Tool Transfer | T1105 |

---

# Root Cause

The attacker abused social engineering techniques by impersonating a trusted educational institution.

Recipients were encouraged to download an executable disguised as an invoice. Weak email authentication (SPF SoftFail and DKIM Fail) increased the likelihood of successful spoofing.

---

# Containment

The following containment actions are recommended:

- Block the sender email.
- Block IP address 107.175.247.199.
- Block the malicious URL.
- Quarantine similar emails.
- Reset credentials if user interaction occurred.

---

# Recommendations

1. Enable strict DMARC enforcement.
2. Reject emails failing SPF and DKIM validation.
3. Deploy advanced email filtering.
4. Conduct phishing awareness training.
5. Block executable downloads from email.
6. Monitor for additional emails using similar indicators.

---

# Lessons Learned

This investigation demonstrates how phishing campaigns combine social engineering with malicious payload delivery.

Proper email authentication, user awareness, and timely investigation significantly reduce the likelihood of successful compromise.

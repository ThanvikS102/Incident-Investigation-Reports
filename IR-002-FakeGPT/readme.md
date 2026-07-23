# IR-002: FakeGPT – Malware Analysis

## Overview

This project documents the investigation of a malicious browser extension named **FakeGPT**, completed as part of a malware analysis training exercise on CyberDefenders.

The investigation focuses on identifying malicious functionality within the extension, including credential theft, keylogging, and data exfiltration. Static analysis was performed on the extension source code to identify Indicators of Compromise (IOCs), understand attacker behavior, and map the observed techniques to the MITRE ATT&CK framework.

> **Disclaimer:** This investigation is based on a simulated training scenario provided by CyberDefenders and is intended for educational purposes only.

---

## Objectives

- Analyze a malicious browser extension.
- Identify malicious JavaScript functionality.
- Detect credential theft mechanisms.
- Identify keylogging behavior.
- Extract Indicators of Compromise (IOCs).
- Map attacker techniques to the MITRE ATT&CK framework.
- Document findings using a structured incident response report.

---

## Skills Demonstrated

- Malware Analysis
- Static Code Analysis
- Browser Extension Analysis
- JavaScript Analysis
- Threat Hunting
- IOC Extraction
- MITRE ATT&CK Mapping
- Incident Documentation

---

## Tools Used

- Visual Studio Code
- CyberDefenders Lab Environment
- Browser Developer Tools
- MITRE ATT&CK Framework
- VirusTotal (IOC Validation)

---

## Folder Structure

```
IR-002-FakeGPT/
│
├── Report.md
├── Report.pdf
├── Timeline.md
├── IOC.csv
├── README.md
│
├── Evidence/
│   ├── FakeGPT.zip
│   ├── manifest.json
│   └── JavaScript Files
│
└── Screenshots/
    ├── 01_Lab_Overview.png
    ├── 02_Extension_Files.png
    ├── 03_Manifest.png
    ├── 04_Malicious_Code.png
    ├── 05_IOCs.png
    └── 06_Completion.png
```

---

## Investigation Summary

The browser extension masqueraded as an AI assistant while secretly monitoring user activity. Analysis revealed functionality capable of collecting login credentials, recording keystrokes, and transmitting sensitive information to attacker-controlled infrastructure.

The extension also used Base64 encoding to obscure target URLs, making static analysis more difficult.

---

## MITRE ATT&CK Techniques

| Technique | ID |
|------------|-----|
| Phishing | T1566 |
| User Execution | T1204 |
| Input Capture: Keylogging | T1056.001 |
| Exfiltration Over Web Service | T1567 |
| Obfuscated Files or Information | T1027 |

---

## Learning Outcomes

This project improved my understanding of:

- Browser-based malware
- JavaScript malware analysis
- Credential theft techniques
- IOC extraction
- Malware documentation
- Threat intelligence reporting

---
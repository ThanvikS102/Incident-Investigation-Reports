# Incident Investigation Report

## Incident Information

| Field | Value |
|------|------|
| Incident ID | IR-002 |
| Incident Name | FakeGPT |
| Category | Malware Analysis |
| Severity | High |
| Status | Closed |
| Analyst | Thanvik S |
| Framework | NIST SP 800-61 |

---

# Executive Summary

A browser extension masquerading as an AI assistant was analyzed after exhibiting suspicious behavior. Static analysis revealed multiple malicious capabilities including credential harvesting, keystroke logging, and unauthorized transmission of collected data.

The extension used Base64 encoding to hide target URLs and reduce visibility during manual inspection. Based on the observed functionality, the extension presents a significant risk to user privacy and organizational security.

---

# Detection

The suspicious browser extension was identified during malware analysis training. Initial review indicated excessive permissions and embedded JavaScript functions capable of intercepting user credentials.

---

# Scope

Affected Platform

- Chromium-based browsers

Affected Asset

- Browser Extension

Threat Type

- Information Stealer

---

# Evidence Collected

- Browser extension package
- manifest.json
- JavaScript source files
- Extension configuration files

---

# Static Analysis

Analysis of the extension revealed:

- Obfuscated JavaScript
- Base64 encoded target URLs
- Functions responsible for credential interception
- Keylogging functionality
- Network communication routines used for data exfiltration

---

# Technical Findings

### Credential Theft

The extension monitored login forms and captured usernames and passwords entered by the victim.

### Keylogging

Keyboard events were monitored to record user input before submission.

### URL Obfuscation

Target URLs were stored using Base64 encoding, making malicious infrastructure less obvious during casual inspection.

### Data Exfiltration

Captured information was transmitted to attacker-controlled endpoints through JavaScript networking functions.

---

# Indicators of Compromise

| IOC Type | Description |
|----------|-------------|
| Browser Extension | FakeGPT |
| Base64 Encoded URLs | Used to conceal malicious destinations |
| JavaScript Functions | Credential collection and exfiltration |
| Manifest Permissions | Access to browsing activity and page content |

---

# MITRE ATT&CK Mapping

| Technique | ID |
|------------|------|
| User Execution | T1204 |
| Input Capture: Keylogging | T1056.001 |
| Obfuscated Files or Information | T1027 |
| Exfiltration Over Web Service | T1567 |
| Credentials from Web Browsers | T1555.003 |

---

# Root Cause

The malicious browser extension relied on social engineering by presenting itself as a legitimate AI productivity tool. Users installing the extension unknowingly granted elevated browser permissions, allowing the malware to monitor user activity and collect sensitive information.

---

# Containment

Recommended containment actions include:

- Remove the malicious extension immediately.
- Reset potentially compromised credentials.
- Review browser extensions across affected systems.
- Block identified malicious infrastructure.
- Perform endpoint malware scans.
- Monitor for additional suspicious browser activity.

---

# Recommendations

1. Install browser extensions only from trusted publishers.
2. Regularly review installed extensions and granted permissions.
3. Enable browser security policies in enterprise environments.
4. Conduct user awareness training regarding malicious extensions.
5. Deploy endpoint protection capable of detecting browser-based malware.

---

# Lessons Learned

This investigation demonstrates that browser extensions can act as effective malware delivery mechanisms while appearing legitimate to users. Static analysis of extension source code, permission requests, and embedded JavaScript provides valuable insight into attacker behavior and enables rapid identification of credential theft and data exfiltration techniques.

---

# Conclusion

The FakeGPT extension exhibited multiple malicious capabilities consistent with information-stealing malware. Prompt detection, removal, and user awareness are essential to reducing the impact of browser-based threats. The investigation successfully identified malicious behaviors, extracted relevant IOCs, and documented attacker techniques using the MITRE ATT&CK framework.
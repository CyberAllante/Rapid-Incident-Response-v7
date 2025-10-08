# 🧠 Malicious Process Detected — Cisco XDR Case Study (RIR v7)

> **Portfolio Project** — Demonstrating incident response and threat analysis skills using Cisco XDR, Microsoft Defender for Endpoint, and Secure Endpoint telemetry.

![License](https://img.shields.io/badge/Platform-Cisco%20XDR%20%7C%20Microsoft%20Defender-blue)
![Status](https://img.shields.io/badge/Status-Investigating-yellow)
![Certification](https://img.shields.io/badge/RIR%20v7-Certified-green)

---

## 📄 Executive Summary
This case study analyzes a **malicious process detection** involving `attacker[.]ihatemikesimone[.]com` in a simulated XDR environment.  
The incident involved multiple adversary behaviors such as:

- **OS Credential Dumping** (T1003)
- **Remote Services Exploitation** (T1021)
- **PowerShell Execution** (T1059.001)
- **Exfiltration Over C2 Channel** (T1041)
- **Masquerading** and **WMI-based lateral movement**

> 🧩 **Scope:** 6 devices, 11 users  
> 🧠 **Analyst:** Allante Johnson  
> 📅 **Detection Period:** May–September 2025  
> ⚙️ **Tools:** Cisco XDR, Secure Endpoint, Microsoft Defender for Endpoint, NGFW Event Service

---

## 🔍 Incident Details

### **Incident Summary**
- **Start Time:** 2025-05-07 10:40:01 UTC  
- **Confirmed By:** Sam Sanderson (2025-09-29)  
- **Status:** Open – Investigating  
- **Root Cause:** Exploitation of remote services and credential theft  
- **Products Used:** Cisco Secure Endpoint, Microsoft Defender for Endpoint, NGFW Event Service  

Errors were identified in **Secure Email Threat Defense**, prompting modifications to detection sources and techniques.

### **Key Artifacts**
| Category | Description |
|----------|-------------|
| **Devices** | 6 impacted hosts including domain controller |
| **Users** | SYSTEM, vic, remi, pat, krbtgt |
| **Malware Behavior** | mshta → PowerShell with Base64 encoding |
| **MITRE TTPs** | Credential Access, Lateral Movement, Exfiltration |
| **Indicators** | `198.18.133.150:8888` (C2), `Invoke-Mimikatz.ps1` |

---

## 🧰 Tools & Techniques
- **Telemetry Sources:** Cisco XDR, MDE, Secure Endpoint
- **Triage:** Correlation of mshta → PowerShell → LSASS memory access
- **Detection Rules:** Custom KQL hunting queries for suspicious base64 and WMI activity
- **Response Actions:**
  - Host isolation
  - Account disablement
  - IOC blocking at firewall/DNS
  - Artifact collection and forensic analysis

---

## 📈 Outcome
This case demonstrates:
- Proficiency in **threat hunting and triage**
- Building **KQL queries** and **SOC detections**
- Applying **MITRE ATT&CK** framework mapping
- Executing **RIR (Rapid Incident Response)** procedures

---

## 🧾 Supporting Documents
- 📘 **Incident Report (67 pages)** — [`report-incident-9d204a49.pdf`](./docs/incident/report-incident-9d204a49.pdf):contentReference[oaicite:0]{index=0}
- 🎓 **Certification:** [Rapid Incident Response v7 — Allante Johnson](./certs/1454694215AJ.pdf) (Issued Oct 3, 2025):contentReference[oaicite:1]{index=1}

---

## 🧭 Lessons Learned
- Harden LSASS and restrict PowerShell logging.
- Implement application control for LOLBins (`mshta.exe`).
- Strengthen detection coverage for WMI and ADS execution.
- Enhance correlation between XDR and EDR telemetry.

---

## 📜 Skills Demonstrated
- 🧠 Threat Detection & Analysis  
- 🧰 KQL & Advanced Hunting  
- ⚙️ SIEM/XDR Correlation  
- 📋 Incident Documentation (True Positive Report)  
- 🚨 SOC Playbook Execution

---

## 🧑‍💻 Author
**Allante Johnson**  
📚 *M.S. Cybersecurity & Information Assurance*  
🎓 *CompTIA CySA+, Pentest+, RIR v7 Certified*  
🔗 [LinkedIn](https://linkedin.com/in/allantejohnson) • [GitHub](https://github.com/CyberAllante)

---

